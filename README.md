# 📄 CV Metin Benzerliği Analizi – Doğal Dil İşleme Projesi (Ödev-2)

Bu proje, Türkçe CV metinlerinden oluşan bir veri seti üzerinde **TF-IDF** ve **Word2Vec** modelleriyle benzerlik analizleri yapmayı ve bu modelleri karşılaştırmalı olarak değerlendirmeyi amaçlamaktadır. Proje, Doğal Dil İşleme dersi kapsamında ikinci ödev olarak hazırlanmıştır.

## 🧠 Amaç
- Eğitilen modellerle (TF-IDF & Word2Vec) benzerlik skoru hesaplamak
- Giriş cümlesi için en benzer ilk 5 CV cümlesini bulmak
- Her modelin başarısını hem anlamsal olarak hem de sıralama tutarlılığı açısından değerlendirmek

## 📁 Proje Dosya Yapısı

├── data/
│   ├── cv_dataset.csv                 # Ham CV verisi
│   ├── cv_lemmatized.csv             # Lemmatize edilmiş veri
│   ├── cv_stemmed.csv                # Stemlenmiş veri
├── outputs/
│   ├── tfidf_stemmed_cv.csv          # Stemmed TF-IDF vektörleri
│   ├── tfidf_lemmatized_cv.csv       # Lemmatized TF-IDF vektörleri
├── models/
│   ├── cv_lemmatized_model_cbow_window2_dim100.model
│   ├── cv_lemmatized_model_cbow_window2_dim300.model
│   └── ...                           # Toplam 16 adet Word2Vec modeli
├── notebook.ipynb                    # Tüm analizlerin yer aldığı Jupyter defteri
├── README.md                         # Bu dosya
├── final_report.pdf                  # PDF olarak hazırlanmış proje raporu

## ⚙️ Kurulum ve Kullanım

### 1. Gerekli Kütüphaneler

Proje şu Python kütüphanelerini kullanır:

pip install pandas numpy scikit-learn gensim tqdm tabulate

Jupyter Notebooks için ayrıca:

pip install notebook

### 2. Notebook'u Çalıştırma

jupyter notebook

Ardından `notebook.ipynb` dosyasını açarak adım adım çalıştırabilirsiniz.

## 🧪 Kullanılan Yöntemler

### A. TF-IDF Benzerliği
- `TfidfVectorizer` ile metin vektörleri oluşturuldu.
- `cosine_similarity` ile giriş cümlesi ile tüm cümleler karşılaştırıldı.

### B. Word2Vec Benzerliği
- Toplam 16 model eğitildi (CBOW / SkipGram, farklı pencere boyutu ve vektör boyutları)
- Her kelimenin vektörü alındı, ortalama alındı ve cosine similarity hesaplandı.

## 📊 Değerlendirme Yöntemleri

### 1. Anlamsal Değerlendirme
- Her modelin önerdiği 5 benzer cümleye 1-5 arası puan verildi
- Her model için ortalama puanlar hesaplandı ve karşılaştırıldı

### 2. Sıralama Tutarlılığı (Jaccard Benzerliği)
- Modellerin sıraladığı ilk 5 CV karşılaştırıldı
- Jaccard skorları ile modellerin benzerlikleri analiz edildi

## 📈 Örnek Sonuçlar

- En başarılı model: `cv_lemmatized_model_cbow_window2_dim100`
- TF-IDF modelleri daha düşük başarı gösterdi
- Pencere boyutu ve vektör boyutu, başarıyı doğrudan etkiledi

## 📌 Notlar

- Giriş metni olarak veri setinden 1 CV seçildi (örnek: index 3)
- Modellerin çıktıları tablolarla görselleştirildi
- Anlamsal değerlendirme tamamen kullanıcı tarafından manuel olarak yapılmıştır

## 📄 Lisans
Bu proje yalnızca eğitim amacıyla hazırlanmıştır.

📫 Herhangi bir soru için iletişim: [Güner / bektasguner772@gmail.com]
