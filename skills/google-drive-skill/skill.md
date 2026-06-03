# Name: Google Drive Sync Helper (Tanpa Zip)
# Description: Skill untuk menyinkronkan (backup) folder proyek secara langsung (unzipped) ke folder Google Drive Lokal menggunakan Robocopy, atau memandu upload manual via web.

## What I do
Saya membantu mencadangkan (backup) proyek Anda secara langsung tanpa kompresi (tanpa zip) ke Google Drive. Saya bisa:
- Mendeteksi letak folder virtual Google Drive untuk Desktop di komputer Anda.
- Menjalankan perintah sinkronisasi cepat (`Robocopy` di PowerShell) untuk menyalin file-file proyek Anda.
- Mengabaikan folder sampah/besar (seperti `.git`, `node_modules`, `.pio`, `build`) secara otomatis agar proses sinkronisasi cepat dan hemat kuota penyimpanan cloud.
- Memberikan panduan manual jika Anda menggunakan Google Drive versi web.

## When to use me
- Di akhir sesi pengerjaan proyek untuk mengamankan salinan terbaru.
- Sebelum Anda mencoba menjalankan program di komputer lain.
- Kapan saja Anda ingin memperbarui file cadangan di cloud tanpa repot men-zip.

## How I do it

### Metode A: Google Drive untuk Desktop (Otomatis & Cepat)
1. Cari keberadaan folder Google Drive virtual di komputer Anda. Saya akan memeriksa drive populer:
   - `G:\My Drive`
   - `H:\My Drive`
   - `D:\Google Drive`
   - `C:\Users\[Username]\Google Drive`
2. Jika tidak ditemukan secara otomatis, tanyakan kepada pengguna: *"Di mana letak folder Google Drive untuk Desktop Anda?"*
3. Tentukan target folder cadangan di Google Drive (misalnya: `G:\My Drive\Backups\[Nama Proyek]`).
4. Jalankan perintah sinkronisasi menggunakan PowerShell **Robocopy** (MIR = Mirroring, XD = Exclude Directories):
   ```powershell
   robocopy "[PATH_PROYEK_LOKAL]" "[PATH_GOOGLE_DRIVE]" /MIR /XD .git node_modules .pio build bin obj .vscode .idea /FFT /R:3 /W:5
   ```
   *Catatan parameter:*
   - `/MIR` : Mirroring (menyamakan persis file lokal dan cloud, file yang dihapus di lokal juga akan dihapus di cloud).
   - `/XD` : Mengabaikan direktori sampah seperti `.git`, `node_modules`, dll.
   - `/FFT` : Toleransi perbedaan waktu file FAT (menghindari copy ulang file yang sama).
   - `/R:3 /W:5` : Mengulang copy maksimal 3 kali jika gagal, dengan jeda 5 detik.
5. Laporkan hasil sinkronisasi:
   ```
   🚀 Proyek berhasil disinkronkan ke Google Drive (Tanpa Zip)!
   📂 Lokasi Cloud: [PATH_GOOGLE_DRIVE]
   Excluding: .git, node_modules, .pio, build, .vscode
   ```

### Metode B: Google Drive Web (Manual)
Jika aplikasi Google Drive untuk Desktop tidak terpasang di komputer Anda:
1. Berikan instruksi langkah demi langkah berikut di panel chat:
   - "Buka browser Anda dan masuk ke [Google Drive](https://drive.google.com)."
   - "Klik tombol **Baru (New)** di pojok kiri atas, lalu pilih **Upload Folder**."
   - "Pilih folder proyek Anda: `[PATH_PROYEK_LOKAL]`."
   - "Konfirmasikan unggahan. Browser Anda akan mengunggah seluruh struktur folder secara langsung tanpa di-zip."
2. Peringatan: Ingatkan pengguna bahwa metode web ini akan mencoba mengunggah folder seperti `node_modules` atau `.git` jika ada, yang bisa memperlambat proses upload. Sarankan untuk menghapus folder build/temporary terlebih dahulu jika ingin menggunakan metode web.
