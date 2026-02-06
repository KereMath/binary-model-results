# Binary Detector'lar - Ozet Tablosu

## Tum Detector'larin Karsilastirmasi (F1 Skoruna Gore Siralanmis)

| # | Detector | En Iyi Model | Val F1 | Test F1 | Test Acc | Ozellik | Pencere |
|---|----------|--------------|--------|---------|----------|---------|---------|
| 1 | **Contextual Anomaly** | LightGBM | 1.0000 | 1.0000 | 1.0000 | TSFresh 777 | No Window |
| 2 | **Deterministic Trend** | LightGBM | 0.9845 | 0.9845 | 0.9844 | TSFresh 777 | No Window |
| 3 | **Stochastic Trend** | LightGBM | 0.9775 | 0.9733 | 0.9734 | TSFresh 777 | No Window |
| 4 | **Trend Shift** | LightGBM | 0.9574 | 0.9526 | 0.9526 | TSFresh 777 | No Window |
| 5 | **Stationarity** | MLP | 0.9410 | - | 0.9412 | Sliding Window | L/5 |
| 6 | **Volatility** | MLP | 0.9266 | 0.9046 | 0.9004 | TSFresh 777 | No Window |
| 7 | **Variance Shift (new)** | XGBoost | 0.9196 | 0.9125 | 0.9108 | TSFresh 777 | No Window |
| 8 | **Mean Shift** | LightGBM | 0.9111 | 0.9068 | 0.9049 | TSFresh 777 | L/5 |
| 9 | **Collective Anomaly** | LightGBM | 0.8958 | 0.8992 | 0.8953 | TSFresh 777 | No Window |
| 10 | **Mean Shift (new)** | LightGBM | 0.8964 | 0.8958 | 0.8936 | TSFresh 777 | No Window |
| 11 | **Point Anomaly** | LightGBM | 0.8928 | 0.8937 | 0.8921 | TSFresh 777 | No Window |

---

## Model Dagilimi

| Model | Kac Detector'da En Iyi | Detector'lar |
|-------|------------------------|--------------|
| LightGBM | 8 | Contextual, Deterministic, Stochastic, Trend Shift, Mean Shift, Collective, Meannew, Point |
| MLP | 2 | Stationarity, Volatility |
| XGBoost | 1 | Variancenew |

---

## Ortak Ozellikler

### Ozellik Cikarma
- **TSFresh "Efficient" Parameter Set:** 777 istatistiksel, spektral ve temporal ozellik
- Tum zaman serisi tek parca olarak islenir (no window)
- Sadece Stationarity ve Mean Shift detector'lari sliding window (L/5) kullanir

### Egitim Stratejisi
- Binary classification (X vs Not-X)
- 3 model karsilastirmasi: LightGBM, XGBoost, MLP
- Train/Validation/Test split
- En iyi model validation F1 skoruna gore secilir

### Veri Seti
- Her sinif icin ~3,450 pozitif ornek
- Dengeli veri seti (50/50)
- Toplam ~7,000 train + ~770 val + ~1,900 test

---

## Performans Analizi

### En Kolay Tespit Edilen Siniflar (F1 > 0.95)
1. Contextual Anomaly (F1 = 1.0000) - Mukemmel ayrim
2. Deterministic Trend (F1 = 0.9845)
3. Stochastic Trend (F1 = 0.9775)
4. Trend Shift (F1 = 0.9574)

### Orta Zorlukta Siniflar (0.90 < F1 < 0.95)
5. Stationarity (F1 = 0.9410)
6. Volatility (F1 = 0.9266)
7. Variance Shift (F1 = 0.9196)
8. Mean Shift (F1 = 0.9111)

### En Zor Tespit Edilen Siniflar (F1 < 0.90)
9. Collective Anomaly (F1 = 0.8958)
10. Mean Shift new (F1 = 0.8964)
11. Point Anomaly (F1 = 0.8928)

---

## Hocanin Makalesi Icin Kullanilan Detector'lar

Hocanin makalesinde (tez.tex) dogrudan kullanilan detector'lar:
1. **Stationarity Detector** - Table 4'te (F1 = 0.9410, MLP)
2. **Mean Shift Detector** - Table 5'te (F1 = 0.9111, LightGBM)

Diger detector'lar TSFresh Ensemble sisteminde (Table X) 9-class classification icin kullanilmistir.

---

## Klasor Yapisi

```
gerekenler/
├── SUMMARY.md (bu dosya)
├── contextual_anomaly_detector_ml/
│   ├── best_model_info.json
│   ├── training_results.json
│   └── output.md
├── deterministic_trend_detector_ml/
│   ├── best_model_info.json
│   ├── training_results.json
│   └── output.md
├── stochastic_trend_detector_ml/
│   ├── best_model_info.json
│   ├── training_results.json
│   └── output.md
├── trend_shift_detector_ml/
│   ├── best_model_info.json
│   ├── training_results.json
│   └── output.md
├── volatility_detector_ml/
│   ├── best_model_info.json
│   ├── training_results.json
│   └── output.md
├── variancenew_detector_ml/
│   ├── best_model_info.json
│   ├── training_results.json
│   └── output.md
├── meannew_detector_ml/
│   ├── best_model_info.json
│   ├── training_results.json
│   └── output.md
├── collective_anomaly_detector_ml/
│   ├── best_model_info.json
│   ├── training_results.json
│   └── output.md
├── point_anomaly_detector_ml/
│   ├── best_model_info.json
│   ├── training_results.json
│   └── output.md
├── mean_shift_detector_ml/
│   ├── best_model_info.json
│   ├── training_results.json
│   └── output.md
└── stationary_detector_ml/
    ├── extracted_results.json
    └── output.md
```
