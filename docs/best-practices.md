# best practices

```

Erişilebilirlik

    liveness and readiness prop'ları doğru şekilde yapılandırıldı mı?
    Master Node'lar tek sayı ve en az 3 tane mi?
    Kopya etcd servisleri izole edildi mi?
    Düzenli etcd yedeklemeleri için bir planınız var mı?
    Master Node'lar bölgeler arası dağıtıldı mı?
    Worker (İşçi) Node'lar bölgeler arası dağıtıldı mı?

    Master ve Worker (işçi) Node'lar için Autoscaling ayarlandı mı?
    Yüksek erişilebilir yük dengeleme oluşturuldu mu?

    Scheduler ve controller manager için aktif-pasif yapılandırma var mı?

    Yüksek erişilebilirlik için doğru sayıda pod kopyası oluşturuldu mu?
    Spinning up any naked pods?
    Çoğul küme federasyonu yapılandırıldı mı?

    etcd servisleri için heartbeat ve master seçim zaman aşımı ayarlandı mı?
    Ingress yapılandırıldı mı?

Kaynak Yönetimi

    Konteynerler için kaynak istekleri ve sınırları yapılandırıldı mı?

    Yerel geçici depolama için belirtilen kaynak istekleri ve sınırları yapılandırıldı mı?

    Ekipleriniz için ayrı ad alanları oluşturdunuz mu?

    Ad alanları için varsayılan kaynak istekleri, sınır aralıkları ve sınırları yapılandırıldı mı?

    Ad alanları için pod ve API Kotaları yapılandırıldı mı?

    Etcd için yeterli kaynak sağlandı mı?

    Etcd için anlık bellek kullanımı yapılandırıldı mı?

    Kubernetes nesnelerine etiketler eklendi mi?

    Bir düğümde çalışabilen kapsül sayısı sınırlandı mı?

    Sistem arka plan programları için ayrılmış işlem kaynakları yapılandırıldı mı?

    API sunucusu için API istek işleme yapılandırıldı mı?

    Kaynak kalmaması durumunda yapılacaklar yapılandırıldı mı?

    PersistentVolumes için önerilen ayarları mı kullanıyorsunuz?

    Etkinleştirilmiş log döndürme var mı?

    Kubelet'in etiket anahtarlarını ayarlamasını veya değiştirmesini engellediniz mi?

Güvenlik

    En son Kubernetes sürümünü mü kullanıyorsunuz?

    Etkin RBAC (Rol Tabanlı Erişim Kontrolü) var mı?

    Kullanıcı erişimiyle ilgili en iyi uygulamaları takip ediyor musunuz?

    Denetim günlüğü etkinleştirildi mi?

    Kale barındırıcısı mı kuruyorsunuz (Erişim için ara sistem)?

    Kabul denetleyicisinde AlwaysPullImages etkinleştirildi mi?

    Pod güvenlik politikası tanımlandı ve kabul denetleyicisinde etkinleştirildi mi?

    Bir Ağ eklentisi ve yapılandırılmış ağ politikaları mı seçtiniz?

    Kubelet için kimlik doğrulama uygulandı mı?

    Kubernetes sırlarını yapılandırdınız mı?

    Beklemede veri şifrelemeyi etkinleştirdiniz mi?

    Varsayılan hizmet hesabı devre dışı bırakılsın mı?

    Güvenlik açıkları için konteynerler tarandı mı?

    Podlar, konteynerler ve birimler için yapılandırılmış güvenlik bağlamı var mı?

    Kubernetes loglama etkinleştirildi mi?

Ölçeklendirme

    Yatak ölçeklendirme yapılandırıldı mı?
    Dikey ölçeklendirme yapılandırıldı mı?
    Küme ölçeklendirme yapılandırıldı mı?

İzleme

    İzleme hattı kuruldu mu?
    İzlemek için ölçüm listeleri oluşturuldu mu

Ek

    Uçtan uca test (e2e test) yapıldı mı?
    Dış servisleri kubernetes içinden erişilecek şekilde tasarladınız mı?
    DNS add-on'u yüklendi mi?

```


Kaynaklar

https://www.weave.works/blog/production-ready-checklist-kubernetes

https://www.weave.works/weave-kubernetes-platform-how-to-guide/

Kubernetes Production Readiness and Best Practices Checklist.pdf

https://learnk8s.io/production-best-practices

https://www.youtube.com/results?search_query=%23KubernetesBestPractices