# Goggles3 USB Livestream

[English](./README.md) | **Bahasa Indonesia**

Tampilkan live view DJI Goggles di komputer melalui kabel USB. Tersedia untuk **Windows** dan **macOS**, dengan preview video, crop 16:9, koreksi lensa, dan preset warna LUT.

Repositori ini menyediakan installer aplikasi. Source code tidak disertakan.

## Download

Versi **1.0.0**:

| Platform | Installer |
| --- | --- |
| Windows | [Download Windows Setup](https://github.com/planktonwhc/Goggles3-USB-Livestream/releases/download/v1.0.0/goggles3-usb-live-1.0.0-Windows-setup.exe) |
| macOS | [Download macOS Package](https://github.com/planktonwhc/Goggles3-USB-Livestream/releases/download/v1.0.0/goggles3-usb-live-1.0.0-MacOS.pkg) |

## Perangkat yang didukung

- **DJI Goggles 3:** sudah diuji.
- **DJI Goggles N3:** belum diuji; kompatibilitas belum dikonfirmasi.
- Kabel USB yang mendukung **transfer data**.
- Aircraft/air unit yang sudah terhubung ke goggles untuk menampilkan gambar kamera.

## Instalasi

### Windows

1. Unduh dan jalankan installer Windows.
2. Ikuti petunjuk instalasi, lalu buka aplikasi.
3. Sambungkan goggles menggunakan kabel USB data.
4. Saat aplikasi meminta izin administrator untuk mengatur adapter jaringan goggles, setujui agar koneksi dapat disiapkan.

Aplikasi menggunakan adapter RNDIS bawaan Windows. Tidak perlu mengganti driver goggles ke WinUSB melalui Zadig. Pertahankan file DLL yang dipasang bersama aplikasi.

### macOS

1. Unduh dan buka installer `.pkg`.
2. Ikuti petunjuk instalasi.
3. Buka aplikasi yang sudah terpasang, lalu sambungkan goggles menggunakan kabel USB data.

#### Izinkan aplikasi dibuka

Jika macOS memblokir installer atau aplikasi karena pengembang tidak dapat diverifikasi:

1. Coba buka installer atau aplikasi satu kali.
2. Buka **System Settings → Privacy & Security** (**Pengaturan Sistem → Privasi & Keamanan**).
3. Gulir ke bagian **Security**, cari installer/aplikasi yang diblokir, lalu klik **Open Anyway / Tetap Buka**.
4. Lakukan autentikasi jika diminta, lalu konfirmasi **Open / Buka**.

Nama opsi tersebut adalah **Open Anyway**, bukan “Trusted Developer.” Lihat [panduan Apple](https://support.apple.com/en-qa/guide/mac-help/mh40616/mac).

Jika aplikasi yang sudah terpasang masih diblokir oleh atribut karantina dan kamu memercayai rilis yang diunduh, buka **Terminal** lalu jalankan:

```sh
sudo xattr -r -d com.apple.quarantine /Applications/Goggles3\ USB\ Live.app
```

Masukkan kata sandi administrator Mac saat diminta (karakter tidak terlihat saat diketik), lalu buka kembali aplikasi. Perintah ini menghapus atribut karantina pada bundle aplikasi tersebut; tidak menandatangani atau menotariskan aplikasi. Perintah mengasumsikan aplikasi terpasang pada lokasi di atas.

## Mulai live view

1. Nyalakan goggles dan aircraft/air unit.
2. Pastikan gambar kamera sudah terlihat di goggles.
3. Aktifkan **LiveView Sharing** melalui shortcut menu goggles: tekan tombol 5D ke bawah/ke arah pengguna, lalu aktifkan berbagi live view. Walaupun keterangannya menyebut Wi-Fi, pengaturan ini juga digunakan untuk jalur berbagi melalui USB.
4. Sambungkan goggles ke komputer.
5. Buka aplikasi dan tekan tombol koneksi.
6. Tunggu hingga video muncul. Gunakan tombol putus koneksi untuk mengakhiri sesi.

### Menguji tanpa aircraft

Pada goggles, aktifkan:

**Settings → Camera → Advanced Camera Settings → Camera View Recording**

Pengaturan ini dapat menampilkan layar tunggu untuk menguji koneksi. Untuk gambar kamera yang lebih bersih dari OSD, nonaktifkan **Camera View Recording**. Jika tidak ada sumber kamera yang terhubung, gambar dapat menjadi kosong.

## Trial dan PRO

| Fitur | Trial | PRO |
| --- | --- | --- |
| Live view melalui USB | Ya | Ya |
| Durasi sesi | 10 menit per sesi | Tanpa batas sesi trial |
| Crop sumber 4:3 ke 16:9 | Ya | Ya |
| Koreksi lensa | — | Ya |
| Preset warna LUT | — | Ya |

Untuk aktivasi PRO, sambungkan goggles, buka pengaturan lisensi di aplikasi, lalu masukkan license key. Aktivasi membutuhkan internet dan terikat pada serial goggles. Setelah aktivasi berhasil, sertifikat lisensi dapat diverifikasi secara offline pada perangkat tersebut.

## Pengaturan gambar

### Crop 16:9

Aktifkan **Fill 16:9 (crop top / bottom)** untuk menampilkan bagian tengah sumber 4:3 dalam rasio 16:9. Bagian atas dan bawah dipotong tanpa meregangkan gambar.

Contoh: sumber 1440×1080 menampilkan area tengah 1440×810. Opsi ini tidak aktif untuk sumber yang sudah 16:9. Crop tidak mendeteksi atau menghapus OSD secara otomatis.

### Lens correction — PRO

Aktifkan **Lens correction**, lalu naikkan **Strength** secara bertahap untuk mengurangi efek cembung. Setiap kali diaktifkan, nilainya kembali ke **0%**, sehingga gambar awal tidak berubah.

Koreksi berjalan di GPU. Sesuaikan kekuatan berdasarkan gambar kamera; fitur ini tidak melakukan kalibrasi lensa otomatis.

### Color grade (LUT) — PRO

Pilih preset LUT melalui pengaturan gambar untuk mengubah tampilan warna. Jika video terasa berat, coba nonaktifkan LUT terlebih dahulu.

## Troubleshooting

| Masalah | Yang perlu diperiksa |
| --- | --- |
| Goggles tidak terdeteksi | Pastikan goggles menyala, gunakan kabel USB data, lalu coba port USB lain. |
| Terhubung tetapi video kosong | Periksa LiveView Sharing dan koneksi aircraft/air unit. Untuk pengujian tanpa aircraft, aktifkan Camera View Recording. |
| Koneksi Windows gagal | Pastikan adapter RNDIS tersedia dan pengaturan adapter yang meminta izin administrator sudah selesai. |
| Gambar tersendat atau pecah | Tutup aplikasi lain yang mengakses goggles, coba sambungan USB langsung, dan uji dengan LUT nonaktif. |
| Crop tidak bisa diaktifkan | Fitur ini hanya berlaku saat dimensi frame sumber mendekati rasio 4:3. |
| Koreksi lensa tidak tersedia | Periksa aktivasi PRO dan pesan kesalahan pada panel pengaturan. |
| Sesi berhenti setelah 10 menit | Batas durasi trial telah tercapai. |
| Aplikasi melaporkan DLL hilang | Instal ulang dari paket installer lengkap. Jangan memindahkan executable sendirian dari folder instalasinya. |

Aplikasi rilis tidak menampilkan log verbose di terminal. Informasi koneksi dan kesalahan aplikasi tersedia pada panel log internal.

VSync dinonaktifkan secara default untuk mengurangi waktu tunggu tampilan. Jika terlihat garis patah saat gambar bergerak (*tearing*), jalankan aplikasi dengan variabel lingkungan **`GOGGLES_VSYNC=1`** untuk mengaktifkannya kembali.

## Melaporkan masalah

Saat melaporkan masalah melalui Issues repositori ini, sertakan versi aplikasi, sistem operasi, model goggles, langkah untuk mengulangi masalah, serta pesan dari panel log. Hindari menyertakan license key atau serial perangkat pada laporan publik.
