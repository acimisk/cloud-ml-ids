# Makine Öğrenmesi Destekli Bulut Sunucularında Çok Tipli Saldırı Tespiti ve Otonom Yanıt Sistemi

## Özet

Bu çalışma, küçük ve orta ölçekli bulut sunucularında gerçekleşebilecek çok tipli saldırıların log verileri üzerinden tespit edilmesi ve otomatik olarak engellenmesini amaçlayan bir güvenlik sistemi geliştirmektedir. Sistem; SSH brute-force, yavaş ve uzun süreli saldırılar (slow attacks), botnet davranışları, DDoS ve diğer anormal ağ aktivitelerini makine öğrenmesi tabanlı risk skorlaması ile analiz etmektedir. Geleneksel kural tabanlı yöntemlerden farklı olarak, davranışsal analiz, sliding window yaklaşımı ve korelasyon temelli değerlendirme mekanizmaları kullanılmaktadır. Tespit edilen tehditlere karşı otomatik engelleme, beyaz liste yönetimi ve geri alma (rollback) mekanizmaları içeren otonom bir yanıt yapısı tasarlanmıştır. Ayrıca saldırıların raporlanması ve izlenmesi amacıyla bildirim ve gösterge paneli altyapısı sağlanmaktadır.

## Anahtar Kelimeler

Bulut Güvenliği, Makine Öğrenmesi, Saldırı Tespiti, Anomali Tespiti, Log Analizi, Otonom Güvenlik Sistemleri

## 1. Giriş

Bulut tabanlı sistemlerin yaygınlaşmasıyla birlikte sunucu altyapıları çeşitli siber saldırılara daha açık hale gelmiştir. Özellikle brute-force, dağıtık hizmet engelleme (DDoS) ve botnet kaynaklı saldırılar, klasik imza veya kural tabanlı güvenlik yaklaşımları ile yeterince etkin biçimde tespit edilememektedir. Bu nedenle davranışsal analiz ve makine öğrenmesi yöntemlerinin güvenlik sistemlerine entegre edilmesi gerekmektedir.

Bu proje, log tabanlı veri analizi üzerinden çoklu saldırı türlerini kapsayan, hedef odaklı ve durum (stateful) analiz yapabilen bir sistem geliştirmeyi hedeflemektedir.

## 2. Yöntem

Sistem dört temel modülden oluşmaktadır:

### 2.1 Log Toplama ve Standardizasyon
Farklı servislerden ve bulut sunucularından elde edilen log verileri toplanmakta, JSON/CSV formatına dönüştürülmekte ve analiz için standart hale getirilmektedir. Bu aşamada çoklu servis korelasyonu için veri hazırlığı yapılmaktadır.

### 2.2 Makine Öğrenmesi ve Korelasyon Motoru
Hazırlanan veriler üzerinde eğitilmiş makine öğrenmesi modelleri kullanılmaktadır. Sliding window yaklaşımı ile zaman bazlı analiz yapılmakta ve hedef servis odaklı risk skoru hesaplanmaktadır. Korelasyon teknikleri ile tekil olaylar yerine davranış örüntüleri değerlendirilmektedir.

### 2.3 Otonom Yanıt Mekanizması
Yüksek risk skoru tespit edildiğinde ilgili IP adresleri otomatik olarak engellenmektedir. Beyaz liste (whitelist) ve geri alma (rollback) mekanizmaları ile yanlış pozitif sonuçların etkisi azaltılmaktadır.

### 2.4 Raporlama ve İzleme
Tespit edilen saldırılar hakkında detaylı bilgiler kullanıcıya bildirilmekte ve saldırı türü, hedef servis, süre ve engellenen IP bilgileri raporlanmaktadır. Bu amaçla web arayüzü veya mesajlaşma tabanlı bildirim sistemi kullanılabilmektedir.

## 3. Beklenen Sonuçlar

Geliştirilecek sistemin, çoklu saldırı türlerini tek bir çatı altında tespit edebilmesi, yanlış pozitif oranını azaltması ve otomatik müdahale mekanizması sayesinde sunucu güvenliğini artırması beklenmektedir. Ayrıca sistemin modüler yapısı sayesinde ölçeklenebilir ve genişletilebilir bir mimari sunması hedeflenmektedir.

## 4. Sonuç

Bu çalışma, makine öğrenmesi tekniklerini bulut güvenliği ile entegre ederek davranışsal analiz temelli, otonom ve hedef odaklı bir saldırı tespit sistemi ortaya koymayı amaçlamaktadır. Geliştirilen yaklaşım, geleneksel yöntemlere kıyasla daha kapsamlı ve uyarlanabilir bir güvenlik çözümü sunmaktadır.
