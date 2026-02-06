# Mean Shift Detector ML

## Gorev
**Binary Classification:** Mean Shift vs Not Mean Shift

## En Iyi Model
| Metrik | Deger |
|--------|-------|
| Model | LightGBM |
| Validation F1 | 0.9111 |
| Test F1 | 0.9068 |
| Test Accuracy | 0.9049 |

## Ozellik Cikarma
- **Yontem:** TSFresh "Efficient" parameter set
- **Ozellik Sayisi:** 777 istatistiksel, spektral ve temporal ozellik
- **Pencere Stratejisi:** L/5 (sliding window)

## Veri Seti
| Set | Ornek Sayisi |
|-----|--------------|
| Train | 67,200 (33,600 + 33,600) |
| Validation | 9,600 (4,800 + 4,800) |
| Test | 19,200 (9,600 + 9,600) |
| **Toplam** | **96,000** |

## Egitim Suresi
| Model | Sure (saniye) |
|-------|---------------|
| LightGBM | 0.429 |
| XGBoost | 0.639 |
| MLP | 8.045 |
| Gradient Boosting | 96.627 |
| SVM RBF | 588.435 |

## Tum Model Karsilastirmasi
| Model | Val Accuracy | Val F1 | Val Precision | Val Recall | AUC |
|-------|--------------|--------|---------------|------------|-----|
| **LightGBM** | **0.9095** | **0.9111** | **0.8951** | **0.9277** | **0.9722** |
| XGBoost | 0.9034 | 0.9048 | 0.8919 | 0.9181 | 0.9703 |
| Gradient Boosting | 0.9029 | 0.9054 | 0.8827 | 0.9294 | 0.9681 |
| MLP | 0.9020 | 0.9034 | 0.8902 | 0.9171 | 0.9698 |
| Random Forest | 0.8998 | 0.9030 | 0.8750 | 0.9329 | 0.9664 |
| Extra Trees | 0.8778 | 0.8862 | 0.8291 | 0.9519 | 0.9540 |
| Decision Tree | 0.8726 | 0.8740 | 0.8646 | 0.8835 | 0.9282 |
| Naive Bayes | 0.5780 | 0.7032 | 0.5423 | 1.0000 | 0.7008 |
| SVM RBF | 0.5767 | 0.7026 | 0.5415 | 1.0000 | 0.7833 |
| SGD Classifier | 0.5728 | 0.6045 | 0.5628 | 0.6529 | 0.5803 |
| Logistic Regression | 0.5846 | 0.4687 | 0.6500 | 0.3665 | 0.7438 |

## 5-Fold Cross Validation (LightGBM)
| Fold | Accuracy | F1 | Precision | Recall |
|------|----------|-----|-----------|--------|
| 1 | 0.9093 | 0.9109 | 0.8954 | 0.9270 |
| 2 | 0.9069 | 0.9087 | 0.8916 | 0.9265 |
| 3 | 0.9085 | 0.9102 | 0.8943 | 0.9267 |
| 4 | 0.9065 | 0.9084 | 0.8901 | 0.9276 |
| 5 | 0.9049 | 0.9061 | 0.8950 | 0.9175 |

## Not
Bu detector hocanin makalesinde kullanilan orijinal mean shift detector'dur. 96,000 orneklik dengeli bir veri seti ile egitilmistir. LightGBM %91.11 F1 skoru ile en iyi performansi gostermistir.
