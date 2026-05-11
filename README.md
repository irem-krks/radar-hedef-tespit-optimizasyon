# Radar Hedef Tespit Sistemi — Evrimsel Optimizasyon

## Proje Hakkında
Bu projede bir radar sisteminin hedef tespitinde kullandığı **karar eşiği**, evrimsel optimizasyon yöntemleriyle belirlenmiştir. Amaç, yanlış alarm (false positive) ve kaçırma (false negative) hatalarını dengeleyen optimal eşik değerini bulmaktır.

## Problem Tanımı
Radar sistemleri hedef tespitinde iki temel hatayla karşılaşır:

| Hata Türü | Açıklama |
|-----------|----------|
| **Yanlış Alarm** | Hedef yokken "var" demek |
| **Kaçırma** | Hedef varken "yok" demek |

Bu iki hata birbirine bağlıdır — birini azaltmak diğerini artırır. Optimal eşik değeri bu dengeyi en iyi kuran noktadır.

## Kullanılan Yöntemler
| Yöntem | Açıklama |
|--------|----------|
| **Genetik Algoritma (GA)** | PyGAD kütüphanesi ile evrimsel arama |
| **Diferansiyel Evrim (DE)** | SciPy ile sürekli uzayda optimizasyon |

## Sinyal Modeli
Radar gürültüsü Gaussian dağılımla modellendi (Merkezi Limit Teoremi gereği):

- Hedef YOK: X ~ N(0, σ²)
- Hedef VAR: X ~ N(μ, σ²)
- SNR = μ/σ = 2.0 (orta zorluk senaryosu)

Gerçek radar verisi gizlilik sınıflandırması nedeniyle kamuya açık olmadığından **Monte Carlo simülasyonu** ile sentetik veri üretilmiştir.

## Kullanılan Teknolojiler
- Python 3
- NumPy, SciPy
- Matplotlib
- PyGAD

