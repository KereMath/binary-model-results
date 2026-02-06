# Trend Shift Detector ML

## Gorev
**Binary Classification:** Trend Shift vs Not Trend Shift

## En Iyi Model
| Metrik | Deger |
|--------|-------|
| Model | LightGBM |
| Validation F1 | 0.9574 |
| Test F1 | 0.9526 |
| Test Accuracy | 0.9526 |

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
| Train | 6,901 (3,450 + 3,451) |
| Validation | 767 (384 + 383) |
| Test | 1,918 |

## Egitim Suresi
| Model | Sure (saniye) |
|-------|---------------|
| LightGBM | 0.266 |
| XGBoost | 0.380 |
| MLP | 0.942 |

## Tum Model Karsilastirmasi
| Model | Val Accuracy | Val F1 | Val Precision | Val Recall |
|-------|--------------|--------|---------------|------------|
| **LightGBM** | **0.9570** | **0.9574** | **0.9464** | **0.9687** |
| XGBoost | 0.9531 | 0.9534 | 0.9460 | 0.9608 |
| MLP | 0.9465 | 0.9474 | 0.9318 | 0.9634 |
