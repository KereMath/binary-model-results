# Volatility Detector ML

## Gorev
**Binary Classification:** Volatility vs Not Volatility

## En Iyi Model
| Metrik | Deger |
|--------|-------|
| Model | MLP |
| Validation F1 | 0.9266 |
| Test F1 | 0.9046 |
| Test Accuracy | 0.9004 |

## Ozellik Cikarma
- **Yontem:** TSFresh "Efficient" parameter set
- **Ozellik Sayisi:** 777 istatistiksel, spektral ve temporal ozellik
- **Pencere Stratejisi:** No Window (tum seri tek parca)

## Veri Seti
| Set | Ornek Sayisi |
|-----|--------------|
| Train | 6,901 (3,450 + 3,451) |
| Validation | 767 (383 + 384) |
| Test | 1,917 |

## Egitim Suresi
| Model | Sure (saniye) |
|-------|---------------|
| LightGBM | 0.296 |
| XGBoost | 0.404 |
| MLP | 0.864 |

## Tum Model Karsilastirmasi
| Model | Val Accuracy | Val F1 | Val Precision | Val Recall |
|-------|--------------|--------|---------------|------------|
| **MLP** | **0.9244** | **0.9266** | **0.9015** | **0.9531** |
| XGBoost | 0.9192 | 0.9205 | 0.9066 | 0.9349 |
| LightGBM | 0.9153 | 0.9168 | 0.9018 | 0.9323 |

## Not
Volatility sinifi icin MLP modeli, LightGBM ve XGBoost'tan daha iyi performans gostermistir. Bu, volatility ozelliklerinin non-linear pattern'lar icerdigi anlamina gelebilir.
