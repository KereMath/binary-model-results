# Stationarity Detector ML

## Gorev
**Binary Classification:** Stationary vs Non-Stationary

## En Iyi Model
| Metrik | Deger |
|--------|-------|
| Model | MLP |
| F1 (macro) | 0.9410 |
| Accuracy | 0.9412 |
| Cohen's Kappa | 0.8825 |
| MCC | 0.8886 |

## Ozellik Cikarma
- **Yontem:** Sliding Window ile istatistiksel ozellikler
- **Pencere Stratejisi:** L/5 (HPT ile optimize edilmis)
- **HPT Yontemi:** GridSearchCV (tek repo olan single detector ml gibi)

## Veri Seti
| Set | Ornek Sayisi |
|-----|--------------|
| Toplam | 119,123 |
| Stationary | 59,598 |
| Non-Stationary | 59,525 |

## Coklu Versiyon Karsilastirmasi (HPT)

### v1 (Baseline)
| Model | Accuracy | F1 (macro) | Cohen's Kappa | MCC |
|-------|----------|------------|---------------|-----|
| XGBoost | 0.8901 | 0.8887 | 0.7801 | 0.7997 |
| LightGBM | 0.8866 | 0.8851 | 0.7732 | 0.7939 |
| Random Forest | 0.8664 | 0.8639 | 0.7327 | 0.7604 |
| MLP | 0.8657 | 0.8632 | 0.7313 | 0.7592 |
| Decision Tree | 0.8797 | 0.8780 | 0.7594 | 0.7822 |

### v2 (Improved)
| Model | Accuracy | F1 (macro) | Cohen's Kappa | MCC |
|-------|----------|------------|---------------|-----|
| Extra Trees | 0.9112 | 0.9105 | 0.8224 | 0.8357 |
| Random Forest | 0.9101 | 0.9094 | 0.8202 | 0.8338 |
| XGBoost | 0.8949 | 0.8937 | 0.7898 | 0.8079 |
| Decision Tree | 0.8869 | 0.8854 | 0.7737 | 0.7943 |
| LightGBM | 0.8884 | 0.8869 | 0.7767 | 0.7968 |

### v3 (Further Tuning)
| Model | Accuracy | F1 (macro) | Cohen's Kappa | MCC |
|-------|----------|------------|---------------|-----|
| **MLP** | **0.9412** | **0.9410** | **0.8825** | **0.8886** |
| XGBoost | 0.9375 | 0.9372 | 0.8750 | 0.8819 |
| LightGBM | 0.9361 | 0.9359 | 0.8722 | 0.8794 |
| Random Forest | 0.9078 | 0.9070 | 0.8157 | 0.8299 |

### v4 (Final - En Iyi)
| Model | Accuracy | F1 (macro) | Cohen's Kappa | MCC |
|-------|----------|------------|---------------|-----|
| **MLP** | **0.9412** | **0.9410** | **0.8825** | **0.8886** |
| XGBoost | 0.9389 | 0.9386 | 0.8777 | 0.8843 |
| Random Forest | 0.9337 | 0.9334 | 0.8673 | 0.8750 |
| Extra Trees | 0.9334 | 0.9331 | 0.8668 | 0.8746 |
| LightGBM | 0.9306 | 0.9302 | 0.8611 | 0.8695 |
| Decision Tree | 0.8860 | 0.8846 | 0.7720 | 0.7913 |

## Confusion Matrix (v4 MLP - En Iyi)
|  | Predicted Stationary | Predicted Non-Stationary |
|--|----------------------|-------------------------|
| Actual Stationary | 59,598 | 0 |
| Actual Non-Stationary | 7,000 | 52,525 |

## Not
Bu detector hocanin makalesinde kullanilan orijinal stationarity detector'dur. Coklu HPT versiyonlari (v1-v6) ile optimize edilmistir. v3 ve v4'te MLP modeli en iyi performansi gostermis ve %94.10 F1 skoruna ulasmistir.

**Onemli:** HPT sureci, model performansini baseline'dan (v1: %88.87) final'e (v4: %94.10) onemli olcude arttirmistir (~%5.2 iyilesme).
