# syslog_linkedlist.c

Linux Syslog Management with Linked List
Bu proje, Linux işletim sistemindeki Syslog (Sistem Günlükleri) mekanizmasını anlamak ve bu verileri Bağlı Liste (Linked List) veri yapısı kullanarak dinamik bir şekilde yönetmek amacıyla geliştirilmiştir.

📌 Proje Hakkında
Syslog, bir işletim sisteminde arka planda çalışan servislerin, çekirdek olaylarının ve uygulama hatalarının kronolojik olarak kaydedildiği bir sistemdir. Bu projede:

Log kayıtları için özel bir struct yapısı oluşturulmuştur.

Veriler, bellek verimliliği sağlamak adına Tek Yönlü Bağlı Liste (Singly Linked List) üzerinde tutulmuştur.

Gerçek zamanlı sistem saati kullanılarak her log kaydına otomatik "Zaman Damgası (Timestamp)" eklenmiştir.

🛠 Kullanılan Teknolojiler ve Veri Yapıları
Dil: C Programlama Dili

Veri Yapısı: Tek Yönlü Bağlı Liste (Singly Linked List)

Bellek Yönetimi: Dinamik Bellek Tahsisi (malloc, free)

Kütüphaneler: <stdio.h>, <stdlib.h>, <string.h>, <time.h>

🚀 Neden Bağlı Liste Tercih Edildi?
Syslog verileri için bağlı liste seçilmesinin temel teknik nedenleri şunlardır:

Dinamik Boyut: Sistem günlüğü kayıtlarının sayısı önceden kestirilemez. Bağlı listeler, çalışma zamanında (runtime) ihtiyaç duyulduğu kadar bellek ayırarak bellek israfını önler.

Hızlı Ekleme (O(1)): Yeni loglar her zaman listenin sonuna eklenir. Tail pointer kullanımıyla veya basit bir iterasyonla verimli bir şekilde kronolojik sıralama korunur.

Log Rotation (Silme Kolaylığı): En eski logların silinmesi gerektiğinde (FIFO mantığı), listenin başındaki düğümü silmek dizilere göre çok daha performanslıdır.

📂 Kod Yapısı ve Fonksiyonlar
Proje içerisinde kullanılan temel bileşenler şunlardır:

SyslogNode: Log bilgilerini (Zaman, Öncelik, Mesaj) ve bir sonraki düğüm adresini tutan ana yapı.

createLogNode(): Bellekte yeni bir alan ayırarak log verilerini hazırlar.

addLogToList(): Hazırlanan logu listenin sonuna (kronolojik sıraya) ekler.

displayLogs(): Tüm listeyi kullanıcıya anlamlı bir tablo formatında sunar.

💻 Çalıştırma Talimatları
Depoyu bilgisayarınıza clone'layın:

Bash
git clone https://github.com/kullaniciadi/repo-adi.git
C dosyasını derleyin:

Bash
gcc main.c -o syslog_app
Uygulamayı çalıştırın:

Bash
./syslog_app

Program yeni log kayıtları oluşturur ve bu kayıtları bağlı listeye ekler. Daha sonra tüm log kayıtları ekrana yazdırılır.

## Kullanılan Dil

C Programming Language
