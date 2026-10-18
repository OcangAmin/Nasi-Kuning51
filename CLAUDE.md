# POS Nasi Kuning 51

Aplikasi kasir (POS) untuk usaha Nasi Kuning 51 dengan 4 cabang (Pramuka, Dermaga, Pemuda, Abadi).
Kasir membukanya lewat GitHub Pages: https://ocangamin.github.io/Nasi-Kuning51/

## File
- `index.html` — aplikasi kasir: HTML, CSS, dan JS dalam satu file. Data penjualan disimpan di `localStorage` HP kasir.
- `admin.html` — halaman owner untuk mengubah menu & harga. Menulis `menu.json` ke repo
  `OcangAmin/nasi-kuning51-menu` lewat GitHub API memakai token fine-grained yang hanya berlaku untuk repo itu.
- `logo.png` — logo usaha (dipakai di header; `index.html` beralih ke salinan ImgBB bila file ini tidak ada).

## Aturan kerja
- **Tanyakan dulu sebelum memperbarui desain.** Desain tampilan ada di kanvas Claude Design:
  https://claude.ai/artifact/7YvatrqWfXEvBLzNF4EawJ
  Bila dalam satu sesi ada perubahan besar pada tampilan atau alur di `index.html` atau `admin.html`
  (layar baru, tata letak berubah, alur kasir/owner berubah), tanyakan ke pengguna apakah kanvas perlu
  diperbarui, sebutkan artboard mana yang terdampak. Perbarui kanvas hanya setelah pengguna setuju.
  Perubahan kecil (teks, warna sedikit, perbaikan bug tanpa perubahan tampilan) tidak perlu ditanyakan.
  Logo di kanvas memakai aset `/_blob/e82e3ba0ae9d1aed178ee48f55c8a920`.
- **Jangan ubah format data `localStorage` tanpa migrasi**: `naskun51_cart`, `naskun51_history`, `naskun51_cabang`,
  `naskun51_seq`, `naskun51_habis`, `naskun51_menu`, `naskun51_last_closed`. Data penjualan hanya ada di HP kasir.
- Uji di Chromium dengan ukuran layar HP (390×844) sebelum push. CDN jsPDF dan Google Fonts bisa diblokir
  di lingkungan uji; sediakan salinan jsPDF 2.5.1 dari npm bila perlu.
- Teks yang tampil ke pengguna memakai bahasa Indonesia. Tombol nota di riwayat tetap bernama "WhatsApp".
