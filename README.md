# Lineup Open Mic

Web sederhana untuk mencatat dan menampilkan lineup komika open mic setiap Jumat.
Statis (HTML saja), di-hosting gratis lewat GitHub Pages. Data disimpan di `data.json`.

## Isi repo
- `index.html` : seluruh aplikasi (tampilan publik + admin)
- `data.json`  : data lineup (diubah otomatis lewat tombol "Simpan ke GitHub")

## Cara deploy
1. Buat repo baru di GitHub (public), misalnya `lineup-open-mic`.
2. Upload `index.html`, `data.json`, dan `README.md` ke branch `main`.
3. Buka **Settings → Pages**. Pada *Build and deployment*, pilih **Deploy from a branch**, branch `main`, folder `/ (root)`, lalu Save.
4. Tunggu 1-2 menit. Situs aktif di `https://USERNAME.github.io/lineup-open-mic/`.

## Cara login admin
1. Buka https://github.com/settings/personal-access-tokens/new
2. Isi nama token, lalu pada **Repository access** pilih **Only select repositories** dan pilih repo ini.
3. Pada **Permissions → Repository permissions**, set **Contents** ke **Read and write**.
4. Generate token, lalu salin (diawali `github_pat_`).
5. Buka situs, klik tulisan kecil **Admin** di bagian bawah (atau tambahkan `#admin` di akhir alamat), tempel token, klik Masuk.

Token hanya tersimpan di browser perangkatmu. **Jangan pernah menaruh token di dalam file repo.**
Pengunjung biasa tidak melihat tombol edit dan tidak bisa mengubah data tanpa token.

## Alur mingguan
1. Masuk admin, isi tanggal, jumlah komika yang naik, dan MC.
2. Tambah/ubah/hapus nama, atur urutan (seret baris atau tombol ↑ ↓).
3. Klik **Simpan ke GitHub**. Tampilan publik langsung ikut berubah.
4. Minggu depan: klik **Mulai pekan berikutnya** (waiting list jadi urutan teratas, tanggal maju 7 hari), lalu simpan.

## Catatan
- Domain sendiri (bukan `github.io`)? Isi `CFG.owner` dan `CFG.repo` di bagian atas script `index.html`.
- Tanpa koneksi GitHub, tombol **Unduh data.json** bisa dipakai lalu commit manual.
- Repo public berarti daftar nama komika juga bisa dibaca publik. Itu sama seperti tampilan webnya.
- Pengunjung membaca data lewat GitHub API (batas 60 permintaan/jam per IP). Jika terlewati, halaman otomatis memakai `data.json` biasa, yang bisa terlambat beberapa menit.
