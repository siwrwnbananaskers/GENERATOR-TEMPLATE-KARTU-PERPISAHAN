# 🎓 GENERATOR KARTU PERPISAHAN (Optimasi Layar LED & Cetak Premium) oleh WiraWebSolusi

Aplikasi berbasis web modern, premium, dan super responsif yang dikembangkan oleh **WiraWebSolusi** (Wira Web Solusi) untuk memproduksi Kartu Perpisahan Sekolah secara massal maupun satuan dengan cepat, indah, dan dioptimalkan khusus untuk tampilan layar proyektor / layar LED besar, serta cetak fisik beresolusi tinggi.

Aplikasi ini dibangun murni menggunakan teknologi **Client-Side (Sisi Klien)**, artinya **tidak ada data, foto, nama, atau NISN siswa yang diunggah ke internet/server luar**. Seluruh proses pengolahan data, pengunggahan foto, hingga pembuatan gambar kartu dilakukan langsung di memori komputer Anda sendiri.

---

## ✨ Fitur Utama

- **100% Aman & Privasi Terjaga (Offline Ready)**: Seluruh pemrosesan bersifat lokal. Tidak memerlukan backend, server, ataupun database online. Aman dari kebocoran data pribadi siswa.
- **Impor Massal via Excel (SheetJS)**: Impor ratusan data siswa sekaligus menggunakan file Excel (`.xlsx`). Sistem otomatis mendeteksi kolom NISN, Nama, dan Cita-Cita.
- **Pencocokan Foto Massal Cerdas**: Cukup unggah semua foto siswa sekaligus dari folder lokal komputer Anda. Sistem akan secara otomatis memetakan foto dengan data siswa berdasarkan nama file foto yang sesuai dengan **NISN** siswa (Contoh: `12345678.jpg`).
- **Kustomisasi Desain Real-Time**:
  - Ubah warna latar belakang (Primary Color).
  - Ubah warna teks nama, kutipan (quote), dan slogan sekolah.
  - Ubah warna emblem (badge) NISN.
  - Unggah logo sekolah kustom langsung di tempat.
  - Teks nama sekolah, slogan, dan teks kelulusan dapat langsung diedit di layar (*contenteditable*).
- **Kontrol Posisi Presisi & Drag-and-Drop (Keyboard Shortcuts)**: 
  - Geser posisi teks nama sekolah dan slogan secara presisi piksel demi piksel menggunakan tombol keyboard.
  - Geser posisi label hak cipta dan teks kelulusan secara dinamis sesuai kebutuhan layout visual Anda.
- **Ekspor Berkualitas Tinggi & Stabil (High-Fidelity Rendering)**:
  - **Efek Bayangan Sempurna (Symmetrical Layered Vector Shadow)**: Mengatasi keterbatasan mesin `html2canvas` dengan menerapkan 4 lapis bayangan vektor simetris di sekeliling foto siswa untuk hasil unduhan yang tebal, presisi, dan premium di semua sisi.
  - **Anti-Distorsi Rasio Foto (No-Squish Engine)**: Mengintegrasikan sistem penukar DOM otomatis berbasis CSS `background-size: cover` saat pemotretan berlangsung. Menghindari bug `html2canvas` yang membuat foto siswa terlihat **gepeng** akibat ketidakcocokan aspect ratio asli.
  - Ekspor satuan ke format **PNG beresolusi tinggi** (skala 2x, setara 2560x1440 piksel) siap cetak.
  - Ekspor massal otomatis ke dalam format **ZIP** untuk semua siswa yang fotonya telah berhasil dicocokkan.
- **Antarmuka Premium & Responsif (Freeze Header & Flex-Layout)**:
  - **Sticky Fixed Header**: Header navigasi tetap beku (*frozen*) di atas layar dengan efek `backdrop-blur-lg` saat menggulir (*scrolling*) ratusan daftar siswa.
  - **Optimasi Seluler Modern**: Restrukturisasi grid layout, pemendekan nama brand menjadi all-caps `GENERATOR KARTU PERPISAHAN`, dan penataan ulang Section 3 (Pilih & Edit Siswa) agar tampil rapi tanpa *overflow* di ponsel.
  - **Footer Premium**: Penataan ulang footer dengan mikro-animasi hover interaktif, indikator privasi aktif berbasis pulsasi, serta integrasi ikon tautan global persis di samping nama pengembang.
- **Penyimpanan Cache Pintar (LocalStorage)**: Seluruh pengaturan warna, logo kustom sekolah, pergeseran letak teks, dan data siswa tersimpan secara otomatis di browser Anda. Pengaturan tidak akan hilang bahkan jika halaman dimuat ulang (refresh) atau browser ditutup.

---

## 🛠️ Panduan Penggunaan

### 1. Memulai Aplikasi
Karena aplikasi ini murni Client-Side, Anda memiliki dua cara mudah untuk menjalankannya:
*   **Cara Langsung**: Cukup klik dua kali (double click) pada file `index.html` untuk membukanya di browser Google Chrome / Microsoft Edge Anda.
*   **Cara Lokal Server**: Jalankan perintah `npx http-server` pada direktori proyek, lalu buka tautan `http://localhost:8080` di browser.

### 2. Format File Excel Import
Buat file Excel dengan kolom-kolom minimal sebagai berikut agar sistem dapat membacanya secara otomatis:
| nisn | nama | cita_cita |
| :--- | :--- | :--- |
| 12345001 | ANDIKA PRATAMA | Ingin menjadi dokter spesialis anak |
| 12345002 | SITI NURHALIZA | Ingin menjadi astronot pertama Indonesia |

*Catatan: Pastikan penulisan header kolom menggunakan huruf kecil semua (`nisn`, `nama`, `cita_cita`).*

### 3. Penamaan File Foto Siswa
Agar sistem dapat memasangkan foto secara massal, beri nama file foto siswa sesuai dengan NISN mereka masing-masing yang tertulis di Excel.
*   Contoh: `12345001.jpg` atau `12345002.png`

### 4. Tombol Shortcut Keyboard
Untuk menyesuaikan letak elemen secara super presisi:
1.  Klik pada area teks nama sekolah ("SDN TEGALSARI"), Teks Kelulusan, atau Label Hak Cipta.
2.  Tahan tombol **`ALT`** pada keyboard Anda, lalu tekan tombol **`Arah Panah` (Atas / Bawah / Kiri / Kanan)** untuk menggeser posisi elemen secara presisi.

---

## 💻 Teknologi yang Digunakan

Aplikasi ini menggunakan kombinasi *modern minimal stack* untuk performa maksimal dan stabilitas rendering:
1.  **Tailwind CSS (v3)**: Untuk styling antarmuka modern, gelap, mewah, dan responsif.
2.  **Alpine.js**: Untuk reactivity state management yang ringan dan cepat.
3.  **html2canvas (v1.4.1)**: Untuk memotret (render) elemen DOM visual menjadi berkas gambar PNG resolusi tinggi siap cetak.
4.  **SheetJS (xlsx.mini)**: Untuk membaca dan memparsing file dokumen Excel langsung di browser.
5.  **JSZip**: Untuk mengompresi kumpulan file PNG kartu perpisahan secara massal menjadi satu file `.zip`.
6.  **FileSaver.js**: Untuk memicu unduhan file gambar tunggal maupun file ZIP massal ke sistem komputer pengguna.

---

## 🛡️ Kebijakan Privasi
Aplikasi ini tidak mengumpulkan, menyimpan, mengirimkan, atau membagikan data apa pun dari berkas Excel atau foto lokal Anda ke server internet mana pun. Aplikasi ini bersifat **100% luring (offline) dan pribadi**. Data Anda sepenuhnya milik Anda dan hanya berada di komputer Anda sendiri.
