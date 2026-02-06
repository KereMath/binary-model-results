# Collective Anomaly Detector ML

## Gorev
**Binary Classification:** Collective Anomaly vs Not Collective Anomaly

## En Iyi Model
| Metrik | Deger |
|--------|-------|
| Model | LightGBM |
| Validation F1 | 0.8958 |
| Test F1 | 0.8992 |
| Test Accuracy | 0.8953 |

## Ozellik Cikarma
- **Yontem:** TSFresh "Efficient" parameter set
- **Ozellik Sayisi:** 777 istatistiksel, spektral ve temporal ozellik
- **Pencere Stratejisi:** No Window (tum seri tek parca)

## Veri Seti
| Set | Ornek Sayisi |
|-----|--------------|
| Train | 6,904 (3,454 + 3,450) |
| Validation | 768 (384 + 384) |
| Test | 1,919 |

## Egitim Suresi
| Model | Sure (saniye) |
|-------|---------------|
| LightGBM | 0.362 |
| XGBoost | 0.503 |
| MLP | 0.954 |

## Tum Model Karsilastirmasi
| Model | Val Accuracy | Val F1 | Val Precision | Val Recall |
|-------|--------------|--------|---------------|------------|
| **LightGBM** | **0.8906** | **0.8958** | **0.8555** | **0.9401** |
| XGBoost | 0.8867 | 0.8917 | 0.8544 | 0.9323 |
| MLP | 0.8841 | 0.8916 | 0.8375 | 0.9531 |

## Not
Collective anomaly tespiti orta zorlukta bir gorevdir. Tum modeller yuksek recall (~93-95%) ama daha dusuk precision (~85%) gostermistir.
