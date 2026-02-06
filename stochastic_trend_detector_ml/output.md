# Stochastic Trend Detector ML

## Gorev
**Binary Classification:** Stochastic Trend vs Not Stochastic Trend

## En Iyi Model
| Metrik | Deger |
|--------|-------|
| Model | LightGBM |
| Validation F1 | 0.9775 |
| Test F1 | 0.9733 |
| Test Accuracy | 0.9734 |

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
| Train | 6,907 (3,454 + 3,453) |
| Validation | 768 (384 + 384) |
| Test | 1,919 |

## Egitim Suresi
| Model | Sure (saniye) |
|-------|---------------|
| LightGBM | 0.247 |
| XGBoost | 0.363 |
| MLP | 0.910 |

## Tum Model Karsilastirmasi
| Model | Val Accuracy | Val F1 | Val Precision | Val Recall |
|-------|--------------|--------|---------------|------------|
| **LightGBM** | **0.9779** | **0.9775** | **0.9946** | **0.9609** |
| XGBoost | 0.9740 | 0.9737 | 0.9840 | 0.9635 |
| MLP | 0.9622 | 0.9617 | 0.9759 | 0.9479 |
