# ai-app-review-analyzer

Project AI-Powered App Review & Sentiment Analyzer ini adalah sebuah sistem berbasis AI yang dirancang untuk mengekstrak dan menganalisis data ulasan aplikasi secara otomatis. Sistem ini mampu mengolah data mentah berupa teks ulasan pengguna, lalu mengklasifikasikannya menjadi informasi terstruktur seperti sentimen pengguna (Positif/Negatif/Netral), kategori masalah utama (Bug, UI/UX, atau Request Fitur), serta memberikan ringkasan keluhan.

Project ini dikembangkan secara khusus sebagai pemenuhan tugas praktik/Capstone dari course IBM SkillsBuild. Pembuatan project ini menjadi wadah implementasi langsung bagi mahasiswa Informatika untuk belajar merancang alur pemrosesan data (AI pipeline) menggunakan Large Language Model (LLM) secara visual menggunakan platform Langflow

Penjelasan Singkat Alur Sistem (Input → Proses → Output)
INPUT: File dataset berisi ulasan pengguna (dummydata.csv) diunggah melalui komponen Read File. Fitur Advanced Parser dimatikan agar sistem membacanya secara murni sebagai teks mentah, bukan sebagai dokumen berformat kompleks.

PROSES: Teks mentah tersebut mengalir masuk ke komponen Agent (didukung oleh LLM Gemini). Di saat yang bersamaan, Agent ini diberi "roh" dan instruksi kerja dari Prompt Template. Setelah data dianalisis, hasilnya dikirim ke Structured Output yang bertugas "memaksa" AI merapikan hasil analisis acak tersebut menjadi format tabel/kolom yang sudah kamu tentukan sebelumnya.

OUTPUT: Paket data yang sudah terstruktur rapi (berupa JSON dari kabel merah/pink) dikirim ke komponen Chat Output. Komponen ini kemudian menerjemahkan struktur data tersebut dan menampilkannya dengan cantik di layar antarmuka Playground siap untuk disalin atau diolah lebih lanjut ke dashboard analitik.

Target Users (Pengguna Utama)
1. Product Manager (PM)

Karakteristik: Berpikir strategis dan berfokus pada pengembangan produk.
Kebutuhan: Ringkasan sentimen kepuasan pengguna dan ide request fitur baru.
Konteks Penggunaan: Dipakai saat Sprint Planning untuk menentukan prioritas pengembangan fitur selanjutnya berdasarkan suara terbanyak.

2. App Developer (Software Engineer)

Karakteristik: Sangat teknis, fokus pada pemecahan masalah dan stabilitas aplikasi.
Kebutuhan: Identifikasi cepat untuk laporan kendala teknis (seperti bug atau force close).
Konteks Penggunaan: Dipakai untuk monitoring harian atau pasca-update agar tim bisa segera merilis perbaikan (patch).

3. UI/UX Designer

Karakteristik: Fokus pada pengalaman, visual, dan kemudahan interaksi pengguna.
Kebutuhan: Data spesifik mengenai keluhan tampilan, warna, atau navigasi yang membingungkan.
Konteks Penggunaan: Dipakai saat fase evaluasi desain untuk merancang ulang antarmuka yang lebih user-friendly.

4. Customer Support (CS) / Quality Assurance (QA)

Karakteristik: Berada di garis depan yang menangani langsung keluhan pengguna.
Kebutuhan: Otomatisasi untuk menyaring dan memilah ribuan feedback mentah dengan cepat.
Konteks Penggunaan: Dipakai sebagai filter otomatis mingguan untuk meneruskan laporan ke divisi yang tepat (ke Developer untuk bug, ke PM untuk fitur).
