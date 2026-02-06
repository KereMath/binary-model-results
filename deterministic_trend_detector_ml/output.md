# Deterministic Trend Detector ML

## Gorev
**Binary Classification:** Deterministic Trend vs Not Deterministic Trend

## En Iyi Model
| Metrik | Deger |
|--------|-------|
| Model | LightGBM |
| Validation F1 | 0.9845 |
| Test F1 | 0.9845 |
| Test Accuracy | 0.9844 |

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
| Train | 6,903 (3,451 + 3,452) |
| Validation | 768 (384 + 384) |
| Test | 1,918 |

## Egitim Suresi
| Model | Sure (saniye) |
|-------|---------------|
| LightGBM | 0.225 |
| XGBoost | 0.304 |
| MLP | 1.057 |

## Tum Model Karsilastirmasi
| Model | Val Accuracy | Val F1 | Val Precision | Val Recall |
|-------|--------------|--------|---------------|------------|
| **LightGBM** | **0.9844** | **0.9845** | **0.9769** | **0.9922** |
| XGBoost | 0.9805 | 0.9807 | 0.9695 | 0.9922 |
| MLP | 0.8919 | 0.8829 | 0.9631 | 0.8151 |
