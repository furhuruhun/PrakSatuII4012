# PrakSatuII4012

Repositori untuk **Praktikum 1: Chatbot** mata kuliah **II4012 Inteligensi Artifisial untuk Bisnis**.

**Tanggal:** 5 Maret 2026

---

## Anggota Kelompok

| Nama | NIM |
|------|-----|
| Muhammad Farhan | 18223004 |
| Kenlyn Tesalonika W | 18223098 |

---

## Topik Chatbot

**Peraturan Kemahasiswaan ITB 2022**

Chatbot ini menjawab pertanyaan seputar peraturan kemahasiswaan ITB (beasiswa, asrama, layanan kesehatan, konseling, organisasi, Mapres, penghargaan Ganesha, izin kegiatan, dan topik terkait).

---

## Tujuan

Implementasi dan analisis perbandingan chatbot **berbasis aturan (rule-based)** dan **generatif (LLM)**, termasuk varian **RAG (Retrieval-Augmented Generation)**.

---

## Isi Proyek

| File | Deskripsi |
|------|-----------|
| `QA_ChatBot_18223004_18223098.ipynb` | Notebook utama berisi semua implementasi chatbot |

---

## Ringkasan Isi Notebook

1. **Rule-based Chatbot (Regex)**  
   Chatbot dengan pola regex untuk mencocokkan pertanyaan dengan jawaban tetap (beasiswa, asrama, kesehatan, konseling, disabilitas, karakter, kewirausahaan, izin kegiatan, organisasi, Mapres, Ganesha). Input dibersihkan (lowercase, hapus filler) lalu dicocokkan ke aturan.

2. **Rule-based Chatbot (NLTK)**  
   Chatbot sederhana memakai NLTK `Chat` dan pasangan refleksi untuk percakapan dasar.

3. **Chatbot dengan LLM**  
   Chatbot generatif menggunakan model Hugging Face (mis. TinyLlama) lewat `transformers` untuk menghasilkan jawaban.

4. **Chatbot RAG–LLM**  
   - **Parsing PDF**: ekstraksi teks dengan `pypdf`, chunking (ukuran & overlap konfigurasi).  
   - **Embedding & indexing**: SentenceTransformer (BAAI/bge-m3), indeks FAISS untuk semantic search (top-k).  
   - **Re-ranking (opsional)**: CrossEncoder (bge-reranker-v2-m3) untuk mengurutkan konteks terpilih.  
   - **LLM**: sintesis jawaban dengan model instruksi (mis. Qwen2.5-1.5B-Instruct), jawaban hanya dari konteks yang di-retrieve.

---

## Cara Menjalankan

1. **Lingkungan**  
   Disarankan memakai **Python 3.8+** dan lingkungan virtual atau [Google Colab](https://colab.research.google.com/).

2. **Dependensi utama** (install sesuai kebutuhan per bagian):
   - Rule-based: `re` (standar), `nltk`
   - LLM: `transformers`, `torch`, `tokenizers>=0.13.3`
   - RAG: `pypdf`, `faiss-cpu`, `sentence-transformers`, `numpy`, `torch`, `transformers`

   Contoh (dalam notebook atau terminal):
   ```bash
   pip install nltk transformers torch pypdf faiss-cpu sentence-transformers
   pip install "tokenizers>=0.13.3"
   ```

3. **Menjalankan**  
   Buka `QA_ChatBot_18223004_18223098.ipynb` di Jupyter/VS Code/Cursor atau upload ke Google Colab, lalu jalankan sel secara berurutan. Untuk bagian RAG, pastikan path ke dokumen PDF (jika dipakai) sudah benar.

4. **Keluar dari chat**  
   Di mode interaktif, ketik `exit`, `quit`, atau `keluar`.

---

## Referensi

- [Python Regex (W3Schools)](https://www.w3schools.com/python/python_regex.asp)
- [Python `re` module](https://docs.python.org/3/library/re.html)
- [Build a simple chatbot with NLTK](https://www.analyticsvidhya.com/blog/2021/07/build-a-simple-chatbot-using-python-and-nltk/)

---

## Lisensi

Materi praktikum II4012 — gunakan sesuai kebijakan akademik ITB.
