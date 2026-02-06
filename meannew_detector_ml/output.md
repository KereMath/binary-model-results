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
| LightGBM | 0.233 |
| XGBoost | 0.501 |
| MLP | 0.578 |

## Tum Model Karsilastirmasi
| Model | Val Accuracy | Val F1 | Val Precision | Val Recall |
|-------|--------------|--------|---------------|------------|
| **LightGBM** | **0.8957** | **0.8964** | **0.8895** | **0.9034** |
| XGBoost | 0.8918 | 0.8943 | 0.8731 | 0.9164 |
| MLP | 0.8761 | 0.8777 | 0.8655 | 0.8903 |

## Not
Mean shift tespiti nispeten daha zor bir gorevdir (F1 ~0.90). LightGBM modeli en iyi dengeyi saglamistir.
