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

## Ozellik Cikarma
- **Yontem:** TSFresh "Efficient" parameter set
- **Ozellik Sayisi:** 777 istatistiksel, spektral ve temporal ozellik
- **Pencere Stratejisi:** No Window (tum seri tek parca)

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

## Not
Stochastic trend sinifi yuksek dogrulukla tespit edilebilmektedir. LightGBM %97.75 F1 skoru ile en iyi sonucu vermistir.
