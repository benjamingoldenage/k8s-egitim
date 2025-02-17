# Dashboard

Bir özellik kurmak isterseniz (örneğin dashboard), ``inventory/mycluster/group_vars/k8s_cluster/addons.yml``  dosyasındaki 4. satırdaki 
```yaml
# dashboard_enabled: true
```
satırı

```yaml
dashboard_enabled: true
```
şeklinde değiştirilir ve cluster.yml tekrar çalıştırılır. 

```sh
ansible-playbook -i inventory/mycluster/hosts.yaml -b cluster.yml -u <kullanıcı> -kK --tags dashboard
```
[Kullanılabilecek farklı tagler](https://github.com/kubernetes-sigs/kubespray/blob/master/docs/ansible.md)

### Dashboard alternatif kurulum

[Buradaki kurulum](https://github.com/kubernetes/dashboard) ile kurulur. 

### Dışarıdan Erişim için Nodeport Tanımı

```sh
kubectl edit -n kube-system   svc kubernetes-dashboard

...
  type: ClusterIP
...

# =>
...
  type: NodePort
... 

# aynı dosyada aşağıdaki satır altına yeni bir satır ekliyoruz.
...
    targetPort: 8443
...

#=>
...
    targetPort: 8443
    nodePort: 30333
...
```
### Dashboard için admin kullanıcı oluşturma

[Buradaki kurulum](https://github.com/kubernetes/dashboard/blob/master/docs/user/access-control/creating-sample-user.md) ile tam yetkili kullanıcı oluşturulur.

```yaml

apiVersion: v1
kind: ServiceAccount
metadata:
  name: admin-user
  namespace: kubernetes-dashboard

---

apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: admin-user
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: cluster-admin
subjects:
- kind: ServiceAccount
  name: admin-user
  namespace: kubernetes-dashboard

--- 

```

```sh

kubectl -n kubernetes-dashboard get secret $(kubectl -n kubernetes-dashboard get sa/admin-user -o jsonpath="{.secrets[0].name}") -o go-template="{{.data.token | base64decode}}"

```

[dashboard](https://github.com/kubernetes/dashboard/blob/master/docs/images/signin.png)
