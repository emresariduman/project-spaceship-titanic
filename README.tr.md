<p align="center"><a href="README.md"><b>🇬🇧 English</b></a></p>

# 🚀 Spaceship Titanic — ML Sınıflandırma Pipeline'ı

**EDA → Öznitelik Mühendisliği → 3 Model Karşılaştırması → Hiperparametre Optimizasyonu → Çapraz Doğrulama**

> **Ağustos 2022'de oluşturuldu** — yapay zeka araçlarının yaygınlaşmasından önce, tamamen manuel veri analizi, öznitelik mühendisliği ve model optimizasyonu ile geliştirilmiştir. **13. dönem [İTÜ SEM Veri Bilimi Uzmanlığı Sertifika Programı](https://itusem.itu.edu.tr/egitimler-ve-programlar/isletme-fakultesi-sertifika-programlari/data-science--uzmanligi-sertifika-programi)** bitirme projesidir.

Kaggle'ın Spaceship Titanic yarışması — yolcuların başka bir boyuta ışınlanıp ışınlanmadığını tahmin etmek için uzay gemisindeki lüks olanaklar, yolcu demografisi ve seyahat bilgilerini kullanan bir sınıflandırma problemi.

---

## Proje Akışı

1. **Keşifçi Veri Analizi** — Dağılımlar, korelasyon heatmap'i, eksik veri, hedef değişken dengesi
2. **Öznitelik Mühendisliği** — PassengerId, Cabin, Name ayrıştırma; yaş gruplama; eksik veri doldurma; etiket kodlama
3. **Modelleme** — 3 sınıflandırıcı, RandomizedSearchCV + 5-fold CV

## Sonuçlar

| Model | En İyi CV Doğruluğu | CV Std | Ezberleme |
|-------|:-------------------:|:------:|:---------:|
| **RandomForest** | **0.7974** | ±0.0070 | ✅ Düşük |
| **GradientBoosting** | **0.7972** | ±0.0097 | ⚠️ Hafif |
| **KNN** | 0.7796 | ±0.0054 | ❌ Yüksek |

## Kullanım

```bash
pip install -r requirements.txt
jupyter notebook "project-spaceship-titanic.ipynb"
```

## Dosya Yapısı

```
├── project-spaceship-titanic.ipynb   # Ana notebook
├── train.csv                          # Eğitim verisi
├── README.md
├── requirements.txt
└── .gitignore
```

## Araçlar

**Python:** pandas · numpy · scikit-learn · matplotlib · seaborn · jupyter
