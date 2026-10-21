# POS Nasi Kuning 51

Aplikasi kasir (POS) untuk usaha Nasi Kuning 51 dengan 4 cabang (Pramuka, Dermaga, Pemuda, Abadi).
Kasir membukanya lewat GitHub Pages: https://ocangamin.github.io/Nasi-Kuning51/

## File
- `index.html` — aplikasi kasir: HTML, CSS, dan JS dalam satu file. Data penjualan disimpan di `localStorage` HP kasir.
- `admin.html` — halaman owner untuk mengubah menu & harga. Menulis `menu.json` ke repo
  `OcangAmin/nasi-kuning51-menu` lewat GitHub API memakai token fine-grained yang hanya berlaku untuk repo itu.
- `logo.png` — logo usaha (dipakai di header; `index.html` beralih ke salinan ImgBB bila file ini tidak ada).

## Aturan kerja
- **Preview di kanvas dulu, baru kode.** Desain tampilan ada di kanvas Claude Design:
  https://claude.ai/artifact/7YvatrqWfXEvBLzNF4EawJ
  Untuk perubahan besar pada tampilan atau alur di `index.html` atau `admin.html`
  (layar baru, tata letak berubah, alur kasir/owner berubah), ikuti urutan ini:
  1. Buat atau ubah artboard terkait di kanvas sebagai preview, lalu kirim link-nya dan sebutkan artboard
     mana yang berubah. Jangan ubah kode dulu.
  2. Tunggu pengguna menyetujui preview atau meminta revisi; revisi di kanvas sampai disetujui.
  3. Setelah disetujui, kerjakan di kode, uji, lalu push.
  4. Tanyakan apakah pengguna mau dibuatkan Pull Request.
  Perubahan kecil (teks, warna sedikit, perbaikan bug tanpa perubahan tampilan) langsung dikerjakan di kode
  tanpa preview. Ingatkan bahwa preview hanya menunjukkan tampilan dan alur; fitur yang bergantung pada HP
  (printer Bluetooth, menu Bagikan, data asli) baru bisa dicoba setelah kode jadi.
  Logo di kanvas memakai aset `/_blob/e82e3ba0ae9d1aed178ee48f55c8a920`.
- **Jangan ubah format data `localStorage` tanpa migrasi**: `naskun51_cart`, `naskun51_history`, `naskun51_cabang`,
  `naskun51_seq`, `naskun51_habis`, `naskun51_menu`, `naskun51_last_closed`, `naskun51_sesi` (sesi jualan: tanggal,
  cabang, kasir), `naskun51_kasir` (daftar nama kasir di HP itu). Data penjualan hanya ada di HP kasir.
  Transaksi di `naskun51_history` boleh punya field opsional `wa` (nomor WA pelanggan, angka saja, format `62…`);
  nomor ini ikut di rekap tutup kasir sebagai data pelanggan.
- Uji di Chromium dengan ukuran layar HP (390×844) sebelum push. CDN jsPDF dan Google Fonts bisa diblokir
  di lingkungan uji; sediakan salinan jsPDF 2.5.1 dari npm bila perlu.
- Teks yang tampil ke pengguna memakai bahasa Indonesia. Tombol nota di riwayat tetap bernama "WhatsApp".
