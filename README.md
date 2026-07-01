# Spor Analitiği — Açık Futbol Lig İstatistikleri

İngiltere Premier Lig'in **2020-21 → 2023-24** sezonlarına ait açık maç istatistiklerini
kullanan uçtan uca bir veri bilimi dönem projesi: veri yükleme, temizleme, keşifsel veri
analizi (EDA), araştırma sorularının yanıtlanması ve basit bir sınıflandırma modeli.

## 👥 Proje Ekibi

| Öğrenci Numarası | Adı Soyadı     |
| ---------------- | -------------- |
| 1306240091       | Efe Ünlü       |
| 1306240033       | Mert Kurthasan |

## 🎯 Amaç ve Araştırma Soruları

Maç içi istatistiklerin (şut, isabetli şut, korner, faul, kart, ilk yarı skoru) maç
sonucuyla ilişkisini incelemek ve maç sonucunu tahmin eden yorumlanabilir bir model kurmak.

1. **S1.** Ev sahibi avantajı istatistiksel olarak gözlemlenebilir mi?
2. **S2.** Hangi maç içi istatistik, gol farkıyla (maç üstünlüğü) en güçlü ilişkilidir?
3. **S3.** İlk yarıyı önde kapatmak maç sonucunu ne ölçüde belirler?

## 📁 Klasör Yapısı

```
VeriBilimiProje/
├── README.md                      # Bu dosya
├── requirements.txt               # Gerekli Python kütüphaneleri
├── prompt_gunlugu.md              # Geliştirme sürecinde kullanılan promptlar
├── data/                          # Ham veri (CSV) + veri sözlüğü
│   ├── season-2020-2021.csv
│   ├── season-2021-2022.csv
│   ├── season-2022-2023.csv
│   ├── season-2023-2024.csv
│   └── VERI_SOZLUGU.md
├── notebook/
│   └── spor_analitigi.ipynb       # Tüm analiz adımlarını içeren çalışır notebook
└── rapor/
    └── rapor.pdf                  # Kısa rapor (3-5 sayfa)
```

## 🚀 Projeyi Çalıştırma

**Gereksinim:** Python 3.9+ (geliştirme Python 3.13 ile yapılmıştır).

```bash
# 1) (Önerilir) Sanal ortam oluşturun
python -m venv venv
# Windows:
venv\Scripts\activate
# macOS / Linux:
source venv/bin/activate

# 2) Kütüphaneleri kurun
pip install -r requirements.txt

# 3) Notebook'u açın ve baştan sona çalıştırın
jupyter notebook notebook/spor_analitigi.ipynb
```

Notebook, veri dosyalarını `data/` klasöründen otomatik bulur; baştan sona
"Run All" ile çalıştırıldığında tüm grafikleri ve model sonuçlarını üretir. İnternet
bağlantısı gerektirmez (veriler depoda hazırdır).

> Raporu (`rapor/rapor.pdf`) yeniden üretmek isteğe bağlıdır ve ek olarak `reportlab`
> kütüphanesini gerektirir.

## 📦 Kullanılan Kütüphaneler

| Kütüphane | Kullanım amacı |
| --------- | -------------- |
| pandas | Veri yükleme, temizleme, tablo işlemleri |
| numpy | Sayısal işlemler |
| matplotlib | Görselleştirme altyapısı |
| seaborn | İstatistiksel grafikler (histogram, kutu, ısı haritası) |
| scipy | İstatistiksel hipotez testi (binom testi) |
| scikit-learn | Modelleme (Lojistik Regresyon), ölçekleme, eksik veri doldurma, metrikler |
| jupyter / notebook | Notebook ortamı |
| reportlab | (Opsiyonel) PDF rapor üretimi |

## 📊 Veri Kaynağı ve Lisansı

- **Veri seti:** İngiltere Premier Lig maç istatistikleri (4 sezon, 1520 maç).
- **Kaynak:** [datasets/football-datasets](https://github.com/datasets/football-datasets)
  (datahub.io) — veriler orijinal olarak
  [football-data.co.uk](https://www.football-data.co.uk/) sitesinden derlenmiştir.
- **Lisans:** [Open Data Commons Public Domain Dedication and License (PDDL) v1.0](https://opendatacommons.org/licenses/pddl/1-0/)

Sütun açıklamaları için bkz. [`data/VERI_SOZLUGU.md`](data/VERI_SOZLUGU.md).

## 🔑 Özet Bulgular

- **Ev sahibi avantajı** net ve **istatistiksel olarak anlamlı** (binom testi, p≈1.1×10⁻⁵): maçların %43.8'i ev galibiyeti, %33.8'i deplasman, %22.4'ü beraberlik.
- Gol farkıyla en güçlü maç içi ilişki **isabetli şut farkındadır** (r≈0.66); kartlar negatif ilişkili.
- İlk yarıyı önde kapatan ev sahibi maçların **%78'ini** kazanıyor.
- Lojistik regresyon test doğruluğu **%64.1** (taban çizgisi %43.8); beraberlikler en zor tahmin edilen sınıf.

Ayrıntılar için `notebook/spor_analitigi.ipynb` ve `rapor/rapor.pdf` dosyalarına bakınız.
