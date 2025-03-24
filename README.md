# Metro_Simulation
 # Proje Hakkında

Bu proje, bir metro ağının en az aktarma veya en hızlı rota ile geçişini hesaplamak için geliştirilmiştir. Kullanıcı, bu simülasyon ile iki istasyon arasındaki en kısa süreli rotayı veya en az aktarmalı rotayı bulabilir.

## İçindekiler
- [Kullanılan Teknolojiler ve Kütüphaneler](#Kullanılan-Teknolojiler-ve-Kütüphaneler)
- [Algoritmaların Çalışma Mantığı](#Algoritmaların-Çalışma-Mantığı)
- [Neden Bu Algoritmalar Kullanıldı?](#Neden-Bu-Algoritmalar-Kullanıldı?)
- [Örnek Kullanım ve Test Sonuçları](#Örnek-Kullanım-ve-Test-Sonuçları)
- [Test Senaryoları](#Test-Senaryoları)
- [Projeyi Geliştirme Fikirleri](#Projeyi-Geliştirme-Fikirleri)

 # Kullanılan Teknolojiler ve Kütüphaneler

Projede aşağıdaki Python kütüphaneleri kullanılmıştır:

collections.defaultdict: Metro hatlarını organize etmek için kullanıldı.

collections.deque: BFS algoritmasında kuyruk yapısı olarak kullanıldı.

heapq: A* algoritmasında öncelikli kuyruk yapısı olarak kullanıldı.

typing: Tip tanımlamaları için kullanıldı.

# Algoritmaların Çalışma Mantığı

- 1. BFS (Breadth-First Search) Algoritması

BFS, bir noktadan başlayarak en kısa yolun bulunması için kullanılan bir algoritmadır. Bu projede en az aktarmalı rotayı bulmak için kullanılmıştır.

- Nasıl çalışır?

Bir kuyruk yapısı kullanarak istasyonlar seviyesi seviyesine aranır.

Her adımda, mevcut istasyonun komşu istasyonları kuyruğa eklenir.

Hedef istasyona ulaşıldığında rota döndürülür.

- 2. A* (A-Star) Algoritması

A* algoritması, en kısa süreli rotayı bulmak için kullanılan bir en iyi öncelikli arama algoritmasıdır.

- Nasıl çalışır?

Bir öncelikli kuyruk (heapq) kullanılarak, en düşük maliyetli (en hızlı) rota hesaplanır.

Her istasyonun komşuları incelenerek, toplam süreye göre en iyi yol bulunur.

En hızlı rota bulunduğunda döndürülür.

 # Neden Bu Algoritmalar Kullanıldı?

BFS, en az aktarmalı rotayı bulmada en etkili algoritmalardan biridir.

A*, en hızlı rotayı bulmada etkili ve verimli bir algoritmadır.

# Örnek Kullanım ve Test Sonuçları

Projede aşağıdaki metro hatları ve istasyonlar tanımlanmıştır:

Kırmızı Hat: Kızılay, Ulus, Demetevler, OSB

Mavi Hat: AŞTİ, Kızılay, Sıhhiye, Gar

Turuncu Hat: Batıkent, Demetevler, Gar, Keçiören

 # Test Senaryoları:

1. AŞTİ'den OSB'ye

En az aktarmalı rota: AŞTİ -> Kızılay -> Ulus -> Demetevler -> OSB
En hızlı rota (Dakika): AŞTİ -> Kızılay -> Demetevler -> OSB (Toplam: 15 dk)

2. Batıkent'ten Keçiören'e

En az aktarmalı rota: Batıkent -> Demetevler -> Gar -> Keçiören
En hızlı rota (Dakika): Batıkent -> Demetevler -> Gar -> Keçiören (Toplam: 21 dk)

 # Projeyi Geliştirme Fikirleri

Daha Gelişmiş Heuristikler: A* algoritmasında mesafe ve süre dışında yoğunluk verileri de eklenerek en iyi rota bulunabilir.

Gerçek Zamanlı Veriler: Metro duraklarının yoğunluk ve tren hareket saatleri eklendiğinde daha hassas hesaplamalar yapılabilir.

Arayüz Entegrasyonu: Projeye bir grafik arayüz eklenerek kullanıcı dostu bir hale getirilebilir.
