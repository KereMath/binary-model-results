# Contextual Anomaly Detector ML

## Gorev
**Binary Classification:** Contextual Anomaly vs Not Contextual Anomaly

## En Iyi Model
| Metrik | Deger |
|--------|-------|
| Model | LightGBM |
| Validation F1 | 1.0000 |
| Test F1 | 1.0000 |
| Test Accuracy | 1.0000 |

## Ozellik Cikarma
- **Yontem:** TSFresh "Efficient" parameter set
- **Ozellik Sayisi:** 777 istatistiksel, spektral ve temporal ozellik
- **Pencere Stratejisi:** No Window (tum seri tek parca)

## Veri Seti
| Set | Ornek Sayisi |
|-----|--------------|
| Train | 6,904 (3,454 + 3,450) |
| Validation | 768 (384 + 384) |
| Test | 1,919 (960 + 959) |

## Egitim Suresi
| Model | Sure (saniye) |
|-------|---------------|
| LightGBM | 0.126 |
| XGBoost | 0.188 |
| MLP | 0.406 |

## Tum Model Karsilastirmasi
| Model | Val Accuracy | Val F1 | Val Precision | Val Recall |
|-------|--------------|--------|---------------|------------|
| **LightGBM** | **1.0000** | **1.0000** | **1.0000** | **1.0000** |
| MLP | 1.0000 | 1.0000 | 1.0000 | 1.0000 |
| XGBoost | 0.9987 | 0.9987 | 1.0000 | 0.9974 |

## Not
Bu detector mukemmel performans gostermistir (F1=1.0). Contextual anomaly siniflari diger siniflardan kolayca ayirt edilebilir ozelliklere sahiptir.
