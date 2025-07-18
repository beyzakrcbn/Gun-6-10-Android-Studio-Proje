
# 📱 Android Studio ve Proje Yapısı - Temel Geliştirme Rehberi

Bu rehber, Android Studio kullanarak Android uygulama geliştirmeye başlamak isteyenler için temel kurulum, yapılandırma ve proje yapısını anlatan detaylı bir kaynaktır.

---

## 🎯 Hedef

Android geliştirme ortamını kurmak, proje yapısını anlamak, emülatör ile test gerçekleştirmek ve temel debugging araçlarını kullanmayı öğrenmek.

---

## 🧩 Öğrenilecek Konular

### 1. ✅ Android Studio Kurulumu ve Yapılandırması

**Android Studio**, Android uygulamaları geliştirmek için kullanılan resmi IDE'dir. Kotlin ve Java ile uyumlu çalışır.

- [Android Studio İndir](https://developer.android.com/studio)
- Kurulum sırasında:
  - **Android SDK**
  - **Emulator (AVD)**
  - **Android Virtual Device (AVD) Manager**
  - **Intel HAXM veya alternatif donanım hızlandırıcısı**

Kurulumdan sonra IDE otomatik olarak gerekli araçları indirir ve yapılandırır. Gerekirse SDK Manager üzerinden eksik bileşenleri yükleyebilirsiniz.

---

### 2. ✅ Android Proje Yapısı (src, res, manifests)

Android projeleri belirli bir klasör yapısına göre organize edilir:

```
MyApplication/
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/ → Kotlin veya Java kodları
│   │   │   ├── res/  → Görseller, layout, string tanımları
│   │   │   └── AndroidManifest.xml → Uygulama tanımı
```

**Detaylar:**

- `java/`: Tüm Kotlin veya Java dosyaları burada bulunur.
- `res/`: 
  - `layout/`: XML ile tanımlanan arayüzler.
  - `drawable/`: Görseller, vektörler.
  - `values/`: Renkler (`colors.xml`), stringler (`strings.xml`) ve temalar (`themes.xml`)
- `AndroidManifest.xml`: 
  - Uygulama adı
  - Başlangıç aktivitesi
  - İzinler (kamera, internet vb.)

---

### 3. ✅ Gradle Build System Temelleri

Gradle, Android projelerinin derlenmesini ve yapılandırılmasını sağlar.

#### Temel Dosyalar:
- `build.gradle (Project)`:
  - Tüm projeye özel ayarlar
  - Gradle versiyonu, plugin'ler
- `build.gradle (Module: app)`:
  - Uygulama ID'si
  - Minimum SDK
  - Bağımlılıklar (`dependencies { }`)

#### Örnek:
```groovy
android {
    compileSdk 34

    defaultConfig {
        applicationId "com.example.helloandroid"
        minSdk 21
        targetSdk 34
    }
}

dependencies {
    implementation "androidx.core:core-ktx:1.12.0"
    implementation "androidx.compose.ui:ui:1.6.0"
}
```

---

### 4. ✅ AVD (Android Virtual Device) Oluşturma

Gerçek bir cihaza ihtiyaç duymadan uygulamaları test etmeye yarar.

#### AVD Oluşturmak için:
- Android Studio > **Device Manager** > **Create Device**
- Cihaz modeli (Pixel 5 gibi) seçilir
- Sistem imajı (Android 11, API 30 vb.) indirilir
- Konfigürasyon yapılır ve emülatör başlatılır

> Emülatör, uygulamayı tıpkı gerçek cihazda çalıştırır gibi simüle eder.

---

### 5. ✅ Debugging Araçları

Android Studio, hata ayıklamak için güçlü araçlar sunar.

- **Logcat**: Uygulama içi log mesajlarını gösterir.
  ```kotlin
  Log.d("TAG", "Butona tıklandı!")
  ```
- **Breakpoints**: Kod üzerinde durdurma noktaları ekleyerek adım adım çalıştırmak.
- **Debugger Panel**: Değişken değerlerini gözlemleme, akışı kontrol etme.
- **Run & Debug Configurations**: Uygulama nasıl başlatılacak, hangi cihazda çalışacak gibi ayarlar.

---

## ✅ Kurulumdan Sonra Yapılacaklar

1. Android Studio kurulumu
2. Yeni proje oluştur ("Empty Activity" veya "Empty Compose Activity")
3. AVD kurulumu ve çalıştırma testi
4. Projeyi Git versiyon kontrolüne alma (isteğe bağlı)

```bash
git init
git add .
git commit -m "İlk Android projesi"
```

---

## 📚 Kaynaklar

- [Android Developers](https://developer.android.com/)
- [Jetpack Compose Resmi Dokümanları](https://developer.android.com/jetpack/compose)
- [Gradle Kullanımı](https://developer.android.com/studio/build)

---

## ✍️ Hazırlayan

Bu belge, Android geliştirmenin ilk adımlarında yol gösterici olması amacıyla hazırlanmıştır. Geri bildirimler ve katkılar için iletişime geçebilirsiniz.
