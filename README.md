# Proyek Akhir Sistem Temu Kembali Informasi (STKI)
*Rekomendasi Tempat Kemah Berbasis Ulasan Menggunakan Vector Space Model (VSM)*


## 1. 💡 Deskripsi Proyek

Proyek ini mengimplementasikan **Vector Space Model (VSM)** sebagai mesin pencari rekomendasi. Tujuan utamanya adalah membantu pengguna menemukan tempat kemah terbaik di wilayah **Jawa Tengah dan DIY** berdasarkan **relevansi** kata kunci pencarian terhadap korpus ulasan yang dikumpulkan.

Sistem ini memastikan **ranking** hasil bukan hanya karena kata kunci ditemukan (Boolean), tetapi karena ulasan tersebut secara statistik paling penting (bobot TF-IDF tertinggi) untuk *query* pengguna.

***

## 2. 🛠️ Metodologi dan Algoritma

* 2.1. Term Weighting & Indexing (TF-IDF)

    -  **Bobot:** Setiap term (kata dasar) diberi bobot **TF-IDF**, di mana nilai ini menjadi elemen vektor.
    $$\text{W}(t, d) = \text{TF}(t, d) \times \text{IDF}(t)$$
    -  **Indexing:** **Inverted Index** dibangun dengan struktur **Linked List** di mana setiap *node* menyimpan bobot TF-IDF ($\text{W}(t, d)$).

* 2.2. Ranking (VSM)

    -  **Pencocokan:** Relevansi dihitung menggunakan **Dot Product** (simulasi Cosine Similarity) antara vektor *query* yang sudah dibobot dan vektor dokumen.
    -  **Output:** Tempat kemah diurutkan dari skor relevansi tertinggi ke terendah.

* 2.3. Preprocessing Bahasa Indonesia ✨

    Digunakan untuk menormalisasi teks ulasan:
    -  **Stop Word Removal:** Filter kata-kata umum (menggunakan `nltk` Bahasa Indonesia).
    -  **Stemming:** Konversi kata berimbuhan ke kata dasar (misalnya, *berkemah* $\rightarrow$ *kemah*) menggunakan **Sastrawi**.

***

## 3. ⚙️ Kebutuhan dan Instalasi

Proyek ini membutuhkan *library* berikut. Direkomendasikan dijalankan di Google Colab.

```bash
# Instalasi Library Wajib
pip install pandas
pip install nltk
pip install Sastrawi
```

***

## 4. 🚀 Cara Menjalankan Engine

* 4.1. Clone Repositori ke lingkungan kerja Anda.

* 4.2. Pastikan Data Ada: File korpus (`corpus_kemah_jateng_diy - Sheet1.csv`) harus tersedia.

* 4.3. Eksekusi Kode: Jalankan seluruh script Python VSM.

* 4.4. Interaksi: Setelah indexing selesai, sistem akan otomatis masuk ke Loop Pencarian Interaktif:
```
Masukkan kata kunci pencarian (atau ketik 'keluar' untuk berhenti):
```
`
    - Masukkan kata kunci (misalnya, toilet bersih) dan tekan Enter.
    - Ketik ya untuk melanjutkan pencarian, atau tidak untuk mengakhiri.

***

## 5. 🔍 Contoh Hasil Ranking

Output menampilkan 5 rekomendasi teratas yang ulasannya paling relevan dengan *query*.

| Rank | Nama Tempat | Lokasi | Avg Rating | VSM Score (Relevansi) |
| :---: | :--- | :---: | :---: | :---: |
| 1 | Camp Ground | Gunungkidul, DIY | 4.70 | 2.8865 |
| 2 | Camping Umbul Sidomukti | Kab. Semarang, Jateng | 4.60 | 1.4929 |

***

## 6. 🧑‍💻 Kontributor

* Nama         :  Candra Wijayanto
* NIM          :  A11.2023.15419
* Mata Kuliah  :  Sistem Temu Kembali Informasi (STKI)
