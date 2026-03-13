
🐧 Linux Syslog Management Simulation with Linked Lists
Bu çalışma, Linux işletim sisteminin kalbi sayılan Syslog mekanizmasını, bilgisayar bilimlerinin temel taşlarından biri olan Bağlı Liste (Linked List) veri yapısıyla simüle etmek amacıyla geliştirilmiştir. Proje, hem sistem programlama mantığını hem de dinamik bellek yönetimini bir araya getirmektedir.

🛠 Teknik Analiz ve Derinlemesine Tasarım
1. Syslog Mekanizması ve Operasyonel Önemi
Syslog, Unix tabanlı sistemlerde tüm olay kayıtlarını (event logs) standartlaştıran bir protokoldür.

Merkezi Yönetim: Farklı servislerin (Apache, SSH, Kernel vb.) kendi günlüklerini tek bir standart formatta üretmesini sağlar.

Analiz Kapasitesi: Sistem yöneticileri, /var/log altındaki bu verileri analiz ederek donanım arızalarını veya siber saldırı girişimlerini henüz büyümeden tespit edebilir.

2. Verilerin Bağlı Liste Yapısıyla Modellenmesi
Syslog kayıtları statik bir yapıya sahip değildir; sistem çalıştığı sürece sürekli akar. Bu akışı modellemek için:

Her bir günlük girdisi, bellekte birbirinden bağımsız ancak birbirine işaretçilerle (pointers) bağlı düğümler (nodes) olarak tutulur.

Bu model, verilerin bellekte ardışık olma zorunluluğunu ortadan kaldırarak esneklik sağlar.

3. Seçilen Veri Yapısı: Tek Yönlü Bağlı Liste (Singly Linked List)
Projenin temelinde Tek Yönlü Bağlı Liste yapısı kullanılmıştır. Bu seçim rastgele değil, syslog verilerinin karakteristiğine uygun olarak yapılmıştır.

4. Teknik Tercih Gerekçeleri ve Syslog İlişkisi
Dinamik Ölçeklenebilirlik: Sabit boyutlu bir dizi (array) kullanılsaydı, log sayısı dizinin kapasitesini aştığında sistem çökerdi. Bağlı liste ile RAM elverdiği sürece sınırsız sayıda log tutulabilir.

Düşük Karmaşıklıklı Ekleme (O(n) veya O(1)): Yeni loglar kronolojik olarak her zaman listenin sonuna eklenir. Bu, syslog'un zaman akışına tam uyum sağlar.

Bellek Optimizasyonu: Sadece aktif olan log kayıtları için bellek tüketilir. Boş dizi hücreleri gibi gereksiz yer kaplayan alanlar oluşmaz.

Log Rotation (Eski Kayıtların Yönetimi): Linux sistemlerde yer açmak için en eski loglar silinir. Bağlı listede listenin en başından (Head) düğüm silmek, dizilerdeki gibi tüm elemanları kaydırma zahmetine girmeden anında gerçekleştirilir.

💻 Yazılım Mimarisi ve Fonksiyon Detayları
Kod içerisindeki tüm bileşenler, profesyonel standartlarda isimlendirilmiştir:

struct SyslogNode:

timestamp: Logun oluşturulma zamanını saniye hassasiyetinde tutar.

priority: Mesajın önem derecesini (INFO, WARNING, ERROR, CRITICAL) belirler.

message: Gerçek olay verisini içeren metin alanıdır.

createLogNode(): Yeni bir log girişi için bellekten (malloc) güvenli bir şekilde yer ayırır ve sistem saatini düğüme enjekte eder.

addLogToList(): Mevcut listenin sonuna giderek yeni düğümü zincire dahil eder.

displayLogs(): Tüm listeyi iteratif bir şekilde gezerek kullanıcıya okunabilir bir rapor sunar.

🚀 Çalıştırma ve Test
Bash
./syslog_manager
