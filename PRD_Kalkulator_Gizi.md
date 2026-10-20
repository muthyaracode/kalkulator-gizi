# PRD — Kalkulator & Pelacak Gizi Harian (NutriTrack)

| Item | Keterangan |
|---|---|
| **Nama Produk** | Kalkulator & Pelacak Gizi Harian (nama kerja: *NutriTrack*; nama final belum ditetapkan) |
| **Jenis Produk** | Web app responsif, mobile-first, dapat dipasang sebagai PWA |
| **Bahasa Antarmuka** | Bahasa Indonesia |
| **Sumber Desain** | `code.html` (prototipe layar Buku Harian) dan `DESIGN.md` (design system "NutriTrack Minimalist Monochrome") |
| **Versi Dokumen** | 1.0 (Draft) |
| **Tanggal** | 20 Oktober 2026 |

> **Catatan cara membaca dokumen.** Bagian yang berasal langsung dari desain ditandai **[Desain]**. Bagian yang saya tambahkan sebagai rekomendasi karena belum ada di desain ditandai **[Usulan]**. Hal yang perlu keputusan Anda dikumpulkan di bagian 14.

---

## 1. Ringkasan Produk

Aplikasi web untuk mencatat makanan harian dan menghitung asupan **kalori serta makronutrien (protein, karbohidrat, lemak)** terhadap target harian pengguna. Fokusnya pada konteks Indonesia: waktu makan *Sarapan, Makan Siang, Makan Malam, Camilan*, dan database makanan lokal (nasi, tempe, tahu, soto, dan sebagainya).

Karakter produk menurut desain: **tenang, minimalis, monokrom gelap**, dan nyaman dipakai satu tangan di ponsel. Pengguna melihat sisa kalori hari ini, progres makro, daftar makanan per waktu makan, lalu menambah catatan baru dalam beberapa ketukan.

### 1.1 Masalah yang Diselesaikan
- Aplikasi pelacak kalori populer sering ramai, bergaya gamifikasi, dan database makanan Indonesianya lemah.
- Pengguna sulit tahu "sisa jatah" kalori dan makro mereka saat sedang memilih makanan.
- Mencatat makanan terasa merepotkan sehingga orang berhenti setelah beberapa hari.

### 1.2 Tujuan
1. Mencatat satu makanan dalam **≤ 3 ketukan / ≤ 10 detik** untuk makanan yang sering dimakan.
2. Menampilkan **sisa kalori dan progres makro secara real-time** setelah setiap catatan.
3. Menyediakan database makanan Indonesia yang cukup untuk kebiasaan makan sehari-hari.
4. Memberikan pengalaman visual yang konsisten dengan design system monokrom.

### 1.3 Metrik Keberhasilan [Usulan]

| Metrik | Target awal |
|---|---|
| Waktu rata-rata mencatat 1 makanan | ≤ 10 detik |
| Pengguna yang mencatat ≥ 1 makanan di hari pertama | ≥ 60% |
| Retensi hari ke-7 | ≥ 25% |
| Pencarian makanan yang menemukan hasil relevan | ≥ 90% |
| Skor Lighthouse (Performance / Accessibility) di ponsel | ≥ 90 / ≥ 95 |

### 1.4 Bukan Tujuan (Out of Scope MVP)
- Diagnosis atau saran medis, termasuk rencana diet untuk kondisi penyakit tertentu.
- Pemindai barcode dan pengenalan makanan lewat foto.
- Fitur sosial, komunitas, dan gamifikasi.
- Integrasi perangkat wearable.
- Aplikasi native iOS/Android (PWA dianggap cukup untuk MVP).

---

## 2. Target Pengguna

| Persona | Kebutuhan | Fitur Kunci |
|---|---|---|
| **Pemula diet / penurunan berat badan** | Tahu batas kalori harian dan sisa jatah | Target kalori, sisa kalori, tip makro |
| **Orang yang membangun otot** | Mengejar target protein | Progres protein, tip protein, riwayat |
| **Orang yang menjaga pola makan sehat** | Mencatat ringan tanpa ribet | Pencarian cepat, pilihan populer, favorit |
| **Mahasiswa gizi / praktisi** (sekunder) | Hitung gizi bahan makanan | Kalkulator estimasi gizi per gram |

---

## 3. Lingkup Rilis

| Fase | Isi |
|---|---|
| **MVP (v1.0)** | Buku Harian lengkap (sesuai desain), pencarian makanan, tambah/hapus catatan, onboarding target kalori, penyimpanan lokal |
| **v1.1** | Halaman Analisis (tren mingguan/bulanan), edit catatan, favorit, riwayat makanan |
| **v1.2** | Eksplor (database & resep), makanan buatan sendiri, mikronutrien, air minum |
| **v2.0** | Akun & sinkronisasi antarperangkat, ekspor data, layout tablet/desktop penuh |

---

## 4. Inventaris Layar

### 4.1 Layar yang Sudah Ada di Desain [Desain]

**Layar: Buku Harian** (tab aktif), terdiri dari urutan berikut dari atas ke bawah:

1. **Top app bar**: ikon kalender, judul "Nutrisi Harian", ikon *tune* (pengaturan), avatar inisial pengguna (contoh "AD").
2. **Pemilih tanggal mingguan**: label tanggal lengkap (contoh "Rabu, 25 Oktober 2023"), tombol "Bulan Ini", dan strip 7 hari (Sen–Min) dengan hari aktif disorot putih.
3. **Kartu ringkasan harian (hero)**:
   - "Anggaran Energi Harian": angka besar **sisa kalori** dan teks "kkal tersisa".
   - "Target Konsumsi" di kanan atas.
   - Bar progres kalori dengan label "kkal terkonsumsi" dan persentase.
   - Tiga kartu mini makro: Protein, Karbo, Lemak (nilai saat ini / target, persentase, bar).
4. **Pencarian Cepat Makanan ("Kalkulator Langsung")**: kolom pencarian, dropdown porsi, tombol "Catat", dan chip pilihan populer (Nasi Putih, Dada Ayam, Telur Rebus, Tempe Bacem, Susu Kedelai).
5. **Daftar Makanan Harian**: kartu per waktu makan (Sarapan, Makan Siang, Makan Malam) berisi target, total kkal, daftar item (nama, chip P/K/L, kkal, tombol hapus), dan tombol "Tambah Makanan …".
6. **Kartu Camilan (empty state)**: border putus-putus, teks "Belum ada makanan dicatat", tombol "+ Tambah".
7. **Kartu "Tips Keseimbangan Makro"**: saran otomatis berdasarkan makro yang belum tercapai.
8. **FAB (+)** untuk catat cepat.
9. **Bottom sheet "Tambah ke [waktu makan]"**: nama makanan, jumlah, satuan (Gram, Porsi, Potong, Mangkok), kartu "Estimasi Gizi" (kkal + P/K/L), tombol Batal dan Simpan Entri.
10. **Toast** umpan balik ("Berhasil dicatat ke jurnal harian!").
11. **Bottom navigation**: Buku Harian, Analisis, Eksplor, Profil.

### 4.2 Layar yang Belum Didesain tetapi Dibutuhkan [Usulan]

| Layar | Alasan |
|---|---|
| **Onboarding & hitung target** | Target 2.100 kkal dan makro harus berasal dari data pengguna |
| **Analisis** | Ada di navigasi, belum ada desainnya |
| **Eksplor** | Ada di navigasi, belum ada desainnya |
| **Profil & Pengaturan** | Ada di navigasi; ikon *tune* juga mengarah ke pengaturan |
| **Hasil pencarian makanan** | Dropdown/daftar saran saat mengetik |
| **Edit target & porsi per waktu makan** | Target per waktu makan (~500/~800/~600) perlu bisa diatur |
| **Kalender bulanan** | Tombol "Bulan Ini" membuka tampilan bulan |
| **Kondisi error, loading, offline** | Belum ada di desain |

---

## 5. Kebutuhan Fungsional

Prioritas memakai MoSCoW: **M**ust, **S**hould, **C**ould.

### 5.1 Onboarding & Target Harian [Usulan]

| ID | Kebutuhan | Prioritas |
|---|---|---|
| FR-01 | Pengguna mengisi jenis kelamin, usia, tinggi, berat, tingkat aktivitas, dan tujuan (turun / jaga / naik berat badan) | M |
| FR-02 | Sistem menghitung target kalori dan target makro dari data tersebut (lihat bagian 6) | M |
| FR-03 | Pengguna dapat menimpa target kalori dan makro secara manual | M |
| FR-04 | Pengguna dapat melewati onboarding dengan target bawaan | S |
| FR-05 | Tampilkan penafian bahwa hasil hanya estimasi dan bukan saran medis | M |

### 5.2 Buku Harian & Navigasi Tanggal [Desain]

| ID | Kebutuhan | Prioritas |
|---|---|---|
| FR-10 | Tampilkan strip 7 hari; mengetuk hari mengganti data seluruh layar ke tanggal itu | M |
| FR-11 | Label tanggal lengkap dalam format Indonesia (hari, tanggal, bulan, tahun) | M |
| FR-12 | Tombol "Bulan Ini" membuka kalender bulanan untuk lompat ke tanggal lain | S |
| FR-13 | Geser strip ke minggu sebelumnya/berikutnya | S |

### 5.3 Ringkasan Kalori & Makro [Desain]

| ID | Kebutuhan | Prioritas |
|---|---|---|
| FR-20 | Hitung **Sisa kalori = Target − Total terkonsumsi** dan tampilkan sebagai angka utama | M |
| FR-21 | Bar progres kalori menampilkan persen terkonsumsi (dibatasi visual 100%) | M |
| FR-22 | Tiga kartu makro menampilkan nilai saat ini / target (gram), persentase, dan bar | M |
| FR-23 | Seluruh angka diperbarui langsung setelah catatan ditambah atau dihapus | M |
| FR-24 | Jika terkonsumsi > target, ubah label menjadi "kkal melebihi target" dan tampilkan selisihnya; jangan memakai warna alarm yang bertentangan dengan gaya monokrom | M |
| FR-25 | Angka memakai *tabular numerals* agar tidak bergeser saat berubah | M |

### 5.4 Pencatatan Makanan

| ID | Kebutuhan | Prioritas |
|---|---|---|
| FR-30 | **Pencarian cepat** dengan saran otomatis (autocomplete) dari database makanan [Desain: kolom ada; saran hasil: Usulan] | M |
| FR-31 | Dropdown porsi cepat (0,5 / 1 / 1,5 / 2 porsi dengan padanan gram) [Desain] | M |
| FR-32 | Chip pilihan populer yang mengisi kolom pencarian [Desain] | M |
| FR-33 | Tombol "Catat" menyimpan item; jika kolom kosong tampilkan pesan "Masukkan nama makanan terlebih dahulu" [Desain] | M |
| FR-34 | Tombol "Tambah" di tiap kartu waktu makan dan FAB membuka bottom sheet dengan judul "Tambah ke [waktu makan]" [Desain] | M |
| FR-35 | Bottom sheet berisi nama makanan, jumlah, satuan (Gram, Porsi, Potong, Mangkok), dan kartu **Estimasi Gizi** yang berubah langsung saat jumlah/satuan diubah [Desain] | M |
| FR-36 | Tombol "Simpan Entri" menyimpan catatan, menutup sheet, dan menampilkan toast sukses [Desain] | M |
| FR-37 | Tombol "Batal" dan tombol tutup menutup sheet tanpa menyimpan [Desain] | M |
| FR-38 | Hapus catatan lewat ikon tempat sampah, dengan opsi **Urungkan (undo)** di toast selama beberapa detik [Hapus: Desain; Undo: Usulan] | M |
| FR-39 | Edit jumlah/satuan catatan yang sudah tersimpan | S |
| FR-40 | Salin catatan dari hari lain ("ulangi makan kemarin") | C |
| FR-41 | Tandai makanan sebagai favorit dan tampilkan chip "Favorit" dan "Riwayat" | S |
| FR-42 | Tambah makanan buatan sendiri (nama, kkal, P, K, L per 100 g atau per porsi) bila tidak ada di database | S |

### 5.5 Waktu Makan [Desain]

| ID | Kebutuhan | Prioritas |
|---|---|---|
| FR-50 | Empat kategori tetap: Sarapan (Pagi), Makan Siang, Makan Malam, Camilan & Tambahan | M |
| FR-51 | Tiap kartu menampilkan total kkal waktu makan dan target (contoh "Target: ~500 kkal") | M |
| FR-52 | Kategori tanpa catatan menampilkan *empty state* bergaya putus-putus | M |
| FR-53 | Pencatatan dari pencarian cepat otomatis masuk ke waktu makan sesuai jam saat ini (aturan di bagian 14) | S |

### 5.6 Tips Makro [Desain]

| ID | Kebutuhan | Prioritas |
|---|---|---|
| FR-60 | Tampilkan satu tip berdasarkan makro dengan capaian terendah, berisi sisa gram dan contoh makanan lokal (contoh desain: "sisa 45g protein → edamame atau tempe rebus") | S |
| FR-61 | Tip disembunyikan bila semua makro sudah ≥ 90% atau belum ada catatan sama sekali | S |
| FR-62 | Tip tidak boleh bernada menghakimi atau menganjurkan pembatasan ekstrem | M |

### 5.7 Analisis (v1.1) [Usulan]

| ID | Kebutuhan | Prioritas |
|---|---|---|
| FR-70 | Grafik kalori 7 dan 30 hari terhadap target | S |
| FR-71 | Rata-rata makro per hari dan komposisi persentase | S |
| FR-72 | Catat berat badan dan tampilkan tren | C |

### 5.8 Profil & Pengaturan [Usulan]

| ID | Kebutuhan | Prioritas |
|---|---|---|
| FR-80 | Ubah data tubuh dan tujuan, target dihitung ulang dengan konfirmasi | M |
| FR-81 | Ekspor data (CSV/JSON) dan hapus seluruh data | S |
| FR-82 | Satuan dan format angka mengikuti Indonesia (`2.100 kkal`, desimal koma) | M |

---

## 6. Aturan Perhitungan [Usulan]

Angka di prototipe konsisten secara internal: 250 + 155 + 15 = 420 (Sarapan), 245 + 215 + 120 + 100 = 680 (Siang), 350 (Malam), total **1.450**, dan 2.100 − 1.450 = **650 kkal tersisa**. Aturan berikut menjaga konsistensi tersebut.

### 6.1 Gizi per Catatan
```
gram_efektif = jumlah × gram_per_satuan
kkal   = kkal_per_100g × gram_efektif / 100
protein = protein_per_100g × gram_efektif / 100   (sama untuk karbo, lemak)
```
- Simpan nilai desimal; **tampilkan** kkal dan gram sebagai bilangan bulat.
- Total harian dijumlahkan dari nilai tersimpan lalu dibulatkan **sekali** di akhir, bukan menjumlahkan angka yang sudah dibulatkan.
- Setiap makanan punya tabel konversi satuan (Gram, Porsi, Potong, Mangkok) ke gram.

### 6.2 Target Kalori
- **BMR** dengan rumus Mifflin-St Jeor:
  - Pria: `10×berat(kg) + 6,25×tinggi(cm) − 5×usia + 5`
  - Wanita: `10×berat(kg) + 6,25×tinggi(cm) − 5×usia − 161`
- **TDEE** = BMR × faktor aktivitas (1,2 / 1,375 / 1,55 / 1,725 / 1,9).
- **Target** = TDEE disesuaikan tujuan (default: turun −15%, jaga 0%, naik +10%), dengan batas bawah aman (misalnya tidak di bawah 1.200 kkal untuk wanita dan 1.500 kkal untuk pria) dan peringatan jika pengguna menimpanya lebih rendah.

### 6.3 Target Makro
- Konversi energi: protein 4 kkal/g, karbohidrat 4 kkal/g, lemak 9 kkal/g.
- Contoh target pada desain (P 140 g, K 220 g, L 65 g) setara ±2.025 kkal, yaitu ±96% dari 2.100 kkal. Pembagian bawaan perlu ditetapkan agar total makro mendekati 100% target kalori (lihat bagian 14).
- Persentase kartu = nilai saat ini / target × 100, dibulatkan, bar dibatasi 100%.

### 6.4 Target per Waktu Makan
Desain menunjukkan ~500 / ~800 / ~600 kkal untuk Sarapan / Siang / Malam (total 1.900). Sisa ±200 kkal secara implisit untuk Camilan. Aturan alokasi bawaan perlu dikonfirmasi (bagian 14).

---

## 7. Model Data [Usulan]

| Entitas | Atribut utama |
|---|---|
| **Pengguna** | id, nama/inisial, jenis kelamin, tanggal lahir, tinggi, berat, tingkat aktivitas, tujuan |
| **Target** | id pengguna, kkal, protein_g, karbo_g, lemak_g, alokasi per waktu makan, berlaku sejak |
| **Makanan** | id, nama, kategori, kkal/100g, protein/100g, karbo/100g, lemak/100g, sumber data, status verifikasi |
| **Satuan Makanan** | id makanan, nama satuan (porsi, potong, mangkok), gram per satuan |
| **Catatan Makan** | id, tanggal, waktu makan, id makanan atau teks bebas, jumlah, satuan, gram efektif, snapshot kkal/P/K/L, dibuat pada |
| **Favorit** | id pengguna, id makanan |
| **Makanan Kustom** | seperti Makanan, dimiliki satu pengguna |

Catatan: simpan **snapshot nilai gizi** pada Catatan Makan agar riwayat tidak berubah bila data makanan diperbarui.

---

## 8. Kebutuhan UI/UX

### 8.1 Design Tokens [Desain]

| Aspek | Ketentuan |
|---|---|
| **Gaya** | Minimalisme disiplin, monokrom editorial, tema gelap sebagai default |
| **Font** | Plus Jakarta Sans untuk semua peran |
| **Ikon** | Material Symbols Outlined |
| **Skala teks** | display-lg 40/48, display-lg-mobile 32/40, headline-lg 28, headline-md 22, headline-sm 18, body-lg 16, body-md 14, body-sm 12, label-lg 14, label-md 12, label-sm 10, metric-numeral 24 |
| **Warna** | Permukaan bertingkat gelap, teks utama putih/abu terang, aksen utama putih; diferensiasi makro lewat nilai terang-gelap (Protein paling terang, Karbo menengah, Lemak paling redup) |
| **Spasi** | Margin 1,25 rem; gutter 1 rem; padding kartu 16 px (ringkas) atau 24 px (ringkasan utama); ritme 8 pt |
| **Bentuk** | Kartu membulat, bar progres berujung penuh (pill), tombol utama bentuk pill, chip sudut halus |
| **Kedalaman** | Pelapisan tonal dan garis tipis 1 px, bukan bayangan tebal; bayangan lembut hanya untuk elemen melayang (bottom sheet, FAB) |
| **Tombol utama** | Latar putih/abu sangat terang, teks gelap tebal, efek tekan `scale(0.98)` |

### 8.2 Perilaku Responsif [Desain]

| Lebar | Layout |
|---|---|
| **< 640 px** | Satu kolom, margin 1,25 rem, bottom navigation dan FAB, bottom sheet dari bawah |
| **640–1024 px** | Dua kolom: kiri ringkasan harian dan makro, kanan daftar makanan; gutter 1,5 rem |
| **> 1024 px** | Grid 12 kolom, lebar konten maksimum 1.080 px, sidebar navigasi dan tren mingguan di kiri, catatan harian di tengah, rail mikronutrien dan hidrasi di kanan |

Pada layar lebar, bottom sheet berubah menjadi dialog di tengah layar (sudah ada di prototipe lewat kelas `sm:`).

### 8.3 Status Antarmuka yang Wajib Ada [Usulan]
- **Loading**: kerangka (skeleton) pada kartu ringkasan dan daftar.
- **Kosong**: sudah ada untuk Camilan; tambahkan untuk hari tanpa catatan sama sekali dengan ajakan mencatat.
- **Error**: gagal memuat database makanan, pencarian tanpa hasil (tawarkan "Tambah makanan sendiri").
- **Offline**: pencatatan tetap bisa, indikator halus bahwa data akan disinkronkan.
- **Konfirmasi**: hapus mendapat opsi urungkan; reset data mendapat dialog konfirmasi.

### 8.4 Aksesibilitas
- Semua tombol ikon memiliki label aksesibel (`aria-label`); beberapa ikon di prototipe (kalender, tune, hapus) hanya memakai ikon.
- Target sentuh minimum 44 × 44 px (ikon hapus dan tombol bar atas di prototipe lebih kecil dari itu).
- Kontras teks ≥ 4,5:1; teks `label-sm` 10 px berisiko sulit dibaca, pertimbangkan minimum 11–12 px untuk teks penting.
- **Jangan menonaktifkan zoom**: prototipe memakai `user-scalable=no` dan `maximum-scale=1.0`, sebaiknya dihapus.
- Navigasi keyboard dan *focus ring* terlihat; bottom sheet menjebak fokus dan dapat ditutup dengan `Esc`.
- Informasi tidak hanya lewat warna; karena palet monokrom, status selalu disertai teks atau angka.
- Hormati `prefers-reduced-motion`.

### 8.5 Teks Antarmuka
Semua teks dalam Bahasa Indonesia yang ringkas dan hangat (contoh dari desain: "kkal tersisa", "Belum ada makanan dicatat", "Berhasil dicatat ke jurnal harian!"). Singkatan P/K/L dijelaskan melalui *tooltip* atau legenda saat pertama kali muncul.

---

## 9. Kebutuhan Non-Fungsional

| Aspek | Target |
|---|---|
| **Performa** | LCP ≤ 2,5 detik pada 4G; respons input (hitung estimasi) ≤ 100 ms; pencarian makanan ≤ 300 ms |
| **Ukuran** | Bundel JS awal ≤ 200 KB gzip (tidak memuat database penuh di awal) |
| **Offline** | Buku Harian dan pencatatan berfungsi tanpa internet (PWA, service worker) |
| **Kompatibilitas** | Dua versi terbaru Chrome, Safari, Edge, Firefox; Android 9+ dan iOS 15+ |
| **Privasi** | Data kesehatan bersifat sensitif; kumpulkan seminimal mungkin, jelaskan penggunaan data, sediakan ekspor dan hapus data (selaras prinsip UU PDP) |
| **Keamanan** | HTTPS, validasi input di klien dan server, tanpa menyimpan data sensitif di URL |
| **Ketersediaan** | ≥ 99,5% jika memakai backend |
| **Observabilitas** | Pelaporan error dan analitik pemakaian anonim dengan persetujuan |
| **Pengelolaan font/aset** | Muat font dan ikon secara efisien; prototipe memuat Tailwind lewat CDN, untuk produksi ganti dengan *build* terkompilasi |

---

## 10. Arsitektur & Teknologi [Usulan]

Prototipe memakai HTML + Tailwind CSS + JavaScript, sehingga jalur paling mulus adalah mempertahankan Tailwind dan token desain yang sama.

### 10.1 Opsi Tumpukan

| Lapisan | Rekomendasi | Alasan |
|---|---|---|
| **Frontend** | Vite + React + TypeScript + Tailwind CSS | Token desain sudah berbasis Tailwind; komponen mudah dipecah |
| **State** | Zustand atau React Context | Cukup untuk skala MVP |
| **Penyimpanan MVP** | IndexedDB (mis. lewat Dexie) | Offline-first, tanpa server, cepat dibangun |
| **Backend (v2)** | FastAPI (Python) + PostgreSQL | Selaras dengan keahlian Python Anda; mudah dikembangkan bertahap |
| **Autentikasi (v2)** | Email + OAuth Google | Sinkronisasi antarperangkat |
| **PWA** | Workbox / vite-plugin-pwa | Instalasi ke layar utama dan cache offline |
| **Hosting** | Vercel / Netlify / Cloudflare Pages (frontend) | Gratis untuk tahap awal |
| **Pengujian** | Vitest, Testing Library, Playwright, Lighthouse CI | Unit, komponen, dan uji alur |

> **Strategi bertahap.** MVP dibuat *local-first* tanpa backend agar cepat rilis dan privasi kuat. Backend dan akun ditambahkan di v2 setelah alur utama terbukti dipakai.

### 10.2 Struktur Komponen (dari desain)
`TopAppBar`, `WeekStrip`, `SummaryCard` (`CalorieBar`, `MacroCard`), `QuickSearch` (`FoodChips`), `MealCard` (`FoodRow`, `EmptyMeal`), `TipCard`, `Fab`, `AddFoodSheet` (`EstimateCard`), `Toast`, `BottomNav`.

### 10.3 Sumber Data Makanan
- Kandidat utama untuk makanan Indonesia: **Tabel Komposisi Pangan Indonesia (TKPI)** dari Kementerian Kesehatan RI. *Lisensi dan ketentuan penggunaan perlu diverifikasi sebelum dipakai.*
- Pelengkap untuk bahan umum internasional: **USDA FoodData Central**.
- Masakan jadi (soto, tempe bacem, tumis) memerlukan kurasi manual atau estimasi resep standar; tandai dengan status "estimasi".
- Tampilkan sumber data dan label bahwa nilai gizi adalah perkiraan.

---

## 11. Alur Pengguna Utama

**A. Pengguna baru**
Buka aplikasi → onboarding (data tubuh, aktivitas, tujuan) → lihat target yang dihitung → ubah bila perlu → masuk Buku Harian kosong.

**B. Catat cepat**
Buku Harian → ketik/pilih chip makanan → pilih porsi → "Catat" → toast sukses → sisa kalori dan makro berubah.

**C. Catat ke waktu makan tertentu**
Ketuk "Tambah Makanan Siang" → bottom sheet "Tambah ke Makan Siang" → isi nama, jumlah, satuan → lihat estimasi gizi langsung → "Simpan Entri" → kartu Makan Siang diperbarui.

**D. Hapus catatan**
Ketuk ikon hapus → item hilang → toast dengan "Urungkan" → total diperbarui.

**E. Lihat hari lain**
Ketuk hari pada strip mingguan atau "Bulan Ini" → seluruh layar berpindah ke tanggal itu.

---

## 12. Kriteria Penerimaan (MVP)

- [ ] Dengan data contoh desain, layar menampilkan **650 kkal tersisa** dari target 2.100 dan 1.450 terkonsumsi (69%).
- [ ] Menambah "Nasi Putih 100 g" menambah kkal, karbo, protein, dan lemak sesuai database dan memperbarui semua angka tanpa memuat ulang halaman.
- [ ] Menghapus catatan memperbarui total waktu makan, sisa kalori, bar, dan makro; opsi urungkan mengembalikannya.
- [ ] Estimasi gizi di bottom sheet berubah real-time saat jumlah atau satuan diubah.
- [ ] Saat kolom pencarian kosong, "Catat" menampilkan pesan peringatan dan tidak menyimpan apa pun.
- [ ] Jika terkonsumsi melebihi target, tampilan tetap jelas dan tidak rusak (tidak ada angka negatif yang membingungkan; bar tidak melewati 100%).
- [ ] Mengganti tanggal menampilkan data tanggal tersebut; tanggal tanpa data menampilkan empty state.
- [ ] Data tetap ada setelah memuat ulang halaman dan saat offline.
- [ ] Layout benar pada 360 px, 768 px, dan 1280 px; tidak ada *scroll* horizontal selain strip hari dan chip.
- [ ] Seluruh kontrol dapat dioperasikan dengan keyboard; zoom pengguna tidak diblokir.
- [ ] Lighthouse mobile: Performance ≥ 90 dan Accessibility ≥ 95.
- [ ] Format angka dan tanggal mengikuti Indonesia.

---

## 13. Rencana Pengujian

| Jenis | Cakupan |
|---|---|
| **Unit** | Rumus BMR/TDEE, konversi satuan, penjumlahan harian, pembulatan, kasus melebihi target |
| **Komponen** | Kartu ringkasan, MealCard (isi/kosong), bottom sheet, toast |
| **End-to-end** | Alur A–E pada bagian 11 |
| **Responsif & lintas peramban** | 360/768/1280 px; Chrome, Safari iOS, Firefox, Edge |
| **Aksesibilitas** | Audit otomatis, uji pembaca layar dasar, uji keyboard |
| **Offline/PWA** | Pencatatan tanpa jaringan, instal ke layar utama |
| **Kebenaran data** | Sampel 50 makanan populer diverifikasi terhadap sumber |

---

## 14. Pertanyaan Terbuka & Temuan pada Desain

### 14.1 Ketidakkonsistenan antara `code.html` dan `DESIGN.md`

| Hal | `code.html` | `DESIGN.md` | Saran |
|---|---|---|---|
| **Target & sisa kalori** | Target 2.100, sisa 650 | Rumus contoh 2.200 − 1.450 = 750 | Tetapkan satu angka contoh (disarankan 2.100/650) |
| **Warna latar** | `#131316` (surface gelap bernuansa biru) | Teks menyebut kanvas `#09090B` dan kartu `#18181B` (zinc) | Pilih satu palet dan sinkronkan |
| **Radius kartu** | `xl` = 0,75 rem (12 px) | Kartu 16 px, kartu hero 24 px | Samakan ke nilai di DESIGN.md |
| **Padding kartu** | Kelas `p- space-md` tidak valid, sehingga padding tidak terterap | 16 px / 24 px | Perbaiki saat implementasi |
| **Input porsi** | `input number` biasa | Stepper `+`/`−` dalam kapsul | Implementasikan stepper |
| **Filter chip** (Semua, Favorit, Riwayat, Resep) | Tidak ada | Ada di komponen | Tentukan layar tempat chip ini muncul |
| **Warna makro** | Protein putih, Karbo abu terang, Lemak abu redup | Protein `#E4E4E7`, Karbo `#A1A1AA`, Lemak `#52525B` | Selaras secara konsep; samakan nilainya |
| **Viewport** | `user-scalable=no` | — | Hapus demi aksesibilitas |
| **Label tab** | "Buku Harian" | Judul bar atas "Nutrisi Harian" | Samakan penamaan |

### 14.2 Keputusan yang Dibutuhkan dari Anda
1. **Nama produk final**: Kalkulator Gizi, NutriTrack, atau nama lain?
2. **Persistensi MVP**: cukup penyimpanan lokal (tanpa akun), atau akun sejak awal?
3. **Sumber database makanan**: TKPI, USDA, kurasi sendiri, atau gabungan? Berapa jumlah makanan awal?
4. **Alokasi target per waktu makan**: persentase tetap, dapat diatur pengguna, atau otomatis?
5. **Pencatatan dari pencarian cepat**: masuk ke waktu makan yang mana (berdasarkan jam, atau tanya pengguna)?
6. **Tema terang**: apakah perlu disediakan selain tema gelap?
7. **Makro tambahan**: apakah serat, gula, dan natrium masuk MVP atau v1.2?
8. **Tujuan produk**: portofolio/belajar, rilis publik gratis, atau komersial? Ini menentukan kebutuhan privasi, hukum, dan skala.

---

## 15. Roadmap Pengembangan [Usulan]

| Fase | Isi | Estimasi (paruh waktu) |
|---|---|---|
| **0. Persiapan** | Keputusan bagian 14, setup proyek, token desain di Tailwind | 3–4 hari |
| **1. Data & Logika** | Skema data, dataset makanan awal, modul perhitungan + unit test | 1–1,5 minggu |
| **2. Buku Harian** | Top bar, strip tanggal, kartu ringkasan, kartu waktu makan | 1–1,5 minggu |
| **3. Pencatatan** | Pencarian, bottom sheet, estimasi gizi, hapus/urungkan, toast | 1–1,5 minggu |
| **4. Onboarding & Profil** | Hitung target, pengaturan, ekspor/hapus data | 1 minggu |
| **5. Responsif & PWA** | Layout tablet/desktop, offline, instal ke layar utama | 1 minggu |
| **6. QA & Aksesibilitas** | Uji lintas perangkat, audit Lighthouse, perbaikan | 1 minggu |
| **7. Rilis MVP** | Deploy, pemantauan, perbaikan awal | 2–3 hari |

**Total MVP ± 7–9 minggu** untuk satu pengembang paruh waktu. Analisis, Eksplor, akun, dan sinkronisasi menyusul di v1.1 hingga v2.0.

---

## 16. Risiko & Mitigasi

| Risiko | Dampak | Mitigasi |
|---|---|---|
| Data gizi masakan Indonesia tidak lengkap atau bervariasi | Estimasi kurang akurat, kepercayaan turun | Mulai dari TKPI, beri label "estimasi", izinkan koreksi dan makanan kustom |
| Pengguna memakai target terlalu rendah | Risiko kesehatan, reputasi | Batas bawah aman, penafian, hindari bahasa yang mendorong restriksi ekstrem |
| Pencatatan terasa melelahkan | Retensi rendah | Chip populer, favorit, riwayat, "ulangi kemarin" |
| Data kesehatan pribadi | Isu privasi/regulasi | Local-first, minimalkan data, ekspor/hapus, kebijakan privasi jelas |
| Ketidakkonsistenan desain terbawa ke kode | Tampilan tidak seragam | Selesaikan tabel 14.1 sebelum implementasi |
| Cakupan melebar (analisis, resep, sosial) | MVP molor | Pegang ruang lingkup bagian 3 dan 1.4 |
| Pembulatan membuat total tidak cocok | Kebingungan pengguna | Bulatkan sekali di akhir (bagian 6.1) |

---

## 17. Lampiran: Data Contoh dari Desain

**Ringkasan hari (Rabu, 25 Oktober 2023)**

| | Nilai |
|---|---|
| Target kalori | 2.100 kkal |
| Terkonsumsi | 1.450 kkal (69%) |
| Sisa | 650 kkal |
| Protein | 95 / 140 g (68%) |
| Karbohidrat | 160 / 220 g (72%) |
| Lemak | 42 / 65 g (64%) |

**Catatan makan contoh**

| Waktu makan | Makanan | kkal | P / K / L (g) |
|---|---|---|---|
| Sarapan | Oatmeal Pisang & Madu | 250 | 7 / 48 / 3 |
| Sarapan | 2 Telur Rebus | 155 | 13 / 1 / 10 |
| Sarapan | Kopi Hitam (Tanpa Gula) | 15 | 0 / 1 / 0 |
| Makan Siang | Dada Ayam Panggang 150 g | 245 | 46 / 0 / 5 |
| Makan Siang | Nasi Merah (1 porsi / 150 g) | 215 | 5 / 45 / 2 |
| Makan Siang | Tumis Brokoli & Wortel | 120 | 4 / 12 / 6 |
| Makan Siang | Tempe Bacem (1 potong) | 100 | 7 / 8 / 4 |
| Makan Malam | Salad Sayur Salmon Panggang | 350 | 28 / 8 / 18 |
| Camilan | (kosong) | 0 | — |

**Item populer (chip cepat):** Nasi Putih, Dada Ayam Panggang, Telur Rebus, Tempe Bacem, Susu Kedelai.

**Contoh estimasi di bottom sheet:** ~185 kkal, P 18 g, K 2 g, L 11 g untuk 100 g.

### Glosarium
- **kkal**: kilokalori, satuan energi pangan.
- **Makro**: protein, karbohidrat, lemak.
- **BMR / TDEE**: kebutuhan energi basal / total harian.
- **PWA**: *Progressive Web App*, web app yang dapat dipasang dan bekerja offline.
- **Local-first**: data disimpan di perangkat pengguna terlebih dahulu.

---

*Penafian produk: perhitungan gizi dalam aplikasi ini adalah estimasi untuk informasi umum dan bukan pengganti saran dokter atau ahli gizi.*
