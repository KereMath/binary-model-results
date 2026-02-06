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

## Ozellik Cikarma
- **Yontem:** TSFresh "Efficient" parameter set
- **Ozellik Sayisi:** 777 istatistiksel, spektral ve temporal ozellik
- **Pencere Stratejisi:** No Window (tum seri tek parca)

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

## Not
Point anomaly tespiti en zor gorevlerden biridir (en dusuk F1 skorlarindan biri). Bu, point anomaly'lerin diger siniflarla ozellik uzayinda cakismasi nedeniyle olabilir.
