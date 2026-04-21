# boletroydev - Apps Showcase Website

## 🚀 Yeni App Ekleme Rehberi

Web sitenize yeni bir app eklemek **çok kolay**! Sadece `apps.json` dosyasına yeni bir entry ekleyin.

---

## 📋 apps.json Yapısı

```json
{
  "benzersiz-app-id": {
    "title": "App Adı",
    "icon": "icons/app-logo.png",
    "desc": "Kısa açıklama (1-2 cümle)",
    "features": ["Özellik 1", "Özellik 2", "Özellik 3"],
    "version": "1.0.0",
    "playStoreUrl": "https://play.google.com/store/apps/details?id=...",
    "appStoreUrl": "https://apps.apple.com/app/...",
    "privacy": "Gizlilik politikası metni (3-5 cümle)",
    "badge": "Yeni" // "Yeni", "Güncellendi" veya null
  }
}
```

---

## 🎯 Hızlı Ekleme Adımları

### 1. App İkonunu Hazırlayın

- Logonuzu `icons/` klasörüne ekleyin
- Format: `.png`, `.jpg` veya `.jpeg`
- Boyut: 512x512px idealdir

### 2. apps.json'a Entry Ekleyin

```json
{
  "yeni-appim": {
    "title": "Süper App",
    "icon": "icons/super-app-logo.png",
    "desc": "Bu harika bir uygulama. Çok işe yarar.",
    "features": ["Hızlı ve güvenli", "Kullanımı kolay", "Çevrimdışı çalışır"],
    "version": "1.0.0",
    "playStoreUrl": "https://play.google.com/store/apps/details?id=com.example",
    "appStoreUrl": "https://apps.apple.com/app/...",
    "privacy": "Uygulamak verilerinizi şifrelenmiş olarak cihazınızda saklar. Hiçbir veri servis sunucularına gönderilmez.",
    "badge": "Yeni"
  }
}
```

### 3. Tarayıcıyı Yenileyin

- `F5` tuşuna basarak sayfayı yenileyin
- Yeni app'iniz anında görünecek! 🎉

---

## 📌 Önemli Notlar

- **benzersiz-app-id**: Her app için türkçe karaktersiz, benzersiz bir kimlik kullanın
- **title**: App mağazasında görünen adı kullanın
- **icon**: Dosya yolu `icons/` klasörüne göre olmalı
- **features**: 3-4 özellik yeterlidir
- **privacy**: Google Play'de gizlilik politikası gerekli
- **playStoreUrl**: Henüz yayınlanmadıysa `"#"` yazın
- **appStoreUrl**: Henüz yayınlanmadıysa `"#"` yazın
- **badge**: `"Yeni"` ya da `"Güncellendi"` yazın, yoksa `null` bırakın

---

## 🎨 İkon Önerileri

Kullanılan Formatlar:

- ✅ `gymix-logo.jpg` (JPG)
- ✅ `fastwallet-logo.png` (PNG)
- ✅ `downgrade-logo.png` (PNG)

---

## 📱 Örnek: Google Play & App Store Linkler

**Google Play:**

```
https://play.google.com/store/apps/details?id=com.yourcompany.appname
```

**App Store:**

```
https://apps.apple.com/us/app/app-name/id1234567890
```

---

## ✨ Otomatik Özellikler

- ✅ Dark Mode desteği
- ✅ Responsive tasarım (mobil/tablet/desktop)
- ✅ Detay sayfası
- ✅ Gizlilik politikası görünümü
- ✅ Animasyonlar

---

**Hepsi bu kadar!** Yeni app eklemek için sadece `apps.json`'a 10 satır eklemek yeterli! 🚀
