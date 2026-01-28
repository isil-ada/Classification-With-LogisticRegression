# Bank Personal Loan Classification (Logistic Regression)

Bu proje, **Bank Personal Loan Modelling** veri seti kullanılarak müşterilerin kişisel kredi (Personal Loan) alıp almayacağının **Logistic Regression** algoritması ile tahmin edilmesini amaçlamaktadır. Çalışma kapsamında veri ön işleme, model eğitimi, model değerlendirme ve **hiperparametre optimizasyonu (GridSearchCV)** adımları detaylı şekilde ele alınmıştır.

> **Not:** Bu proje, ders / akademik çalışma kapsamında hazırlanmış olup öğretici niteliktedir.

---

## Proje Yapısı

```
Classification-With-Logistic-Regression/
│
├── Classification_with_Logistic_Regression.ipynb
├── Bank_Personal_Loan_Modelling.csv
└── README.md
```

---

## Kullanılan Teknolojiler ve Kütüphaneler

* Python 3.x
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn

---

## Veri Seti Hakkında

Veri seti, bankacılık müşterilerine ait demografik ve finansal bilgileri içermektedir. Amaç, müşterinin **Personal Loan** (kişisel kredi) alıp almayacağını tahmin etmektir.

* Hedef değişken: **Personal Loan** (0 / 1)
* Gereksiz görülen **ID** kolonu modelleme öncesinde veri setinden çıkarılmıştır.
* Eksik veri kontrolü yapılmış, veri setinde boş değer bulunmadığı görülmüştür.

---

## Modelleme Süreci

### 1️Veri Hazırlama

* Özellikler (X) ve hedef değişken (y) ayrıştırılmıştır.
* Veri seti %80 eğitim, %20 test olacak şekilde bölünmüştür.
* Özellikler, **StandardScaler** kullanılarak ölçeklendirilmiştir.

---

### Logistic Regression Modeli

* Temel Logistic Regression modeli eğitilmiştir.
* Test verisi üzerinde doğruluk (accuracy) metriği ile değerlendirilmiştir.
* **Confusion Matrix** ve **Classification Report** ile model performansı detaylı şekilde analiz edilmiştir.

Confusion Matrix görselleştirmesi için **Seaborn heatmap** kullanılmıştır.

---

## Model Değerlendirme Metrikleri

Aşağıdaki metrikler kullanılmıştır:

* Accuracy
* Precision
* Recall
* F1-Score

Bu metrikler, sınıflandırma performansının dengeli bir şekilde değerlendirilmesini sağlamaktadır.

---

## Hiperparametre Optimizasyonu (GridSearchCV)

Model performansını artırmak amacıyla **GridSearchCV** kullanılmıştır.

### Denenen Parametreler:

* `solver`: liblinear, lbfgs, saga

* `penalty`: l1, l2, elasticnet, None

* `C`: 0.001 – 100 aralığında farklı değerler

* `max_iter`: 200 – 2000

* `class_weight`: balanced / None

* `l1_ratio` (ElasticNet için)

* 5-fold çapraz doğrulama uygulanmıştır.

* En iyi hiperparametreler otomatik olarak seçilmiştir.

---

## Orijinal vs Optimize Edilmiş Model Karşılaştırması

| Model    | Test Accuracy | İyileşme |
| -------- | ------------- | -------- |
| Original | Referans      | 0        |
| Tuned    | Daha Yüksek   | Pozitif  |

Ayrıca aşağıdaki metrikler grafiksel olarak karşılaştırılmıştır:

* Accuracy
* Precision
* Recall
* F1-Score

Bu karşılaştırma sayesinde hiperparametre optimizasyonunun model performansına olan katkısı net bir şekilde gözlemlenmiştir.

---

## Görselleştirmeler

* Confusion Matrix (Orijinal & Tuned)
* Model performans karşılaştırma bar grafiği

Görseller, modelin güçlü ve zayıf yönlerini yorumlamayı kolaylaştırmaktadır.

---

## Diğer Algoritmalar ile Karşılaştırma

### KNN (K-Nearest Neighbors)

**Avantajlar:**

* Basit ve sezgisel bir algoritmadır
* Parametrik değildir

**Dezavantajlar:**

* Büyük veri setlerinde hesaplama maliyeti yüksektir
* Özellik ölçeklendirmeye oldukça duyarlıdır
* K değeri yanlış seçilirse performans düşer

Logistic Regression, KNN’e kıyasla daha hızlıdır ve büyük veri setlerinde daha stabildir.

---

### Decision Tree

**Avantajlar:**

* Yorumlanabilirliği yüksektir
* Özellik ölçeklendirmeye ihtiyaç duymaz

**Dezavantajlar:**

* Aşırı öğrenmeye (overfitting) yatkındır
* Küçük veri değişimlerine karşı hassastır

Bu projede kullanılan Logistic Regression modeli, Decision Tree’ye kıyasla daha dengeli ve genellenebilir sonuçlar üretmiştir.

---

## Sonuç

Bu proje, **Logistic Regression** algoritmasının sınıflandırma problemlerinde nasıl kullanılacağını, hiperparametre optimizasyonunun model performansına etkisini ve farklı algoritmalarla karşılaştırmasını kapsamlı şekilde göstermektedir.

Makine öğrenmesine yeni başlayanlar ve sınıflandırma algoritmalarını karşılaştırmalı olarak öğrenmek isteyenler için öğretici bir çalışmadır.

---

---

Projeyi beğendiyseniz yıldız vermeyi unutmayın!


