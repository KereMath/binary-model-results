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

## Ozellik Cikarma
- **Yontem:** TSFresh "Efficient" parameter set
- **Ozellik Sayisi:** 777 istatistiksel, spektral ve temporal ozellik
- **Pencere Stratejisi:** No Window (tum seri tek parca)

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

## Not
Deterministic trend sinifi cok yuksek dogrulukla tespit edilebilmektedir. LightGBM modeli %98.45 F1 skoru ile en iyi performansi gostermistir.
