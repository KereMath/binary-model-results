# Mean Shift Detector ML (meannew)

## Gorev
**Binary Classification:** Mean Shift vs Not Mean Shift

## En Iyi Model
| Metrik | Deger |
|--------|-------|
| Model | LightGBM |
| Validation F1 | 0.8964 |
| Test F1 | 0.8958 |
| Test Accuracy | 0.8936 |

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
| LightGBM | 0.233 |
| XGBoost | 0.501 |
| MLP | 0.578 |

## Tum Model Karsilastirmasi
| Model | Val Accuracy | Val F1 | Val Precision | Val Recall |
|-------|--------------|--------|---------------|------------|
| **LightGBM** | **0.8957** | **0.8964** | **0.8895** | **0.9034** |
| XGBoost | 0.8918 | 0.8943 | 0.8731 | 0.9164 |
| MLP | 0.8761 | 0.8777 | 0.8655 | 0.8903 |
