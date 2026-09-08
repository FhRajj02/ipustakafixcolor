# iPustaka PUA — struktur proyek

Situs ini sekarang dipisah per halaman (bukan satu file SPA) supaya
gampang dibuka dan diatur di VS Code. Buka folder ini sebagai
workspace, lalu jalankan `menu.html` lewat ekstensi Live Server
(atau buka langsung di browser).

## Peta file → jendela/menu

| File                                                   | Menu / cabang sidebar                          |
|---------------------------------------------------------|-------------------------------------------------|
| `menu.html`                                              | Beranda (tampilan utama)                        |
| `menu-Beranda-Rekomendasi.html`                           | Beranda → Rekomendasi                           |
| `menu-Beranda-rekomendasi-matakuliah_wajib.html`          | Beranda → Rekomendasi → Matakuliah wajib        |
| `menu-Beranda-rekomendasi-Matakuliah_umum.html`           | Beranda → Rekomendasi → Matakuliah umum         |
| `menu-Berita.html`                                        | Berita                                          |
| `menu-rak_pinjam.html`                                    | Rak Pinjam                                      |

## File bersama (satu sumber, dipakai semua halaman)

- `style.css` — semua styling sidebar, kartu, dan halaman. Ubah di sini,
  otomatis berlaku ke semua halaman.
- `nav.js` — logika buka/tutup submenu sidebar (tombol panah ▸).
- `books.js` — fungsi `renderBooks()` untuk kartu sampul buku, dipakai
  oleh halaman Rekomendasi, Matakuliah Wajib, dan Matakuliah Umum.
- `covers/` — taruh file gambar sampul asli di sini kalau kamu punya
  (lihat komentar di awal `books.js` untuk cara penamaan filenya).
  Kalau kosong, kartu otomatis memakai desain sampul buatan
  (judul + nomor panggil).

## Menambah halaman/cabang baru

1. Salin salah satu file `menu-*.html` yang paling mirip sebagai
   titik awal.
2. Ganti `<title>`, isi `<section class="view active">`, dan skrip
   data di bagian bawah `<body>`.
3. Tambahkan tautan `<a>` menu barunya di blok `<nav class="nav">`
   pada **semua** file (termasuk file baru itu sendiri), lalu tandai
   `class="active"` pada file yang sesuai dan `class="nav-group open"` /
   `class="rotated"` pada leluhurnya supaya sidebar terbuka dengan benar
   saat halaman itu yang sedang dibuka.
