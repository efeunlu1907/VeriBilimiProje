# Prompt Günlüğü

Bu dosya, **Spor Analitiği — Açık Futbol Lig İstatistikleri** projesinin geliştirilmesi
sırasında yapay zekâ asistanıyla kullanılan önemli promptları kronolojik sırayla içerir.
Her promptun hangi proje adımında kullanıldığı belirtilmiştir.

| # | Adım | Prompt |
| - | ---- | ------ |
| 1 | Tema & planlama | "Veri bilimi dönem projesi için 'Spor analitiği — açık futbol lig istatistikleri' temasını seçtim. Teknik kapsam: veri temizleme, EDA (en az 4 görsel), en az 3 araştırma sorusu ve basit bir model. Bana uçtan uca bir proje planı çıkar." |
| 2 | Veri kaynağı | "Bu tema için ücretsiz ve açık lisanslı bir futbol lig veri seti öner. Şut, korner, kart gibi maç içi istatistikleri de içermeli ve lisansı net olmalı." |
| 3 | Veri kaynağı | "football-data.co.uk formatındaki (FTHG, FTAG, FTR, HS, HST, HC ... sütunlu) Premier Lig verisini GitHub'dan indirilebilecek bir kaynaktan bul ve lisansını doğrula." |
| 4 | Veri yükleme | "İndirdiğim 4 sezonluk CSV dosyasını (her biri ayrı dosya) pandas ile oku, her birine 'Season' sütunu ekleyip tek bir DataFrame'de birleştir." |
| 5 | Veri temizleme | "Birleştirilen veride eksik değerleri ve yinelenen satırları kontrol et; Date sütununu tarih tipine, gol/şut/kart sütunlarını tam sayıya dönüştür." |
| 6 | Veri temizleme | "Ev sahibi toplam şut (HS) sütununda IQR yöntemiyle aykırı değerleri tespit et. Bu değerleri silmeli miyim yoksa tutmalı mıyım, gerekçesiyle açıkla." |
| 7 | Özellik türetme | "Analiz ve modelleme için türetilmiş sütunlar oluştur: toplam gol, gol farkı, isabetli şut farkı, korner/faul/kart farkları ve ilk yarı gol farkı." |
| 8 | EDA | "En az 4 farklı görselleştirme türü kullanarak EDA yap: maç başına gol histogramı, maç sonucu çubuk grafiği, sonuca göre isabetli şut farkı kutu grafiği ve korelasyon ısı haritası. Kodu yorum satırlarıyla açıkla." |
| 9 | Araştırma sorusu 1 | "Ev sahibi avantajını veriyle göster: ev/deplasman galibiyet yüzdeleri ve ortalama gol sayılarını karşılaştır, sonucu yorumla." |
| 10 | Araştırma sorusu 2 | "Hangi maç içi istatistiğin gol farkıyla en güçlü ilişkili olduğunu korelasyonlarla bul. Kartların neden negatif korelasyon verdiğini açıkla." |
| 11 | Araştırma sorusu 3 | "İlk yarı sonucu (HTR) ile maç sonu sonucu (FTR) arasındaki koşullu olasılıkları çapraz tablo ve ısı haritasıyla incele." |
| 12 | Modelleme | "Maç sonucunu (H/D/A) maç içi istatistik farklarından tahmin eden bir Lojistik Regresyon modeli kur. Maç sonu gol sayılarını özellik olarak KULLANMA, çünkü sonucu doğrudan tanımlarlar. Eğitim/test ayrımı, ölçekleme ve bir taban çizgisi ekle." |
| 13 | Model değerlendirme | "Modeli doğruluk, sınıflandırma raporu ve karışıklık matrisiyle değerlendir. Beraberlik sınıfının neden zor tahmin edildiğini yorumla." |
| 14 | Yorum & sınırlamalar | "Bulguları futbol teması bağlamında yorumla; bu modelin maç öncesi tahmin için değil açıklama için kullanıldığını vurgulayan bir sınırlamalar bölümü yaz." |
| 15 | Teslim | "Tüm çalışmayı GitHub'a uygun şekilde paketle: çalışır notebook, 3-5 sayfalık PDF rapor, README (ekip bilgisi, çalıştırma talimatı, kütüphaneler, veri kaynağı ve lisansı) ve requirements.txt." |
| 16 | Kalite kontrol | "Notebook'u baştan sona çalıştırıp hiçbir hücrenin hata vermediğini ve tüm grafiklerin üretildiğini doğrula." |
| 17 | Eksik veri (ders referansı) | "Ders notebook'larını (Keşifsel Veri Analizi, İstatistik) referans alarak, veri tam olsa bile bir eksik veri senaryosu ekle: bir kopyada yapay eksik değer üret, tespit et ve ortalama/medyan/KNN ile doldurup RMSE ile karşılaştır. Çok karıştırma." |
| 18 | Çıkarımsal istatistik | "Ev sahibi avantajı sorusunu sadece betimsel değil, hipotez testiyle de yanıtla: kesin sonuçlu maçlarda binom testi kur, H0/H1 ve p-değerini raporla." |
| 19 | sklearn kullanımı | "Notebook'a, kullandığımız sklearn bileşenlerinin (train_test_split, StandardScaler, LogisticRegression, metrikler, imputer'lar) her birinin ne için kullanıldığını gösteren kısa bir kullanım tablosu ekle." |
| 20 | Rapor güncelleme | "Eklenen eksik veri senaryosunu ve hipotez testi sonucunu rapora işle; raporu 3-5 sayfa aralığında tut." |
| 21 | GitHub'a yayınlama | "Projeyi efeunlu1907 hesabında herkese açık bir GitHub deposu olarak oluştur, main dalına gönder; commit'lerde yapay zekâ ortak-yazar bilgisi bulunmasın." |
| 22 | Ekip bilgisi | "README ve rapora ekip bilgilerini ekle: Efe Ünlü (1306240091) ve Mert Kurthasan (1306240033)." |
| 23 | Sadeleştirme | "Teslim setini sadeleştir: rapor figürlerini ve gereksiz Markdown rapor kaynağını (PDF yeterli) ile ödev metnini (Proje.md) kaldır; sklearn bölümünü yalnızca kullanımı anlatacak biçimde sadeleştir." |

> Not: Promptlar, projenin gerçek geliştirme akışını yansıtacak şekilde özetlenmiştir.
> Üretilen tüm kod blokları gözden geçirilmiş ve anlaşılarak kullanılmıştır.
