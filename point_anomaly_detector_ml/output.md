# Point Anomaly Detector ML

## Gorev
**Binary Classification:** Point Anomaly vs Not Point Anomaly

## En Iyi Model
| Metrik | Deger |
|--------|-------|
| Model | LightGBM |
| Validation F1 | 0.8928 |
| Test F1 | 0.8937 |
| Test Accuracy | 0.8921 |

## Veri Kaynagi ve On Isleme
- **Ham Veri:** Generated Data (sentetik uretilmis zaman serileri)
- **Windowing:** L/5 sliding window uygulanmis
- **TSFresh:** Kullanilmadi
- **Ozellik Cikarma:** Custom extraction (~38 istatistiksel ozellik)
  - Basic stats: mean, std, var, min, max, range
  - Percentiles: q25, median, q75, iqr
  - Shape stats: skewness, kurtosis, cv
  - Differencing: diff1_mean/std/var, diff2_mean/std/var
  - Rolling window: rolling_mean_std, rolling_mean_range, rolling_std_mean
  - Half comparison: half_mean_diff, half_std_diff, half_mean_ratio
  - Autocorrelation: lag1, lag10
  - Other: num_peaks, zero_crossing_rate

## Veri Seti
| Set | Ornek Sayisi |
|-----|--------------|
| Train | 6,903 (3,452 + 3,451) |
| Validation | 767 (384 + 383) |
| Test | 1,918 |

## Egitim Suresi
| Model | Sure (saniye) |
|-------|---------------|
| LightGBM | 0.280 |
| XGBoost | 0.435 |
| MLP | 1.035 |

## Tum Model Karsilastirmasi
| Model | Val Accuracy | Val F1 | Val Precision | Val Recall |
|-------|--------------|--------|---------------|------------|
| **LightGBM** | **0.8892** | **0.8928** | **0.8634** | **0.9243** |
| XGBoost | 0.8840 | 0.8869 | 0.8639 | 0.9112 |
| MLP | 0.8696 | 0.8759 | 0.8345 | 0.9217 |
