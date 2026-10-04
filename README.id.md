# Goggles3 USB Livestream

[English](./README.md) | **Bahasa Indonesia**

Tampilkan live view DJI Goggles di komputer melalui kabel USB. Tersedia untuk **Windows** dan **macOS**, dengan preview video, crop 16:9, koreksi lensa, dan preset warna LUT.

Repositori ini menyediakan installer aplikasi. Source code tidak disertakan.

## Download

Versi **1.0.1**:

| Platform | Installer |
| --- | --- |
| Windows (64-bit) | [Download Windows Setup](https://github.com/planktonwhc/Goggles3-USB-Livestream/releases/download/v1.0.1/goggles3-usb-live-1.0.1-windows-x86_64-setup.exe) |
| macOS (Apple Silicon dan Intel) | [Download macOS Package](https://github.com/planktonwhc/Goggles3-USB-Livestream/releases/download/v1.0.1/goggles3-usb-live-1.0.1-macos-universal.pkg) |

Satu paket macOS universal sekarang mendukung Apple Silicon (M1 atau lebih baru) maupun Intel -- tidak perlu cek dulu chip Mac kamu sebelum mengunduh.

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

1. Unduh installer `.pkg` (lihat [Download](#download) -- satu paket universal berjalan di Apple Silicon maupun Intel), lalu buka.
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

## Panduan penggunaan

### 1. Hubungkan goggles ke komputer dengan USB-C

Hubungkan port USB-C goggles ke komputer memakai kabel yang mendukung **transfer data** (kabel khusus charging tidak akan berfungsi). Sebaiknya langsung ke komputer, tanpa hub.

### 2. Aktifkan OTG Wired Connection

Di goggles, buka **Settings → About → OTG Wired Connection to Computer** lalu aktifkan. Kalau aplikasi menyatakan goggles tidak terdeteksi, periksa pengaturan ini lebih dulu.

![OTG Wired Connection to Computer](guide/1.%20Enable%20OTG-wired.png)

Bila goggles sudah terhubung, tampil **OTG Wired Connection -- Connected**:

![OTG Wired Connection: Connected](guide/1.%20Done%20OTG.png)

dan notifikasi **OTG Wired Connection** di layar utama:

![Notifikasi OTG Wired Connection](guide/1.%20OTG%20Succes%20Notif.png)

### 3. Aktifkan LiveView sharing dari tombol 5D

Tekan **tombol 5D** ke bawah (ke arah Anda) untuk membuka menu pintas, lalu aktifkan **Share Liveview to Mobile Device via Wi-Fi**. Walaupun keterangannya menyebut Wi-Fi, jalur berbagi yang sama juga dipakai koneksi USB.

![Share Liveview dari menu pintas 5D](guide/2.%205D-enable-live-view.png)

### 4. Menguji tanpa aircraft: aktifkan Camera View Recording

Tanpa aircraft atau air unit yang terhubung, buka **Settings → Camera → Advanced Camera Settings** lalu aktifkan **Camera View Recording**. Goggles akan mengirim tampilan layarnya, sehingga koneksi bisa diuji tanpa terbang.

![Camera View Recording](guide/3.%20enable-camera-view.png)

Untuk tampilan terbang dengan OSD yang lebih sedikit, matikan lagi **Camera View Recording** setelah aircraft terhubung; bila dimatikan dan belum ada kamera yang terhubung, gambar akan kosong.

### Mulai live view

Buka aplikasi lalu tekan **Connect**. Video muncul setelah goggles menerima gambar dari kamera; sebelum itu status menampilkan **Waiting for camera**. Tekan **Disconnect** untuk mengakhiri sesi.

## Trial dan PRO

| Fitur | Trial | PRO |
| --- | --- | --- |
| Live view melalui USB | Ya | Ya |
| Durasi sesi | 10 menit per sesi | Tanpa batas |
| Crop sumber 4:3 ke 16:9 | Ya | Ya |
| Koreksi lensa | — | Ya |
| Preset warna LUT | — | Ya |

Beli lisensi PRO di [fly.gadgetid.cloud](https://fly.gadgetid.cloud/).

### License key PRO gratis

Coba semua fitur PRO secara gratis dengan salah satu license key berikut:

```
FL-L3J4-F8M9-A2G9-HRRP
FL-CZBC-8P9Z-CGNT-ZAXD
```

Untuk aktivasi PRO, sambungkan goggles, buka pengaturan lisensi di aplikasi, lalu masukkan license key — salah satu kode gratis di atas, atau yang sudah dibeli. Aktivasi membutuhkan internet dan terikat pada serial goggles. Setelah aktivasi berhasil, sertifikat lisensi dapat diverifikasi secara offline pada perangkat tersebut.

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
| Goggles tidak terdeteksi | Aktifkan **OTG Wired Connection to Computer** di goggles (langkah 2 panduan), pastikan goggles menyala, gunakan kabel USB data, lalu coba port USB lain. |
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
