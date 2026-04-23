# boletroydev

Bu proje, uygulamalarını tek yerde tanıtmak ve her uygulama için ayrı gizlilik politikası sayfası yayımlamak için hazırlandı.

## 🚀 Özellikler

- **Uygulama Vitrin**: Modern kart tasarımı ile uygulama tanıtımı
- **Arama Fonksiyonu**: Uygulama kartlarını başlık ve açıklamaya göre ara
- **Koyu/Açık Tema**: Otomatik sistem tercihini algılayan tema değiştirici
- **Animasyonlar**: Yumuşak geçişler, hover efektleri ve arka plan animasyonları
- **Responsive Tasarım**: Mobil uyumlu, tüm cihazlarda çalışır
- **Gizlilik Politikaları**: Her uygulama için ayrı, Google Play uyumlu politika sayfaları
- **SEO Dostu**: Meta etiketleri ve yapılandırılmış veriler

Ana mantık:

- Ana vitrin sayfası: [index.html](./index.html)
- Uygulama verileri: [apps.json](./apps.json)
- Uygulamaya özel gizlilik sayfaları:
  `gymix-privacy.html`
  `downgrade-privacy.html`
  `fastwallet-privacy.html`
  `voltlog-privacy.html`
  `calf-raises-privacy.html`

Bu yapı özellikle şu senaryo için uygun:

- Uygulamalar çok büyük değil
- Her uygulama için Google Play'e verilecek ayrı bir privacy policy linki lazım
- Bazı uygulamaların kendi web sitesi var, bazılarının yok
- Test linkleri de aynı yerde yönetilmek isteniyor

## Dosya Yapısı

- `index.html`
  Ana vitrin, uygulama kartları, detay ekranı ve politika merkezi.
- `apps.json`
  Yeni uygulama eklerken dolduracağın ana veri dosyası.
- `*-privacy.html`
  Her uygulama için bağımsız gizlilik politikası sayfası.
- `icons/`
  Uygulama ikonları.

## Yeni App Ekleme

Yeni bir app eklerken genelde 4 adım yeterli:

1. İkonu `icons/` klasörüne koy.
2. `apps.json` içine yeni uygulamayı ekle.
3. Aynı uygulama için yeni bir `*-privacy.html` dosyası oluştur.
4. Gerekirse test linklerini ve website linkini doldur.

## Kullanım

- **Ana Sayfa**: Tüm uygulamaları listeler
- **Arama**: Navigasyon çubuğundaki arama kutusu ile uygulama ara
- **Detay**: Karttaki "Detaya Git" butonu ile uygulama detaylarını gör
- **Gizlilik**: "Gizlilik" butonu ile politika sayfasına git
- **Tema**: Sağ üstteki tema butonu ile koyu/açık modu değiştir
- **Başa Dön**: Sayfa sonundaki ↑ butonu ile tepeye dön

## apps.json Şablonu

Yeni uygulama eklerken aşağıdaki yapıyı kopyalayıp düzenleyebilirsin:

```json
{
  "yeni-app-id": {
    "title": "Yeni App",
    "icon": "icons/yeni-app.png",
    "desc": "Uygulamanın kısa açıklaması.",
    "features": [
      "Özellik 1",
      "Özellik 2",
      "Özellik 3"
    ],
    "version": "1.0.0",
    "websiteUrl": "#",
    "playStoreUrl": "#",
    "appStoreUrl": "#",
    "testLinks": [
      {
        "label": "Android Test",
        "url": "#",
        "note": "APK veya internal test bağlantısı"
      },
      {
        "label": "iOS Test",
        "url": "#",
        "note": "TestFlight bağlantısı"
      }
    ],
    "badge": "Yeni",
    "privacyPage": "yeni-app-privacy.html",
    "privacy": {
      "lastUpdated": "21 Nisan 2026",
      "summary": "Bu uygulamanın kısa gizlilik özeti.",
      "dataCollected": [
        "Toplanan veri 1",
        "Toplanan veri 2"
      ],
      "dataNotCollected": [
        "Toplanmayan veri 1",
        "Toplanmayan veri 2"
      ],
      "usagePurposes": [
        "Amaç 1",
        "Amaç 2"
      ],
      "sharing": "Veri paylaşımı ile ilgili açıklama.",
      "storage": "Veri saklama ile ilgili açıklama.",
      "security": "Güvenlik önlemleri ile ilgili açıklama.",
      "children": "Çocukların gizliliği ile ilgili açıklama.",
      "userRights": "Kullanıcı hakları ile ilgili açıklama."
    }
  }
}
```

## Alanların Anlamı

- `title`
  Uygulamanın görünen adı.
- `icon`
  `icons/` klasöründeki ikon yolu.
- `desc`
  Kartta ve detay sayfasında görünen kısa açıklama.
- `features`
  Kısa madde listesi.
- `version`
  Mevcut sürüm bilgisi.
- `websiteUrl`
  Uygulamanın kendi sitesi varsa linkini yaz. Yoksa `"#"` bırak.
- `playStoreUrl`
  Mağaza linki varsa ekle. Yoksa `"#"`.
- `appStoreUrl`
  App Store linki varsa ekle. Yoksa `"#"`.
- `testLinks`
  TestFlight, APK, Firebase App Distribution veya kapalı test linkleri.
- `badge`
  `"Yeni"`, `"Güncellendi"` ya da `null`.
- `privacyPage`
  O uygulamaya ait bağımsız gizlilik dosyasının adı.
- `privacy`
  Uygulama için detaylı politika içeriği.

## Website Alanı Nasıl Çalışır?

- `websiteUrl` gerçek bir link ise kartta ve detay sayfasında `Website` butonu görünür.
- `websiteUrl` `"#"` ise buton çıkmaz.
- Ayrıca uygulama kartında durum etiketi görünür:
  sitesi varsa `Website Hazır`
  sitesi yoksa `Website Yakında`

Bu sayede bazı uygulamalarda site varken bazılarında yoksa arayüz bozulmaz.

## Test Linkleri Nasıl Çalışır?

- `testLinks` içindeki `url` gerçek bir link ise buton görünür.
- `url` `"#"` ise buton görünmez.
- Test linki yoksa detay ekranında ve gizlilik sayfasında bilgilendirici bir not görünür.

Örnek test linkleri:

- Google Play internal testing
- Google Play closed testing
- Firebase App Distribution
- Direkt APK linki
- TestFlight

## Gizlilik Sayfası Nasıl Oluşturulur?

En kolay yöntem:

1. Var olan privacy sayfalarından birini kopyala.
2. Dosya adını yeni uygulamaya göre değiştir.
3. Başlıkları, ikon yolunu ve metinleri düzenle.
4. `apps.json` içindeki `privacyPage` alanını bu yeni dosya adıyla eşleştir.

Örnek:

- yeni dosya: `superapp-privacy.html`
- `privacyPage`: `"superapp-privacy.html"`

## Google Play İçin Öneri

Google Play tarafında mümkünse her uygulama için ayrı privacy page kullan:

- `gymix-privacy.html`
- `downgrade-privacy.html`
- `fastwallet-privacy.html`

Bu yöntem tek genel politika sayfasından daha temiz görünür.

## Kendi Websitesi Olan App'ler

Bir uygulamanın kendi domaini varsa:

- `websiteUrl` alanına gerçek siteyi yaz
- istersen sonra privacy sayfasını da o domaine taşı
- ama istersen bu repo içindeki privacy sayfasını kullanmaya devam et

Yani iki model de mümkün:

- tanıtım sitesi dışarıda, privacy burada
- hem tanıtım hem privacy uygulamanın kendi sitesinde

## Hızlı Kontrol Listesi

Yeni bir uygulama ekledikten sonra şunları kontrol et:

1. İkon doğru görünüyor mu
2. Kart açılıyor mu
3. Detay sayfası açılıyor mu
4. Gizlilik sayfası açılıyor mu
5. `privacyPage` dosyası gerçekten var mı
6. Website linki varsa çalışıyor mu
7. Test linki varsa çalışıyor mu

## Kısa Özet

Yeni app eklerken normalde sadece şunları yapman yeterli:

1. `apps.json` içine uygulamayı ekle
2. `*-privacy.html` dosyasını oluştur
3. ikon ekle
4. varsa website ve test linklerini doldur

Bu dört adımla sistemi kendi başına rahatça büyütebilirsin.
