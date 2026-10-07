# SkillSwap

**Learn a Skill. Share a Skill.**

Prototype marketplace multi-page: 24 halaman HTML asli, CSS, dan vanilla JavaScript. Tidak memerlukan Node.js, npm, framework, database, atau backend untuk menjalankan website.

## Mulai cepat

1. Ekstrak ZIP.
2. Buka `index.html` di browser desktop.
3. Klik **Log in → Try demo account** untuk menggunakan Athira, atau buat akun baru.
4. Pilih Learn atau Teach. Akun yang sama bisa berpindah mode lewat header atau halaman Profile.

Setelah demo pertama kali dibuat, login manual menggunakan username `athira` dan password `demo123` juga bisa. Jangan masukkan password asli: autentikasi ini hanya simulasi lokal. Google sign-in menggunakan dialog simulasi dan tidak menghubungkan akun Google.

Semua file menggunakan path relatif dan tidak memakai fetch/module imports. Tampilan dapat dibuka langsung dari file. Namun, kebijakan localStorage untuk `file://` berbeda antar-browser, khususnya di perangkat mobile. Untuk perpindahan halaman dengan data konsisten, gunakan GitHub Pages. Jika penyimpanan browser tidak tersedia, aplikasi menampilkan pesan error.

## Upload ke GitHub Pages

1. Buat repository GitHub bernama `skillswap` (public jika menggunakan GitHub Free).
2. Upload **isi folder hasil ekstrak**, bukan ZIP atau folder pembungkusnya. `index.html` harus berada di root repository bersama `css`, `js`, `assets`, dan `instructor`.
3. Commit ke branch `main`.
4. Buka **Settings → Pages → Build and deployment**.
5. Pilih **Deploy from a branch**, branch **main**, folder **/(root)**, lalu **Save**.
6. Tunggu proses deployment di tab Actions. Buka alamat yang ditampilkan oleh GitHub Pages.

Tidak ada langkah build. File `.nojekyll` sudah disertakan. Semua navigasi menuju file HTML nyata; folder repository di URL tidak merusak path aset.

Panduan resmi, diperiksa 7 Oktober 2026:
https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Isi proyek

- `index.html`: landing page / learner home setelah login.
- `login.html`, `register.html`, `choose-mode.html`: autentikasi demo dan onboarding.
- `explore.html`: pencarian, kategori, filter gabungan, sorting.
- `class-detail.html?id=figma`: detail berdasarkan ID kelas.
- `instructor-profile.html?id=figma`: profil pengajar dan tab About/Classes/Reviews.
- `checkout.html`, `payment-success.html`: transaksi simulasi dan struk.
- `my-learning.html`, `review.html`: sesi demo, progress, history, review.
- `profile.html`, `notifications.html`, `how-it-works.html`.
- `instructor/dashboard.html`: statistik terhitung dari data akun.
- `instructor/create-class.html`: wizard 7 langkah, thumbnail, draft, edit, preview, publish.
- `instructor/my-classes.html`, `class-management.html`, `students.html`, `earnings.html`.
- `about.html`, `help.html`, `terms.html`, `privacy.html`: halaman footer nyata.
- `css/style.css`: token warna, layout desktop, breakpoint tablet/mobile, reduced motion.
- `js/app.js`: penyimpanan, seed kelas, helper, header/footer, komponen kartu.
- `js/auth.js`: akun lokal, login demo, seed data Athira.
- `js/learner.js`: alur learner.
- `js/instructor.js`: alur instructor.
- `assets/images/`: ilustrasi SVG lokal orisinal untuk hero dan 8 kategori.
- `assets/icons/`: favicon/logo.

## Fitur yang dapat diuji

### Learner

1. Login / register → choose mode → Start Learning.
2. Cari `Figma`, `Design`, atau `Sarah`.
3. Gabungkan kategori, harga, rating, level, online/offline, jadwal, dan lokasi. Lokasi hanya muncul jika Offline.
4. Reset filter, ubah sort, coba pencarian tanpa hasil.
5. View Class → profil pengajar → kembali ke detail → Join Class.
6. Pilih metode pembayaran. Coba promo `LEARN10` (diskon 10% harga kelas).
7. Aktifkan **Simulate payment failure** untuk menguji error; matikan untuk transaksi berhasil.
8. View My Learning → Join Demo Session → Complete Demo Session → Leave Review.
9. Cek Payment History, Saved Classes, dan Notifications.

### Instructor

1. Switch to Teach Mode → Create New Class.
2. Isi 7 langkah. Coba lanjut tanpa harga untuk melihat validasi.
3. Preview → Publish → kelas muncul di My Classes dan Explore.
4. Edit kelas, save draft, lihat daftar peserta dan profil peserta.
5. Coba Cancel Class: enrollment dibatalkan dan transaksi simulasi diberi status Refunded.
6. Coba Mark Class Completed: semua peserta aktif dapat memberi review.
7. Earnings menampilkan transaksi, saldo pending, net earnings, dan chart enam bulan.

Akun demo berisi 8 peserta contoh, 2 kelas milik Athira (1 aktif, 1 draft), 1 kelas belajar selesai, dan transaksi contoh. Akun baru mulai kosong. Total dashboard dihitung dari data; bukan angka hardcoded yang tidak sesuai tabel.

## Aturan simulasi

- Tidak ada transfer uang, email, pesan, meeting, atau kelas nyata.
- Contact menampilkan alamat peserta; tidak mengirim pesan.
- Biaya checkout learner Rp5.000. Komisi instructor 10% dari harga kelas. Diskon promo diasumsikan ditanggung platform.
- Pembayaran sukses menyimpan enrollment dan payment. Enrollment duplikat, kelas penuh, kelas nonaktif, dan pembelian kelas sendiri dicegah.
- Kelas contoh memiliki tanggal relatif saat browser pertama kali membuat seed data.
- Review hanya tersedia untuk enrollment berstatus Completed.
- Data per akun dipisahkan menggunakan userId / ownerId. Ini logika prototype, bukan security boundary production.
- Remember me memperpanjang sesi dari 8 jam menjadi 30 hari.
- Tombol Forgot Password membuka petunjuk lokal; tidak ada layanan reset melalui email.
- Upload thumbnail mendukung PNG/JPG/WebP hingga 2 MB. Kuota localStorage terbatas; terlalu banyak gambar bisa memenuhi penyimpanan dan memunculkan error.

## localStorage

Key utama: `user`, `currentMode`, `classes`, `createdClasses`, `enrollments`, `payments`, `reviews`, `bookmarks`, `notifications`.

Key pendukung: `accounts`, `rememberMe`, `sessionExpires`.

Data hanya tersimpan di browser dan origin yang sama; tidak sinkron antarperangkat. Menghapus site data akan menghapus semua data prototype. Tidak ada backend atau database terpusat.

## Mengedit

Ubah warna di `:root` pada `css/style.css`. Ubah struktur konten di masing-masing HTML. Halaman yang menampilkan data menggunakan renderer di file JS terkait. Ubah seed marketplace di `js/app.js` dan seed demo Athira di `js/auth.js`; hapus data situs di browser untuk memuat ulang seed baru.

Font Google bersifat opsional; jika internet tidak tersedia, website memakai Arial/sans-serif. Semua ilustrasi sudah lokal.

## Pembaruan desain Studio

Versi ini memakai hero navy/cobalt, aksen mint/amber/lavender, serta sembilan foto ilustratif yang dibuat dengan AI. Gambar tersimpan lokal. Default gambar lama dipetakan ke foto baru saat render; data akun dan thumbnail unggahan pengguna tetap dipertahankan. Prompt desain profesional tersedia di `PROMPT-DESIGN.md`.

## Status QA

Lihat `QA.md`. Pengujian DOM/logika dan link sudah selesai. Pengujian visual browser penuh belum dilakukan karena runtime browser pengujian tidak tersedia dan unduhannya gagal di lingkungan pembuatan.

## Versi ekspor terbaru — 7 Oktober 2026

Sama dengan SkillSwap versi 3 yang diterbitkan. Delapan kategori kelas memakai foto berbeda; Programming tidak lagi memakai foto UI/UX. Usulan fitur tambahan belum diterapkan.
