# ESP8266 HomeKit LED Kontrol Projesi

Bu proje, ESP8266 mikrodenetleyici kartını kullanarak Apple HomeKit üzerinden bir LED'i kontrol etmeyi sağlar. Proje, ESP8266'nın WiFi özelliklerini kullanarak yerel ağınıza bağlanır ve HomeKit uygulaması üzerinden LED'i açıp kapatmanıza olanak tanır.

## Proje Açıklaması

Proje, ESP8266 kartının D1 pinine bağlı bir LED'i Apple HomeKit uygulaması üzerinden kontrol etmenizi sağlar. HomeKit uygulamasına cihaz ekleyerek, belirlediğiniz şifre ile cihazı eşleştirebilir ve LED'i açıp kapatabilirsiniz.

## Kurulum

### Gereksinimler

- **ESP8266** mikrodenetleyici kartı
- **Arduino IDE** (ESP8266 desteği ile kurulu)
- **Apple HomeKit** uygulaması (iOS cihazlarda)
- **LED** ve direnç (isteğe bağlı, D1 pinine bağlanacak)

### Adım Adım Kurulum

1. **Arduino IDE'yi Hazırlama**:
   - Arduino IDE'yi açın ve `arduino_homekit_server` kütüphanesini kurun.
   - ESP8266 kartını seçin ve doğru portu ayarlayın.

2. **WiFi Bilgilerini Güncelleme**:
   - `wifi_info.h` dosyasını açın ve aşağıdaki satırları kendi WiFi ağ bilgilerinizle güncelleyin:
     ```cpp
     const char *ssid = "Wifi-Name";
     const char *password = "Password";
     ```
   - `Wifi-Name` ve `Password` yerine kendi WiFi ağınızın adını ve şifresini girin.

3. **Kodu Yükleme**:
   - `test.ino` dosyasını Arduino IDE'de açın ve kodu ESP8266 kartınıza yükleyin.

4. **HomeKit ile Eşleştirme**:
   - iOS cihazınızda HomeKit uygulamasını açın.
   - "Cihaz Ekle" seçeneğini kullanarak ESP8266 kartını bulun.
   - Şifre olarak `111-11-111` girin ve cihazı eşleştirin.

5. **LED Kontrolü**:
   - HomeKit uygulamasında oluşturduğunuz buton ile LED'i açıp kapatabilirsiniz.

## Dosyalar

- **test.ino**: Ana proje dosyası. ESP8266'nın HomeKit ile iletişim kurmasını sağlar.
- **wifi_info.h**: WiFi ağ bilgilerinin bulunduğu dosya. Kullanıcılar bu dosyayı kendi WiFi bilgileri ile güncellemeli.
- **my_accessory.c**: HomeKit karakteristiklerini ve ayarlarını tanımlar.

## Önemli Notlar

- **WiFi Bilgileri**: Kullanıcıların kendi WiFi ağ bilgilerini `wifi_info.h` dosyasına girmesi gerekmektedir. Aksi takdirde ESP8266 kartı internete bağlanamaz.
- **HomeKit Şifresi**: HomeKit eşleştirme şifresi `111-11-111` olarak ayarlanmıştır. Bu şifreyi değiştirmek isterseniz `my_accessory.c` dosyasındaki `config` yapısını güncelleyebilirsiniz.

## Katkıda Bulunma

Eğer bu projeyi geliştirmek veya yeni özellikler eklemek isterseniz, lütfen aşağıdaki adımları takip edin:

1. Repoyu forklayın.
2. Yeni bir branch oluşturun (`git checkout -b yeni-ozellik`).
3. Değişikliklerinizi commit edin (`git commit -am 'Yeni özellik eklendi'`).
4. Branch'inizi pushlayın (`git push origin yeni-ozellik`).
5. Bir Pull Request oluşturun.

## Lisans

Bu proje MIT Lisansı altında lisanslanmıştır. Daha fazla bilgi için [LICENSE](LICENSE) dosyasına bakın.

---

Bu `README.md` dosyası, projenizi kullanacak kişilere rehberlik edecek ve kendi WiFi bilgilerini nasıl gireceklerini açıklayacaktır. Ayrıca, projenin nasıl çalıştığını ve nasıl katkıda bulunabileceklerini de belirtmiş olursunuz. Başarılar dilerim!
