# Name: Auto-Generate Workflow Files (Ultimate Edition)
# Description: Skill untuk membuat folder proyek, dokumen fisik, boilerplate code, daftar belanja, dan skill dasar otomatis.

## What I do
[cite_start]Saya mengambil alih terminal/sistem operasi untuk membuat folder proyek, dokumen PRD/Arsitektur, inisialisasi file kode dasar (Boilerplate) [cite: 639][cite_start], serta menyuntikkan skill dasar (`log` & `git`) secara otomatis[cite: 579].

## When to use me
Gunakan saya HANYA SETELAH tahap wawancara spesifik selesai dan kamu sudah merumuskan konsep proyek secara matang.

## How I do it
1. Minta izin pengguna dan tentukan nama folder proyek (gunakan huruf kecil dan tanda hubung, misal: `proyek-smart-home`).
2. Jalankan perintah pembuatan folder baru dengan nama tersebut.
3. Masuk ke dalam direktori folder yang baru dibuat.
4. Buat file `1_PRD.md` dan isi dengan rancangan PRD.
5. Buat file `2_Arsitektur.md` (Pastikan mengisi bab "Potensi Masalah/Mitigasi Risiko").
6. [cite_start]Buat file `3_Daftar_Belanja.md` [cite: 636] (Hanya jika ada komponen/layanan yang belum dimiliki pengguna).
7. Buat file `4_Troubleshooting.md` dan isi dengan 3 prediksi error umum beserta solusinya.
8. Salin file `i:\Workflow-Factory\agents-template.md` menjadi `agents.md` di root proyek, lalu sesuaikan aturan AI agar spesifik untuk proyek/platform tersebut.
9. [cite_start]Buat file `status.md` dan isi dengan format Sprint Timeline target harian[cite: 647].
10. **(Boilerplate Generator):**
    - Jika platform proyek adalah ESP/IoT, buat folder `src/` berisi file `main.cpp` kosong dan buat file `platformio.ini` kosong.
    - Jika platform Web, buat file `index.html` dan `style.css` kosong.
    - Jika platform Android, buat struktur boilerplate Kotlin: `app/src/main/java/com/example/myapp/MainActivity.kt` (class MainActivity dasar), `app/src/main/res/layout/activity_main.xml` (tampilan Hello World dasar), `app/src/main/AndroidManifest.xml` (file manifest Android), dan `build.gradle` (file gradle build).
11. Buat direktori `skills/log-skill` dan salin isi file dari `i:\Workflow-Factory\skills\log-skill\skill.md`. Buat direktori `skills/git-skill` dan salin isi file dari `i:\Workflow-Factory\skills\git-skill\skill.md`.

### Cetak Skill Tambahan (Universal & Kondisional)

> **PENTING:** Untuk setiap skill di bawah ini, **salin persis** konten file `skill.md` dari path sumber di Workflow-Factory. JANGAN menulis ulang atau memodifikasi kontennya agar konsistensi terjaga antar proyek.
> **Path sumber:** `i:\Workflow-Factory\skills\[nama-skill]\skill.md`

12. **(Universal)** Buat direktori `skills/review-kode-skill/` dan salin isi file dari `i:\Workflow-Factory\skills\review-kode-skill\skill.md`.
13. **(Universal)** Buat direktori `skills/deployment-skill/` dan salin isi file dari `i:\Workflow-Factory\skills\deployment-skill\skill.md`.
14. **(Universal)** Buat direktori `skills/testing-skill/` dan salin isi file dari `i:\Workflow-Factory\skills\testing-skill\skill.md`.
15. **(Universal)** Buat direktori `skills/git-workflow-skill/` dan salin isi file dari `i:\Workflow-Factory\skills\git-workflow-skill\skill.md`.
16. **(Universal)** Buat direktori `skills/security-audit-skill/` dan salin isi file dari `i:\Workflow-Factory\skills\security-audit-skill\skill.md`.
17. **(Universal)** Buat direktori `skills/sprint-update-skill/` dan salin isi file dari `i:\Workflow-Factory\skills\sprint-update-skill\skill.md`.
18. **(Universal)** Buat direktori `skills/backup-skill/` dan salin isi file dari `i:\Workflow-Factory\skills\backup-skill\skill.md`.
19. **(Universal)** Buat direktori `skills/env-setup-skill/` dan salin isi file dari `i:\Workflow-Factory\skills\env-setup-skill\skill.md`.
20. **(Universal)** Buat direktori `skills/readme-generator-skill/` dan salin isi file dari `i:\Workflow-Factory\skills\readme-generator-skill\skill.md`.
21. **(Universal)** Buat direktori `skills/error-solver-skill/` dan salin isi file dari `i:\Workflow-Factory\skills\error-solver-skill\skill.md`.
22. **(Universal)** Buat direktori `skills/prompt-helper-skill/` dan salin isi file dari `i:\Workflow-Factory\skills\prompt-helper-skill\skill.md`.
23. **(Universal)** Buat direktori `skills/google-drive-skill/` dan salin isi file dari `i:\Workflow-Factory\skills\google-drive-skill\skill.md`.
24. **(Kondisional)** **Jika proyek memiliki backend/API**, buat direktori `skills/dokumentasi-api-skill/` dan salin isi file dari `i:\Workflow-Factory\skills\dokumentasi-api-skill\skill.md`. **Jika tidak, lewati langkah ini.**
25. **(Kondisional)** **Jika proyek membutuhkan database**, buat direktori `skills/database-schema-skill/` dan salin isi file dari `i:\Workflow-Factory\skills\database-schema-skill\skill.md`. **Jika tidak, lewati langkah ini.**

### Cetak Dokumen & File Tambahan

26. **(Universal)** Buat file `README.md` utama di root proyek berdasarkan input PRD (gunakan `readme-generator-skill` sebagai referensi).
27. **(Universal)** Buat file `5_Panduan_Deployment.md` dan isi dengan panduan deployment step-by-step sesuai platform proyek.
28. **(Universal)** Buat file `6_Skenario_Testing.md` dan isi dengan daftar test case berdasarkan fitur di PRD.
29. **(Kondisional)** **Jika proyek memiliki backend/API**, buat file `7_Dokumentasi_API.md` dan isi dengan dokumentasi endpoint API. **Jika tidak, lewati.**
30. **(Kondisional)** **Jika proyek membutuhkan database**, buat file `8_Database_Schema.md` dan isi dengan rancangan skema database. **Jika tidak, lewati.**
31. **(Universal)** Buat file `9_Git_Workflow.md` dan isi dengan panduan branching, konvensi commit, dan alur PR.
32. **(Universal)** Buat file `10_Security_Checklist.md` dan isi dengan checklist keamanan sesuai platform.
33. **(Universal)** Buat file `11_Panduan_Setup.md` dan isi dengan panduan instalasi tools lokal proyek.
34. **(Universal)** Buat file `.gitignore` sesuai platform proyek.
35. **(Universal)** Buat file `.cursorignore` dan `.windsurfignore` di root proyek untuk mengoptimalkan kuota token. Tuliskan isi ignore berikut secara persis ke kedua file tersebut:
    ```ini
    # Abaikan folder skill agar AI tidak memakan token membaca panduan statis secara konstan
    # AI hanya akan membaca skill jika Anda memanggilnya secara eksplisit (misal pakai @ di Cursor)
    /skills/
    README.md
    TUTORIAL.md
    status.md
    agents-template.md

    # Abaikan file grafis & aset besar (Penyebab utama kuota cepat habis)
    *.png
    *.jpg
    *.jpeg
    *.gif
    *.svg
    *.pdf
    *.zip
    *.cdr
    *.psd

    # Abaikan file temporary dan auto-backup
    *.BAK
    *.tmp
    *.log

    # Abaikan file konfigurasi lokal editor yang sering berubah otomatis
    /.vscode/
    /.idea/

    # Abaikan folder hasil build/kompilasi & pihak ketiga
    /node_modules/
    /build/
    /.pio/
    /dist/
    ```

### Laporan Akhir

36. Setelah semua eksekusi berhasil, laporkan di panel chat:
    ```
    🎉 Pabrik Ultimate sukses mencetak seluruh ekosistem proyek!

    📄 Dokumen: README.md, PRD, Arsitektur, Troubleshooting, Deployment, Testing, Git Workflow, Security Checklist, Panduan Setup, Ignore (.cursorignore, .windsurfignore)
    📄 Dokumen Kondisional: [Dokumentasi API ✅/⏭️] [Database Schema ✅/⏭️] [Daftar Belanja ✅/⏭️]
    🧰 Skills: log, git, review-kode, deployment, testing, git-workflow, security-audit, sprint-update, backup, env-setup, readme-generator, error-solver, prompt-helper, google-drive [+dokumentasi-api] [+database-schema]
    📦 Boilerplate: [sesuai platform]

    Proyek 100% siap dikerjakan!
    ```