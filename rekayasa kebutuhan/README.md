# Sistem Pelacakan Alumni Otomatis

Sistem ini dikembangkan untuk memenuhi tugas Daily Project, fokus pada pelacakan jejak digital alumni menggunakan algoritma penanganan nama umum dan background processing.

## 🚀 Fitur Utama
- **Modul 1:** Penyiapan Profil (Handling Low Context & Nama Umum).
- **Modul 2:** Pelacakan Otomatis (Background Job Queue).
- **Modul 3:** Laporan Jejak Bukti digital.

## 📊 Pengujian Aspek Kualitas (Software Quality Assurance)

Berdasarkan aspek kualitas yang ditentukan pada Daily Project 2:

| No | Aspek Kualitas | Skenario Pengujian | Hasil Yang Diharapkan | Status |
|----|----------------|-------------------|-----------------------|--------|
| 1 | **Functionality** | Klik tombol "Siapkan Profil" pada nama "Muhammad Adrian" | Sistem berhasil membuat alias "M. Adrian" dan flag Nama Umum aktif | ✅ Pass |
| 2 | **Privacy** | Memproses data alumni dengan status `is_opt_out = true` | Sistem menolak memproses sesuai kebijakan privasi | ✅ Pass |
| 3 | **Efficiency** | Menjalankan pelacakan untuk 3 alumni secara bersamaan | Sistem menggunakan Queue agar web tidak freeze/hang | ✅ Pass |
| 4 | **Reliability** | Mematikan worker antrean saat proses berjalan | Antrean tetap tersimpan di database dan lanjut saat worker aktif | ✅ Pass |
| 5 | **Usability** | Navigasi dari Dashboard ke Detail Bukti | User dapat melihat bukti digital dalam maksimal 2 klik | ✅ Pass |

## 🛠️ Cara Menjalankan Secara Lokal
1. Clone repository
2. Jalankan `composer install`
3. Konfigurasi `.env` (Database MySQL)
4. `php artisan migrate:fresh --seed`
5. `php artisan serve`
6. Di terminal terpisah, jalankan `php artisan queue:work`
