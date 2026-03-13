# syslog_linkedlist.c
# Linux Syslog Bilgilerinin Bağlı Liste ile Gösterilmesi

Bu proje Linux işletim sisteminde kullanılan Syslog mekanizmasını incelemek ve syslog verilerini bağlı liste veri yapısı ile saklayan bir uygulama geliştirmek amacıyla hazırlanmıştır.

## Syslog Nedir?

Syslog Linux ve Unix tabanlı sistemlerde kullanılan bir sistem günlükleme mekanizmasıdır. Sistem olaylarını kayıt altına alır.

Örneğin:

- kullanıcı girişleri
- sistem hataları
- servis başlatma ve durdurma
- ağ bağlantıları

gibi olaylar log kayıtları olarak tutulur.

## Kullanılan Veri Yapısı

Bu projede Syslog kayıtlarını saklamak için **Doubly Linked List (Çift Bağlı Liste)** veri yapısı kullanılmıştır.

Her düğüm şu bilgileri içerir:

- zaman
- log seviyesi
- log mesajı
- önceki düğüm adresi
- sonraki düğüm adresi

## Neden Doubly Linked List?

Syslog kayıtları için çift bağlı liste tercih edilmiştir çünkü:

- log kayıtları ileri ve geri gezilebilir
- log silme işlemleri kolaydır
- dinamik bellek kullanımı sağlar
- büyük log sistemlerinde verimli çalışır

## Programın Çalışması

Program yeni log kayıtları oluşturur ve bu kayıtları bağlı listeye ekler. Daha sonra tüm log kayıtları ekrana yazdırılır.

## Kullanılan Dil

C Programming Language
