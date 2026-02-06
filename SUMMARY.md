# Binary Detector'lar - Ozet Tablosu

## Tum Detector'larin Karsilastirmasi (F1 Skoruna Gore Siralanmis)

| # | Detector | En Iyi Model | Val F1 | Test F1 | Test Acc | Veri Kaynagi |
|---|----------|--------------|--------|---------|----------|--------------|
| 1 | **Contextual Anomaly** | LightGBM | 1.0000 | 1.0000 | 1.0000 | Generated Data |
| 2 | **Deterministic Trend** | LightGBM | 0.9845 | 0.9845 | 0.9844 | Generated Data |
| 3 | **Stochastic Trend** | LightGBM | 0.9775 | 0.9733 | 0.9734 | Generated Data |
| 4 | **Trend Shift** | LightGBM | 0.9574 | 0.9526 | 0.9526 | Generated Data |
| 5 | **Stationarity** | MLP | 0.9410 | - | 0.9412 | LASTDATA |
| 6 | **Volatility** | MLP | 0.9266 | 0.9046 | 0.9004 | Generated Data |
| 7 | **Variance Shift (new)** | XGBoost | 0.9196 | 0.9125 | 0.9108 | Generated Data |
| 8 | **Mean Shift** | LightGBM | 0.9111 | 0.9068 | 0.9049 | Generated Data |
| 9 | **Collective Anomaly** | LightGBM | 0.8958 | 0.8992 | 0.8953 | Generated Data |
| 10 | **Mean Shift (new)** | LightGBM | 0.8964 | 0.8958 | 0.8936 | Generated Data |
| 11 | **Point Anomaly** | LightGBM | 0.8928 | 0.8937 | 0.8921 | Generated Data |

---

## Veri Kaynaklari

| Kaynak | Aciklama | Kullanan Detector'lar |
|--------|----------|----------------------|
| **Generated Data** | Sentetik uretilmis zaman serileri | 10 detector |
| **LASTDATA** | Farkli dataset | Sadece Stationarity |

---

## Ozellik Cikarma (Tum Detector'lar Icin Ayni)

- **TSFresh:** Kullanilmadi
- **Windowing:** L/5 sliding window (tum detector'larda)
- **Ozellik Sayisi:** ~38 custom istatistiksel ozellik

### Cikarilan Ozellikler
```
Basic stats: mean, std, var, min, max, range
Percentiles: q25, median, q75, iqr
Shape stats: skewness, kurtosis, cv
Differencing: diff1_mean, diff1_std, diff1_var, diff2_mean, diff2_std, diff2_var
Rolling window: rolling_mean_std, rolling_mean_range, max_rolling_mean_change,
                mean_rolling_mean_change, rolling_std_mean, rolling_std_std
Half comparison: half_mean_diff, half_std_diff, half_mean_ratio
Autocorrelation: autocorr_lag1, autocorr_lag10
Other: num_peaks, zero_crossing_rate
```

---

## Model Dagilimi

| Model | Kac Detector'da En Iyi | Detector'lar |
|-------|------------------------|--------------|
| LightGBM | 8 | Contextual, Deterministic, Stochastic, Trend Shift, Mean Shift, Collective, Meannew, Point |
| MLP | 2 | Stationarity, Volatility |
| XGBoost | 1 | Variancenew |

---

## Egitim Stratejisi

- Binary classification (X vs Not-X)
- 3 model karsilastirmasi: LightGBM, XGBoost, MLP
- Train/Validation/Test split
- En iyi model validation F1 skoruna gore secilir
- Dengeli veri seti (50/50)

---

## Veri Seti Boyutlari

| Detector | Train | Validation | Test | Toplam |
|----------|-------|------------|------|--------|
| **Stationarity** | - | - | - | 119,123 |
| **Mean Shift** | 67,200 | 9,600 | 19,200 | 96,000 |
| **Diger 9 detector** | ~6,900 | ~770 | ~1,900 | ~9,600 |

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
