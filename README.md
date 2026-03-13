# Linux Syslog Bilgilerinin Bağlı Liste ile Gösterilmesi

Bu proje Linux işletim sisteminde kullanılan Syslog mekanizmasını incelemek ve syslog verilerini Doubly Linked List veri yapısı ile saklayan bir uygulama geliştirmek amacıyla hazırlanmıştır.

---

## Syslog Nedir?

Syslog, Linux ve Unix tabanlı sistemlerde kullanılan bir sistem günlükleme mekanizmasıdır. Sistem olaylarını kayıt altına alır. Örneğin:

- kullanıcı girişleri  
- sistem hataları  
- servis başlatma ve durdurma  
- ağ bağlantıları  

bu olaylar log kayıtları olarak tutulur.

---

## Kullanılan Veri Yapısı

Bu projede Syslog kayıtlarını saklamak için Doubly Linked List veri yapısı kullanılmıştır.

Her düğüm (node) şu bilgileri içerir:

- Zaman bilgisi  
- Log seviyesi (INFO, WARNING, ERROR)  
- Log mesajı  
- Önceki düğüm adresi  
- Sonraki düğüm adresi  

Doubly linked list sayesinde:

- Log kayıtları ileri ve geri gezilebilir  
- Log silme işlemleri kolaydır  
- Dinamik bellek kullanımı sağlanır  

---

## Program Kodu

```c
