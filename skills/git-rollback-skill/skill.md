# Name: Git Version Rollback & History Tracker
# Description: Skill untuk melihat riwayat perubahan kode (commit) lengkap dengan waktu dan tanggal presisi, melihat detail perbedaan kode, serta melakukan pengembalian versi (rollback) secara aman.

## What I do
Saya membantu melacak sejarah perubahan proyek Anda dan mengembalikannya ke versi yang diinginkan. Saya bisa:
- Menampilkan daftar commit lengkap dengan tanggal, waktu, waktu relatif, hash, dan pesan commit menggunakan format yang sangat mudah dibaca.
- Menunjukkan detail perubahan (baris kode mana saja yang berubah) di commit tertentu.
- Melakukan rollback file ke versi lama secara aman (temporer maupun permanen).

## When to use me
- Ketika AI menghasilkan kode yang salah atau merusak fitur yang sebelumnya sudah berjalan dengan baik.
- Ketika Anda ingin melihat kapan saja dan apa saja perubahan yang telah Anda lakukan di proyek.
- Ketika Anda ingin membandingkan kode saat ini dengan versi beberapa hari yang lalu.

## How I do it

### 📈 Tahap 1: Melihat Riwayat Versi (Commit History)
1. Jalankan perintah Git Log kustom berikut untuk menampilkan daftar commit lengkap dengan waktu dan tanggal:
   ```bash
   git log --pretty=format:"[%cd (%cr)] %h - %s" --date=format:"%Y-%m-%d %H:%M:%S" -n 15
   ```
2. Sajikan daftarnya di panel chat secara rapi. Contoh:
   > `[2026-06-03 23:55:34 (2 jam yang lalu)] b69649f - feat: tambah halaman login`
   > `[2026-06-03 21:30:12 (4 jam yang lalu)] a1c2d3f - style: rapikan tombol`

### 🔍 Tahap 2: Melihat Perbedaan Kode (Diff & Show)
- **Melihat isi perubahan versi tertentu:**
  Jalankan `git show [commit-hash]` untuk melihat file dan baris kode mana saja yang diubah pada versi tersebut.
- **Membandingkan kode sekarang dengan versi lama:**
  Jalankan `git diff [commit-hash]` untuk menampilkan perbedaan baris demi baris.

### ↩️ Tahap 3: Mengembalikan Versi (Rollback)
Berikan pilihan metode pengembalian berikut ke pengguna sesuai tingkat kebutuhannya:

#### Opsi A: Intip/Uji Coba Saja (Sangat Aman)
*Gunakan ini jika hanya ingin melihat/menjalankan kode lama secara sementara tanpa menghapus kode Anda saat ini.*
1. Jalankan perintah:
   ```bash
   git checkout [commit-hash]
   ```
2. Jelaskan kepada pengguna: *"Kode Anda saat ini telah disesuaikan sementara dengan versi target. Anda bisa menguji atau menyalin kodenya. Untuk kembali ke versi terbaru saat ini, cukup jalankan perintah `git checkout main`."*

#### Opsi B: Batalkan Efek Versi Tertentu (Aman)
*Gunakan ini jika ingin membuat commit baru yang secara otomatis membatalkan perubahan yang dibuat oleh versi tertentu, tetapi sejarah commit setelahnya tetap dipertahankan.*
1. Jalankan perintah:
   ```bash
   git revert [commit-hash] --no-edit
   ```
2. Laporkan: "✅ Perubahan dari versi [commit-hash] berhasil dibatalkan dan disimpan dalam commit baru."

#### Opsi C: Reset Total ke Versi Lama (🔴 SENSITIF & BERBAHAYA)
*Gunakan ini jika Anda benar-benar ingin membuang semua kode baru yang ditulis setelah versi target dan kembali murni ke versi lama tersebut.*
1. **⚠️ PROTOKOL PERINGATAN:** Anda **wajib** meminta konfirmasi tegas dari pengguna di chat sebelum menjalankan ini:
   > *"Peringatan: Perintah ini akan menghapus permanen semua perubahan kode dan commit yang dibuat setelah versi ini. Apakah Anda yakin ingin melanjutkan? (Ketik YA atau TIDAK)"*
2. Jika pengguna mengetik "YA", jalankan:
   ```bash
   git reset --hard [commit-hash]
   ```
3. Laporkan: "✅ Proyek berhasil di-reset total ke versi [commit-hash]. Semua file telah dikembalikan ke kondisi tanggal tersebut."
