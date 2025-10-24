# 🏕️ Proyek STKI: Rekomendasi Tempat Kemah VSM

![Proyek VSM]([https://picsum.photos/900/350/?blur=1](https://akcdn.detik.net.id/community/media/visual/2020/05/22/fc03c424-a754-4a91-9277-3db8715a3153_169.jpeg?w=700&q=90))

***
[![Status](https://img.shields.io/badge/Status-Selesai-brightgreen)]()
[![Python](https://img.shields.io/badge/Language-Python%203.11+-blue)]()

## 1. 💡 Deskripsi Proyek

Proyek ini mengimplementasikan **Vector Space Model (VSM)** sebagai mesin pencari rekomendasi. Tujuan utamanya adalah membantu pengguna menemukan tempat kemah terbaik di wilayah **Jawa Tengah dan DIY** berdasarkan **relevansi** kata kunci pencarian terhadap korpus ulasan yang dikumpulkan.

Sistem ini memastikan **ranking** hasil bukan hanya karena kata kunci ditemukan (Boolean), tetapi karena ulasan tersebut secara statistik paling penting (bobot TF-IDF tertinggi) untuk *query* pengguna.

***

## 2. 🛠️ Metodologi dan Algoritma

### 2.1. Term Weighting & Indexing (TF-IDF)

* **Bobot:** Setiap term (kata dasar) diberi bobot **TF-IDF**, di mana nilai ini menjadi elemen vektor.
    $$\text{W}(t, d) = \text{TF}(t, d) \times \text{IDF}(t)$$
* **Indexing:** **Inverted Index** dibangun dengan struktur **Linked List** di mana setiap *node* menyimpan bobot TF-IDF ($\text{W}(t, d)$).

### 2.2. Ranking (VSM)

* **Pencocokan:** Relevansi dihitung menggunakan **Dot Product** (simulasi Cosine Similarity) antara vektor *query* yang sudah dibobot dan vektor dokumen.
* **Output:** Tempat kemah diurutkan dari skor relevansi tertinggi ke terendah.

### 2.3. Preprocessing Bahasa Indonesia ✨

Digunakan untuk menormalisasi teks ulasan:
* **Stop Word Removal:** Filter kata-kata umum (menggunakan `nltk` Bahasa Indonesia).
* **Stemming:** Konversi kata berimbuhan ke kata dasar (misalnya, *berkemah* $\rightarrow$ *kemah*) menggunakan **Sastrawi**.

***

## 3. ⚙️ Kebutuhan dan Instalasi

Proyek ini membutuhkan *library* berikut. Direkomendasikan dijalankan di Google Colab.

```bash
# Instalasi Library Wajib
pip install pandas
pip install nltk
pip install Sastrawi
