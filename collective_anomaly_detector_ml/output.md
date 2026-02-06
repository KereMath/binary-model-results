# Collective Anomaly Detector ML

## Gorev
**Binary Classification:** Collective Anomaly vs Not Collective Anomaly

## En Iyi Model
| Metrik | Deger |
|--------|-------|
| Model | LightGBM |
| Validation F1 | 0.8958 |
| Test F1 | 0.8992 |
| Test Accuracy | 0.8953 |

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
| Train | 6,904 (3,454 + 3,450) |
| Validation | 768 (384 + 384) |
| Test | 1,919 |

## Egitim Suresi
| Model | Sure (saniye) |
|-------|---------------|
| LightGBM | 0.362 |
| XGBoost | 0.503 |
| MLP | 0.954 |

## Tum Model Karsilastirmasi
| Model | Val Accuracy | Val F1 | Val Precision | Val Recall |
|-------|--------------|--------|---------------|------------|
| **LightGBM** | **0.8906** | **0.8958** | **0.8555** | **0.9401** |
| XGBoost | 0.8867 | 0.8917 | 0.8544 | 0.9323 |
| MLP | 0.8841 | 0.8916 | 0.8375 | 0.9531 |
