# Variance Shift Detector ML (variancenew)

## Gorev
**Binary Classification:** Variance Shift vs Not Variance Shift

## En Iyi Model
| Metrik | Deger |
|--------|-------|
| Model | XGBoost |
| Validation F1 | 0.9196 |
| Test F1 | 0.9125 |
| Test Accuracy | 0.9108 |

## Ozellik Cikarma
- **Yontem:** TSFresh "Efficient" parameter set
- **Ozellik Sayisi:** 777 istatistiksel, spektral ve temporal ozellik
- **Pencere Stratejisi:** No Window (tum seri tek parca)

## Veri Seti
| Set | Ornek Sayisi |
|-----|--------------|
| Train | 6,901 (3,450 + 3,451) |
| Validation | 767 (384 + 383) |
| Test | 1,918 |

## Egitim Suresi
| Model | Sure (saniye) |
|-------|---------------|
| LightGBM | 0.275 |
| XGBoost | 0.419 |
| MLP | 0.448 |

## Tum Model Karsilastirmasi
| Model | Val Accuracy | Val F1 | Val Precision | Val Recall |
|-------|--------------|--------|---------------|------------|
| **XGBoost** | **0.9205** | **0.9196** | **0.9282** | **0.9112** |
| LightGBM | 0.9166 | 0.9147 | 0.9346 | 0.8956 |
| MLP | 0.9113 | 0.9101 | 0.9223 | 0.8982 |

## Not
Variance shift sinifi icin XGBoost modeli az farkla en iyi performansi gostermistir. Tum modeller %91+ dogruluk saglamistir.
