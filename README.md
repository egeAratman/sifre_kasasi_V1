# Şifre Kasası (Password Vault)

Güvenli şifre yöneticisi uygulaması. Bu uygulama, şifrelerinizi cihazınıza özel benzersiz kimlik ile SHA-256 şifreleme kullanarak maksimum güvenlikle saklar.
bu proje tübitak desteği ile kapadokya üniversitesinde yapılmıştır
screenshot lara screenshots clasöründen ulaşabilirsiniz

## 🔐 Güvenlik Özellikleri

### Cihaza Özel Şifreleme
- **Benzersiz Cihaz ID'si**: Her cihaz için otomatik olarak benzersiz bir kimlik oluşturulur
- **SHA-256 Şifreleme**: Endüstri standardı şifreleme algoritması kullanılır
- **Salt ile Şifreleme**: Her şifre farklı salt değeriyle şifrelenir
- **XOR Şifreleme**: Hızlı ve güvenli XOR algoritması kullanılır

### Çapraz Cihaz Güvenliği
- **Cihaz Doğrulaması**: Veriler yalnızca kaydetildikleri cihazda çözülebilir
- **Yetkisiz Erişim Koruması**: Farklı bir cihazda veriler otomatik olarak çözülemez
- **Güvenlik Uyarı Sistemi**: Yetkisiz cihaz erişimi tespit edildiğinde kullanıcı uyarılır

### Veri Koruması
- **Yerel Depolama**: Veriler yalnızca cihazda saklanır, buluta gönderilmez
- **Şifrelenmiş Backup**: Tüm şifreler şifrelenmiş formatta saklanır
- **Güvenli Silme**: Veriler güvenli şekilde temizlenebilir

## 📱 Kullanım

1. **İlk Kurulum**: Uygulamayı ilk açtığınızda ana şifrenizi belirleyin
2. **Şifre Ekleme**: Vault ekranında yeni şifrelerinizi ekleyin
3. **Şifre Görüntüleme**: Kaydedilen şifrelerinizi görüntüleyin ve kopyalayın
4. **Güvenlik**: Cihaz değiştirdiğinizde verileriniz otomatik olarak korunur

## 🛡️ Güvenlik Mimarisi

```
Kullanıcı Şifresi → [SHA-256 + Cihaz ID] → Şifreleme Anahtarı → XOR + Salt → Şifrelenmiş Veri
```

### Şifreleme Süreci
1. Cihazın benzersiz ID'si alınır (Android ID, iOS Identifier, vs.)
2. ID ile birleştirilmiş anahtar materyali SHA-256 ile hash'lenir
3. Rastgele salt değeri oluşturulur
4. Veri salt ile birleştirilir
5. XOR algoritması ile şifrelenir
6. Base64 formatında saklanır

### Cihaz Doğrulama
- Uygulama her açıldığında cihaz kimliği kontrol edilir
- Farklı cihaz tespit edilirse güvenlik uyarısı gösterilir
- Yetkisiz erişimde veriler çözülemez

## 🚀 Kurulum

### Gereksinimler
- Flutter SDK (>=3.5.3)
- Dart SDK
- Android Studio / VS Code
- Android/iOS cihaz veya emülatör

### Bağımlılıklar
```yaml
dependencies:
  flutter:
    sdk: flutter
  crypto: ^3.0.6
  device_info_plus: ^11.1.0
  shared_preferences: ^2.5.3
  cupertino_icons: ^1.0.8
```

### Çalıştırma
```bash
# Bağımlılıkları yükle
flutter pub get

# Uygulamayı çalıştır
flutter run

# APK oluştur
flutter build apk --release
```

## 🧪 Test

```bash
# Tüm testleri çalıştır
flutter test

# Şifreleme testlerini çalıştır
flutter test test/encryption_test.dart
```

## 📋 Özellikler

### 🔐 Güvenlik
- ✅ SHA-256 + Cihaz ID şifreleme
- ✅ Cihaza özel koruma
- ✅ Çapraz cihaz güvenliği
- ✅ Güvenlik uyarı sistemi
- ✅ Yerel veri depolama

### 🎨 Modern Arayüz
- ✅ Material Design 3 uyumlu
- ✅ Gradient ve animasyonlar
- ✅ Card-based tasarım
- ✅ Responsive layout
- ✅ Karanlık/Aydınlık tema

### 🚀 Fonksiyonaliteler
- ✅ Güçlü şifre oluşturucu
- ✅ Şifre gücü analizi
- ✅ Akıllı arama ve filtreleme
- ✅ One-tap şifre kopyalama
- ✅ Şifre düzenleme ve silme
- ✅ Güvenli veri temizleme

## ⚠️ Önemli Notlar

- **Yedekleme**: Cihazınızı kaybetmeniz durumunda verilerinizi kurtarmanın bir yolu yoktur
- **Ana Şifre**: Ana şifrenizi unutursanız tüm verileriniz kaybolur
- **Güvenlik**: Bu uygulama maksimum güvenlik için tasarlanmıştır, ancak %100 güvenlik garanti edilemez
- **Sorumluluk**: Veri kaybından geliştiriciler sorumlu tutulamaz

## 📞 Destek

Sorularınız veya sorunlarınız için GitHub Issues bölümünü kullanabilirsiniz.

## 📄 Lisans

Bu proje MIT lisansı altında lisanslanmıştır.r_demo

A new Flutter project.

## Getting Started

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
