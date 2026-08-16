# Fake News Detection

A Natural Language Processing and Machine Learning project for classifying news articles as **Fake or True**.

The project compares traditional machine learning algorithms with deep learning approaches, including **Linear SVM, Random Forest, Logistic Regression, Multinomial Naive Bayes, CNN, and LSTM**.

> **Best Test Accuracy: 99.94% — CNN**

---

## 📊 Results

| Model                       | Approach                  | Test Accuracy |
| --------------------------- | ------------------------- | ------------: |
| **CNN**                     | Deep Learning             |    **99.94%** |
| **Linear SVC**              | TF-IDF + Machine Learning |    **99.75%** |
| **LSTM**                    | Deep Learning             |    **99.72%** |
| **Logistic Regression**     | TF-IDF + Machine Learning |    **99.10%** |
| **Random Forest**           | TF-IDF + Machine Learning |    **97.91%** |
| **Multinomial Naive Bayes** | TF-IDF + Machine Learning |    **94.22%** |

The reported results were obtained from the executed notebooks using the current preprocessing pipeline and train/test split.

---

# 🇬🇧 English

## 📌 Project Overview

This project focuses on the automatic classification of news articles as **Fake** or **True** using Natural Language Processing (NLP), traditional machine learning, and deep learning techniques.

The project compares multiple approaches to determine how different text classification methods perform on the same dataset.

The following models were implemented and evaluated:

* Linear Support Vector Machine (LinearSVC)
* Random Forest
* Logistic Regression
* Multinomial Naive Bayes
* Convolutional Neural Network (CNN)
* Long Short-Term Memory (LSTM)

---

## 📓 Project Structure

The project consists of three Jupyter Notebooks:

| Notebook                       | Description                                                       |
| ------------------------------ | ----------------------------------------------------------------- |
| `FakeNewsDetection.ipynb`      | Traditional machine learning models and exploratory data analysis |
| `FakeNewsDetection-CNN.ipynb`  | CNN-based text classification                                     |
| `FakeNewsDetection-LSTM.ipynb` | LSTM-based text classification                                    |

---

## 📂 Dataset

The project uses two datasets:

* `Fake.csv`
* `True.csv`

Each article contains the following fields:

* `title` — News headline
* `text` — Article content
* `subject` — News category
* `date` — Publication date

The target labels are defined as:

* `0` → Fake News
* `1` → True News

The dataset contains:

* **23,481 fake news articles**
* **21,417 true news articles**
* **44,898 articles in total**

---

## 🧹 Text Preprocessing

The text data is processed using several NLP techniques before model training.

The preprocessing pipeline includes:

* Removing unnecessary characters
* Removing HTML and script content
* Converting text to lowercase
* Stopword removal
* Tokenization
* Lemmatization
* Cleaning and combining text fields

The `title`, `subject`, and `text` fields are combined to create the input text used by the models.

---

## 🔎 Exploratory Data Analysis

Exploratory Data Analysis (EDA) was performed to investigate the textual characteristics and distribution of the dataset.

The analysis includes:

* Word frequency analysis
* WordCloud visualization
* 2-gram analysis
* 3-gram analysis
* Class distribution analysis
* Text-based visualizations

The following libraries were used:

* Matplotlib
* Seaborn
* WordCloud

---

# 🤖 Traditional Machine Learning

For the traditional machine learning approach, the processed text was transformed into numerical features using **TF-IDF Vectorization**.

The dataset was split into:

* **80% training**
* **20% testing**

The following classifiers were evaluated:

### Linear Support Vector Machine

**Test Accuracy: 99.75%**

### Logistic Regression

**Test Accuracy: 99.10%**

### Random Forest

**Test Accuracy: 97.91%**

### Multinomial Naive Bayes

**Test Accuracy: 94.22%**

### Traditional ML Comparison

| Model                   | Test Accuracy |
| ----------------------- | ------------: |
| Linear SVC              |    **99.75%** |
| Logistic Regression     |    **99.10%** |
| Random Forest           |    **97.91%** |
| Multinomial Naive Bayes |    **94.22%** |

---

# 🧠 Deep Learning

## CNN

For the CNN approach, the text was tokenized using the TensorFlow/Keras `Tokenizer`.

The input sequences were padded to a maximum length of **650 tokens**, with the vocabulary limited to **20,000 words**.

### Architecture

```text
Input Text
    ↓
Tokenizer
    ↓
Padding
    ↓
Embedding
    ↓
Conv1D
    ↓
GlobalMaxPooling1D
    ↓
Dense
    ↓
Sigmoid
    ↓
Fake / True
```

The model was trained using:

* **Optimizer:** Adam
* **Loss:** Binary Crossentropy
* **Early Stopping:** Enabled

### CNN Result

**Test Accuracy: 99.94%**

**Test Loss: ~0.0015**

---

## LSTM

For the LSTM approach, the text was tokenized and padded to a maximum sequence length of **650 tokens**.

### Architecture

```text
Input Text
    ↓
Tokenizer
    ↓
Padding
    ↓
Embedding
    ↓
LSTM (100 units)
    ↓
Dense
    ↓
Sigmoid
    ↓
Fake / True
```

The model was trained using:

* **Optimizer:** Adam
* **Loss:** Binary Crossentropy

### LSTM Result

**Test Accuracy: 99.72%**

**Test Loss: ~0.0129**

---

# 📈 Model Comparison

The experiments demonstrate that both traditional machine learning and deep learning approaches can achieve very high performance on this dataset.

```text
CNN                    99.94%
Linear SVC             99.75%
LSTM                   99.72%
Logistic Regression    99.10%
Random Forest          97.91%
Naive Bayes            94.22%
```

The CNN achieved the highest recorded test accuracy among the evaluated models.

---

## 🛠️ Technologies

### Programming Language

* Python

### Data Processing

* Pandas
* NumPy

### Natural Language Processing

* NLTK
* BeautifulSoup

### Machine Learning

* Scikit-learn

### Deep Learning

* TensorFlow
* Keras

### Visualization

* Matplotlib
* Seaborn
* WordCloud

---

## 📁 Repository Structure

```text
fake-news-detection/
│
├── FakeNewsDetection.ipynb
├── FakeNewsDetection-CNN.ipynb
├── FakeNewsDetection-LSTM.ipynb
│
├── Fake.csv
├── True.csv
│
├── README.md
└── requirements.txt
```

---

## ⚠️ Limitations

The reported accuracy values are based on the current dataset, preprocessing pipeline, and train/test split used in the notebooks.

The very high test accuracy should therefore **not be interpreted as equivalent to real-world fake-news detection performance**.

Potential factors that may affect generalization include:

* Dataset-specific linguistic patterns
* Differences between fake and true news sources
* Similar or duplicated articles within the dataset
* Dataset bias
* Distribution differences between the dataset and real-world news
* The specific train/test split used in the experiments

Further evaluation using an independent external dataset, cross-validation, and additional metrics such as **precision, recall, F1-score, and confusion matrices** would provide a stronger assessment of model generalization.

---

## 📝 Notes

All reported performance metrics were obtained from the executed notebooks.

Results may vary depending on:

* Train/test split
* Preprocessing techniques
* Random state
* Model hyperparameters
* Dataset composition

This project is intended as an experimental comparison of NLP-based text classification approaches rather than a production-ready fake-news detection system.

---

# 🇹🇷 Türkçe

## 📌 Proje Özeti

Bu proje, haber metinlerinin **Sahte (Fake)** veya **Gerçek (True)** olarak otomatik şekilde sınıflandırılması amacıyla geliştirilmiş bir **Doğal Dil İşleme (NLP), Makine Öğrenmesi ve Derin Öğrenme** projesidir.

Projede geleneksel makine öğrenmesi algoritmaları ile derin öğrenme modelleri karşılaştırılmıştır.

Uygulanan modeller:

* Linear Support Vector Machine (LinearSVC)
* Random Forest
* Logistic Regression
* Multinomial Naive Bayes
* Convolutional Neural Network (CNN)
* Long Short-Term Memory (LSTM)

> **En yüksek test doğruluğu: %99,94 — CNN**

---

## 📊 Sonuçlar

| Model                       | Yaklaşım                  | Test Accuracy |
| --------------------------- | ------------------------- | ------------: |
| **CNN**                     | Derin Öğrenme             |    **%99,94** |
| **Linear SVC**              | TF-IDF + Makine Öğrenmesi |    **%99,75** |
| **LSTM**                    | Derin Öğrenme             |    **%99,72** |
| **Logistic Regression**     | TF-IDF + Makine Öğrenmesi |    **%99,10** |
| **Random Forest**           | TF-IDF + Makine Öğrenmesi |    **%97,91** |
| **Multinomial Naive Bayes** | TF-IDF + Makine Öğrenmesi |    **%94,22** |

Sonuçlar, notebook'larda kullanılan mevcut preprocessing pipeline ve train/test ayrımı üzerinden elde edilmiştir.

---

## 📓 Proje İçeriği

Proje üç farklı Jupyter Notebook içermektedir:

| Notebook                       | Açıklama                                                       |
| ------------------------------ | -------------------------------------------------------------- |
| `FakeNewsDetection.ipynb`      | Geleneksel makine öğrenmesi modelleri ve keşifsel veri analizi |
| `FakeNewsDetection-CNN.ipynb`  | CNN tabanlı metin sınıflandırma modeli                         |
| `FakeNewsDetection-LSTM.ipynb` | LSTM tabanlı metin sınıflandırma modeli                        |

---

## 📂 Veri Seti

Projede iki veri seti kullanılmıştır:

* `Fake.csv`
* `True.csv`

Her haber aşağıdaki alanları içermektedir:

* `title` — Haber başlığı
* `text` — Haber metni
* `subject` — Haber konusu
* `date` — Yayın tarihi

Etiketler:

* `0` → Sahte Haber
* `1` → Gerçek Haber

Veri setinde:

* **23.481 sahte haber**
* **21.417 gerçek haber**
* **Toplam 44.898 haber**

bulunmaktadır.

---

## 🧹 Veri Ön İşleme

Model eğitimi öncesinde haber metinleri çeşitli NLP işlemlerinden geçirilmiştir.

Uygulanan işlemler:

* Gereksiz karakterlerin temizlenmesi
* HTML ve script içeriklerinin temizlenmesi
* Küçük harfe dönüştürme
* Stopword temizleme
* Tokenization
* Lemmatization
* Metin alanlarının birleştirilmesi ve temizlenmesi

Model girdisini oluşturmak için `title`, `subject` ve `text` alanları birlikte kullanılmıştır.

---

## 🔎 Keşifsel Veri Analizi

Veri setinin yapısını ve metinsel özelliklerini incelemek amacıyla çeşitli EDA çalışmaları gerçekleştirilmiştir.

Bunlar:

* Kelime frekansı analizi
* WordCloud görselleştirmeleri
* 2-gram analizi
* 3-gram analizi
* Sınıf dağılımı analizi
* Metin tabanlı görselleştirmeler

Kullanılan kütüphaneler:

* Matplotlib
* Seaborn
* WordCloud

---

# 🤖 Geleneksel Makine Öğrenmesi

Metin verileri, geleneksel makine öğrenmesi modellerinde kullanılmak üzere **TF-IDF Vectorization** yöntemiyle sayısal özelliklere dönüştürülmüştür.

Veri:

* **%80 eğitim**
* **%20 test**

olacak şekilde ayrılmıştır.

Uygulanan modeller:

### Linear Support Vector Machine

**Test Accuracy: %99,75**

### Logistic Regression

**Test Accuracy: %99,10**

### Random Forest

**Test Accuracy: %97,91**

### Multinomial Naive Bayes

**Test Accuracy: %94,22**

### Geleneksel Modellerin Karşılaştırması

| Model                   | Test Accuracy |
| ----------------------- | ------------: |
| Linear SVC              |    **%99,75** |
| Logistic Regression     |    **%99,10** |
| Random Forest           |    **%97,91** |
| Multinomial Naive Bayes |    **%94,22** |

---

# 🧠 Derin Öğrenme

## CNN

CNN yaklaşımında metinler TensorFlow/Keras `Tokenizer` kullanılarak tokenize edilmiştir.

Metinler maksimum **650 token** uzunluğuna padding uygulanarak hazırlanmış ve kelime dağarcığı **20.000 kelime** ile sınırlandırılmıştır.

### Model Mimarisi

```text
Girdi Metni
    ↓
Tokenizer
    ↓
Padding
    ↓
Embedding
    ↓
Conv1D
    ↓
GlobalMaxPooling1D
    ↓
Dense
    ↓
Sigmoid
    ↓
Fake / True
```

Model eğitiminde:

* **Optimizer:** Adam
* **Loss:** Binary Crossentropy
* **Early Stopping:** Kullanıldı

### CNN Sonucu

**Test Accuracy: %99,94**

**Test Loss: ~0,0015**

---

## LSTM

LSTM modelinde metinler tokenize edilmiş ve maksimum **650 token** uzunluğuna padding uygulanmıştır.

### Model Mimarisi

```text
Girdi Metni
    ↓
Tokenizer
    ↓
Padding
    ↓
Embedding
    ↓
LSTM (100 units)
    ↓
Dense
    ↓
Sigmoid
    ↓
Fake / True
```

Model eğitiminde:

* **Optimizer:** Adam
* **Loss:** Binary Crossentropy

kullanılmıştır.

### LSTM Sonucu

**Test Accuracy: %99,72**

**Test Loss: ~0,0129**

---

# 📈 Model Karşılaştırması

Deneyler, hem geleneksel makine öğrenmesi hem de derin öğrenme yaklaşımlarının bu veri setinde oldukça yüksek performans gösterebildiğini ortaya koymaktadır.

```text
CNN                    %99,94
Linear SVC             %99,75
LSTM                   %99,72
Logistic Regression    %99,10
Random Forest          %97,91
Naive Bayes            %94,22
```

Test sonuçları içerisinde en yüksek doğruluk **CNN modeli tarafından %99,94** ile elde edilmiştir.

---

## 🛠️ Kullanılan Teknolojiler

### Programlama Dili

* Python

### Veri İşleme

* Pandas
* NumPy

### Doğal Dil İşleme

* NLTK
* BeautifulSoup

### Makine Öğrenmesi

* Scikit-learn

### Derin Öğrenme

* TensorFlow
* Keras

### Görselleştirme

* Matplotlib
* Seaborn
* WordCloud

---

## 📁 Proje Yapısı

```text
fake-news-detection/
│
├── FakeNewsDetection.ipynb
├── FakeNewsDetection-CNN.ipynb
├── FakeNewsDetection-LSTM.ipynb
│
├── Fake.csv
├── True.csv
│
├── README.md
└── requirements.txt
```

---

## ⚠️ Sınırlılıklar

Raporda belirtilen doğruluk değerleri, notebook'larda kullanılan mevcut veri seti, preprocessing pipeline ve train/test ayrımı üzerinden elde edilmiştir.

Bu nedenle elde edilen yüksek doğruluk değerleri **gerçek dünyadaki sahte haber tespit performansı ile doğrudan eşdeğer olarak değerlendirilmemelidir.**

Model performansını etkileyebilecek faktörler arasında:

* Veri setine özgü dilsel kalıplar
* Sahte ve gerçek haber kaynakları arasındaki farklılıklar
* Veri setindeki benzer veya tekrarlanan haberler
* Veri seti kaynaklı bias
* Veri seti ile gerçek dünya haber dağılımları arasındaki farklılıklar
* Kullanılan train/test ayrımı

bulunmaktadır.

Modelin genelleme yeteneğini daha güvenilir şekilde değerlendirmek için bağımsız bir harici veri seti, cross-validation ve **precision, recall, F1-score ve confusion matrix** gibi ek metriklerin kullanılması faydalı olacaktır.

---

## 📝 Not

Tüm performans değerleri çalıştırılmış notebook'lardan elde edilmiştir.

Sonuçlar aşağıdaki faktörlere bağlı olarak değişebilir:

* Train/test split
* Veri ön işleme yöntemleri
* Random state
* Model hyperparameter'ları
* Veri setinin içeriği

Bu proje, NLP tabanlı metin sınıflandırma yaklaşımlarının karşılaştırılması amacıyla hazırlanmış deneysel bir çalışmadır ve production-ready bir fake-news detection sistemi olarak değerlendirilmemelidir.
