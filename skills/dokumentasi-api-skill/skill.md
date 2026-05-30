# Name: Dokumentasi API Otomatis
# Description: Skill kondisional untuk membuat dokumentasi endpoint API lengkap. Hanya digunakan jika proyek memiliki backend/API.

## What I do
Saya membuat file `7_Dokumentasi_API.md` yang berisi dokumentasi lengkap setiap endpoint API di proyek: method, URL, parameter, header, response body, dan error code. Dilengkapi contoh request/response yang siap digunakan.

## When to use me
- Saat `cetak-dokumen-skill` dijalankan **DAN** proyek memiliki backend/API (kondisional).
- Saat menambahkan endpoint API baru.
- Saat onboarding developer frontend/mobile yang butuh referensi API.

## Syarat Aktivasi
> ⚡ **Skill ini KONDISIONAL.** Hanya dicetak jika proyek memiliki backend/API.
> Jika proyek adalah IoT sederhana tanpa API, atau Desktop offline, skill ini DILEWATI.

## How I do it
1. Baca file `1_PRD.md` dan `2_Arsitektur.md` untuk mengidentifikasi fitur yang membutuhkan API.
2. Identifikasi semua endpoint yang dibutuhkan berdasarkan fitur di PRD.
3. Buat file `7_Dokumentasi_API.md` dengan struktur:
   ```
   # Dokumentasi API: [Nama Proyek]

   ## Informasi Umum
   - **Base URL:** `https://api.example.com/v1` (sesuaikan)
   - **Format Response:** JSON
   - **Autentikasi:** [Bearer Token / API Key / Session / None]

   ## Autentikasi
   (Panduan cara mendapatkan dan menggunakan token/key)

   ### Contoh Header Autentikasi
   ```
   Authorization: Bearer <token>
   Content-Type: application/json
   ```

   ## Daftar Endpoint

   ### 📁 [Nama Grup/Modul 1] (misal: Auth)

   #### `POST /auth/login`
   **Deskripsi:** Login pengguna dan mendapatkan token.

   **Request Body:**
   | Field | Tipe | Wajib | Deskripsi |
   |-------|------|-------|-----------|
   | email | string | ✅ | Email pengguna |
   | password | string | ✅ | Password pengguna |

   **Contoh Request:**
   ```json
   {
     "email": "user@example.com",
     "password": "password123"
   }
   ```

   **Response Sukses (200):**
   ```json
   {
     "status": "success",
     "data": {
       "token": "eyJhbGciOiJ...",
       "user": {
         "id": 1,
         "name": "User",
         "email": "user@example.com"
       }
     }
   }
   ```

   **Response Error:**
   | Kode | Deskripsi |
   |------|-----------|
   | 400 | Request body tidak valid |
   | 401 | Email atau password salah |
   | 429 | Terlalu banyak percobaan login |
   | 500 | Internal server error |

   ### 📁 [Nama Grup/Modul 2]
   (format serupa untuk setiap endpoint)

   ## Kode Error Global
   | Kode | Deskripsi | Penanganan |
   |------|-----------|------------|
   | 400 | Bad Request | Periksa format request |
   | 401 | Unauthorized | Refresh token atau login ulang |
   | 403 | Forbidden | Periksa hak akses |
   | 404 | Not Found | Periksa URL endpoint |
   | 422 | Validation Error | Periksa field yang dikirim |
   | 429 | Rate Limited | Tunggu sebelum retry |
   | 500 | Server Error | Hubungi backend developer |

   ## Rate Limiting
   (informasi batasan request per menit/jam)

   ## Changelog API
   | Versi | Tanggal | Perubahan |
   |-------|---------|-----------|
   | v1.0 | (tanggal) | Rilis awal |
   ```
4. Sesuaikan endpoint berdasarkan fitur di PRD.
5. Laporkan: "📡 Dokumentasi API berhasil dicetak! [jumlah] endpoint terdokumentasi."
