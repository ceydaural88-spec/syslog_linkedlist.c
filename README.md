# Linux Syslog Bilgilerinin Bağlı Liste ile Gösterilmesi

Bu proje Linux işletim sisteminde kullanılan **Syslog (okunuşu: sis-log)** mekanizmasını incelemek ve syslog verilerini **Doubly Linked List (okunuşu: dabıl linkt list)** veri yapısı ile saklayan bir uygulama geliştirmek amacıyla hazırlanmıştır.

---

## Syslog Nedir?

Syslog, Linux ve Unix tabanlı sistemlerde kullanılan bir **sistem günlükleme mekanizmasıdır**. Sistem olaylarını kayıt altına alır. Örneğin:

- kullanıcı girişleri  
- sistem hataları  
- servis başlatma ve durdurma  
- ağ bağlantıları  

bu olaylar **log (okunuşu: log)** kayıtları olarak tutulur.

---

## Kullanılan Veri Yapısı

Bu projede Syslog kayıtlarını saklamak için **Doubly Linked List** veri yapısı kullanılmıştır.

Her düğüm (node, okunuşu: nod) şu bilgileri içerir:

- Zaman bilgisi  
- Log seviyesi (INFO – info, WARNING – warning, ERROR – eror)  
- Log mesajı  
- Önceki düğüm adresi  
- Sonraki düğüm adresi  

Doubly linked list sayesinde:

- Log kayıtları ileri ve geri gezilebilir  
- Log silme işlemleri kolaydır  
- Dinamik bellek kullanımı sağlanır  

---

#
