# CLEARMAIL PROTOTİP TASLAĞI

## Giriş

Bu doküman, Thunderbird altyapısını kullanarak geliştirilecek Clearmail uygulamasının başlangıç prototipinin oluşturulması için gerekli adımları ve temel özellikleri tanımlamaktadır. Prototip aşaması, projenin fizibilite değerlendirmesi ve temel konsept doğrulaması için kritik önem taşımaktadır.

## 1. Prototip Kapsamı

Prototip aşamasında aşağıdaki temel özellikler geliştirilecektir:

1. **Temel Marka Değişiklikleri:**
   - Thunderbird logo ve isim değişiklikleri
   - Clearmail marka kimliği uygulaması
   - Basit arayüz renk ve tema güncellemeleri

2. **Exchange 2019 Bağlantısı:**
   - EWS API ile temel bağlantı
   - E-posta alma ve gönderme
   - Klasör yapısı senkronizasyonu
   - Takvim entegrasyonu

3. **Basit Kural Motoru:**
   - Temel filtreleme özellikleri
   - Kural oluşturma arayüzü
   - Otomatik kategorilendirme

4. **Kullanıcı Arayüzü İyileştirmeleri:**
   - Modernize edilmiş e-posta görüntüleme
   - Geliştirilmiş liste görünümü
   - Mobil uyumlu tasarım temelleri

## 2. Teknik Yaklaşım

### 2.1. Thunderbird Fork Süreci

```bash
# GitHub üzerinden Thunderbird repo'sunu fork etme
git clone https://github.com/mozilla/releases-comm-central.git clearmail
cd clearmail

# Geliştirme için yeni bir branch oluşturma
git checkout -b clearmail-dev

# Gerekli bağımlılıkları kurma
./mach bootstrap

# İlk test derlemesi
./mach build
```

### 2.2. Marka Değişiklikleri

Marka değişiklikleri için değiştirilmesi gereken temel dosyalar:

- `/mail/branding/` dizinindeki logo ve grafik öğeleri
- `/mail/locales/en-US/chrome/messenger/messenger.properties` dosyasındaki metin değişiklikleri
- `mail/app/` dizinindeki uygulama bilgileri

### 2.3. Exchange Entegrasyonu

Exchange 2019 entegrasyonu için şu adımlar izlenecektir:

1. Mevcut IMAP/POP3 işlevselliğinin üzerine EWS API desteği eklenecek
2. Kimlik doğrulama için OAuth 2.0 desteği eklenecek
3. Exchange özel özelliklerini desteklemek için genişletme yapılacak

### 2.4. Kural Motoru Geliştirmeleri

Mevcut Thunderbird kural motoru temel alınarak:

1. Daha esnek kural oluşturma yapısı için JavaScript genişletmeleri
2. Kullanıcı arayüzü iyileştirmeleri
3. Gelişmiş eylem tipleri desteği

## 3. Prototip Geliştirme Aşamaları

### Aşama 1: Hazırlık ve Kurulum (1-2 Hafta)
- Geliştirme ortamının kurulması
- Kaynak kodun forku ve ilk derleme
- Proje yapısı analizi
- Değiştirilecek bileşenlerin belirlenmesi

### Aşama 2: Temel Marka Değişiklikleri (1-2 Hafta)
- Logo ve isim değişiklikleri
- Uygulama içi metinlerin güncellenmesi
- Splash ekranı ve simge değişiklikleri
- Basit tema renk değişiklikleri

### Aşama 3: Exchange Bağlantı Modülü (3-4 Hafta)
- EWS API entegrasyonu için gerekli kütüphanelerin eklenmesi
- OAuth 2.0 kimlik doğrulama mekanizmasının entegrasyonu
- Temel e-posta işlemleri için API bağlantıları
- Adres defteri ve takvim senkronizasyonu

### Aşama 4: Kural Motoru Genişletmeleri (2-3 Hafta)
- Kural tanımlama arayüzünün modernizasyonu
- Gelişmiş kural aksiyonlarının eklenmesi
- Otomatik kategorizasyon algoritması

### Aşama 5: Arayüz İyileştirmeleri (2-3 Hafta)
- Ana posta görünümü güncellemesi
- Liste görünümlerinin modernizasyonu
- Tepkisel tasarım unsurlarının eklenmesi
- Genel kullanıcı deneyimi iyileştirmeleri

### Aşama 6: Test ve İyileştirmeler (2 Hafta)
- Fonksiyonel testler
- Performans testleri
- Kullanılabilirlik testleri
- Hata düzeltme ve iyileştirmeler

## 4. Prototip Test Kriterleri

### 4.1. Temel İşlevsellik
- Exchange 2019 sunucusuna başarılı bağlantı
- E-posta alma ve gönderme
- Klasörler arasında gezinme
- Takvim öğelerine erişim

### 4.2. Performans Kriterleri
- Başlangıç süresi (30 saniyeden az)
- E-posta indekslemesi (1000 e-posta için 5 dakikadan az)
- Arayüz tepki süresi (maksimum 1 saniye)

### 4.3. Kullanıcı Deneyimi Kriterleri
- Temel görevleri tamamlama süresi
- Kural oluşturma kolaylığı
- Arayüz tutarlılığı

## 5. Geliştirme Ortamı Gereksinimleri

### 5.1. Donanım Gereksinimleri
- Minimum 16GB RAM
- SSD depolama (en az 100GB boş alan)
- Multicore işlemci (8+ çekirdek önerilen)

### 5.2. Yazılım Gereksinimleri
- Linux, macOS veya Windows 10/11
- Git ve Mercurial versiyon kontrol sistemi
- Mozilla Build paketi
- C++ derleyicisi
- Python 3.6+
- Rust derleyicisi
- Node.js (arayüz geliştirmeleri için)

### 5.3. Test Ortamı
- Exchange 2019 test sunucusu
- Test hesapları
- Farklı istemci platformları (Windows, macOS, Linux)

## 6. Kaynak Gereksinimi

### 6.1. İnsan Kaynağı
- 1 Kıdemli C++/XUL Geliştirici
- 1 Exchange API Uzmanı
- 1 UI/UX Tasarımcı
- 1 Test Mühendisi

### 6.2. Zaman Planlaması
- Toplam prototip geliştirme süresi: 10-14 hafta
- Haftalık gözden geçirme toplantıları
- 2 haftalık sprint döngüleri

## 7. Çıktılar

Prototip aşaması sonunda aşağıdaki çıktılar teslim edilecektir:

1. **Clearmail Prototip Uygulaması:**
   - Windows, macOS ve Linux için installer
   - Kaynak kod deposu
   - Derleme talimatları

2. **Teknik Dokümantasyon:**
   - Mimari diyagramlar
   - API entegrasyon belgeleri
   - Geliştirici kılavuzu

3. **Test Raporları:**
   - Fonksiyonel test sonuçları
   - Performans testi sonuçları
   - Bilinen sorunlar ve sınırlamalar listesi

4. **İleri Geliştirme Planı:**
   - Tam ürün geliştirme yol haritası
   - Kaynak gereksinimleri
   - Risk değerlendirmesi

## 8. Sonraki Adımlar

Prototip aşaması tamamlandıktan sonra:

1. Prototip değerlendirmesi ve geri bildirim toplama
2. Tam ürün geliştirme planının finalize edilmesi
3. Ürün yol haritasının oluşturulması
4. Geliştirme ekibinin genişletilmesi
5. Tam ürün geliştirme fazına geçiş