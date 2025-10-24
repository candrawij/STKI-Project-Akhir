# Proyek Akhir Sistem Temu Kembali Informasi (STKI)
**Rekomendasi Tempat Kemah Berbasis Ulasan Menggunakan Vector Space Model (VSM)**

1. ##💡 Deskripsi Proyek
Proyek ini adalah implementasi dari Vector Space Model (VSM) sebagai mesin pencari rekomendasi. Tujuannya adalah membantu pengguna menemukan tempat kemah terbaik di wilayah Jawa Tengah (Jateng) dan Daerah Istimewa Yogyakarta (DIY) berdasarkan relevansi ulasan yang ada.Sistem ini tidak hanya mencari kata kunci, tetapi juga memberikan bobot pada kata-kata penting (Term Weighting menggunakan TF-IDF) untuk menghasilkan urutan rekomendasi yang paling akurat dan sesuai dengan query pengguna.

3. 🛠️ ##*Metodologi dan Fitur Utama*
Proyek ini dibangun melalui beberapa tahap utama dengan fokus pada pemrosesan Bahasa Indonesia dan implementasi algoritma IR.Metodologi (Information Retrieval)Term Weighting: TF-IDF (Term Frequency-Inverse Document Frequency) digunakan untuk menghitung bobot setiap kata di setiap ulasan (dokumen) dan query (vektor).Indexing: Inverted Index dibangun dengan struktur data Linked List untuk menyimpan bobot TF-IDF dari setiap term ke dokumen yang mengandungnya.Ranking: Vector Space Model (VSM) diterapkan melalui perhitungan Cosine Similarity (Dot Product) antara vektor query dan vektor setiap dokumen ulasan.Fitur UtamaPreprocessing Bahasa Indonesia: Meliputi Case Folding, Stop Word Removal (menggunakan nltk.corpus.stopwords Bahasa Indonesia), dan Stemming (menggunakan Sastrawi).Pencarian Interaktif: Sistem dapat menerima query dari pengguna secara berulang dalam loop interaktif di Colab.Ranking Berbasis Relevansi: Hasil ditampilkan dalam urutan ranking berdasarkan seberapa relevan (tinggi skor VSM-nya) ulasan suatu tempat dengan kata kunci yang dicari.

4. 📁 ##*Struktur Data Korpus*
Korpus: Data dikumpulkan dari ulasan tempat kemah di Jateng dan DIY.Format: CSV (corpus_kemah_jateng_diy - Sheet1.csv).Isi Dokumen: Setiap baris mewakili satu ulasan (Doc_ID, Nama_Tempat, Lokasi, Rating, Teks_Mentah).Inverted Index ImplementationInverted Index diimplementasikan menggunakan:linked_list_data: Struktur dictionary di mana kunci adalah term unik, dan nilainya adalah objek SlinkedList.Node: Setiap node dalam linked list menyimpan docId dan freq (yang menyimpan nilai bobot TF-IDF $\text{W}(t, d)$).

5. ⚙️ ##*Kebutuhan dan Instalasi*
Proyek ini membutuhkan library Python berikut:Bash# Instalasi Library

pip install pandas
pip install nltk
pip install Sastrawi
 
5. 🚀 ##*Cara Menjalankan*
Clone Repositori:Bashgit clone https://github.com/candrawij/STKI-Project-Akhir.git
cd STKI-Project-Akhir
Siapkan Data: Pastikan file corpus_kemah_jateng_diy - Sheet1.csv berada di direktori yang sama dengan notebook atau script Python.Jalankan di Google Colab: Buka notebook VSM (misalnya, VSM_Ranking_Interactive.ipynb) di Google Colab.Eksekusi: Jalankan semua cell secara berurutan.Interaksi: Setelah cell terakhir dieksekusi, sistem akan meminta Anda memasukkan query pencarian:Masukkan kata kunci pencarian (atau ketik 'keluar' untuk berhenti):
Masukkan kata kunci (misalnya, toilet bersih) dan tekan Enter.Sistem akan menampilkan 5 rekomendasi teratas dan menanyakan apakah Anda ingin melanjutkan.Ketik ya untuk clear output dan memasukkan query baru.

6. ✨ ##*Contoh Hasil*
QueryHasil Ranking (Nama Tempat)Top VSM Scoredingin pemandangan terbaik1. Heha Sky View Camp (Ulasan: 4.8)0.87542. [Nama Tempat Lain] (Ulasan: 4.5)0.7212cocok untuk anak-anak1. [Nama Tempat Keluarga] (Ulasan: 5.0)0.9011......

7. 👤 ##*Kontributor*
Nama Anda: [Candra Wijayanto] NIM: [NIM Anda] Mata Kuliah: Sistem Temu Kembali Informasi (STKI) Dosen: [Nama Dosen Anda]
