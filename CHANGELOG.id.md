# Changelog

[English](./CHANGELOG.md) | **Bahasa Indonesia**

## 1.0.3 — 2026-10-20

### Diperbaiki

- **Kamera virtual di Windows 10.** Di 1.0.2 kamera virtual hanya berfungsi di
  Windows 11; di Windows 10 kamera tidak pernah muncul di OBS, Zoom, atau
  aplikasi lain. Kini berfungsi di Windows 10 dan Windows 11, di aplikasi
  64-bit maupun 32-bit.
- **Urutan membuka kamera virtual.** Membuka OBS atau Zoom sebelum Goggles3 USB
  Live (atau sebelum kamera virtual diaktifkan) tidak lagi membuat source
  kosong sampai Anda memilihnya ulang. Kamera menampilkan abu-abu gelap selama
  belum ada video, lalu otomatis berganti ke gambar live.
- **Ikon aplikasi di Windows.** Ikon sebelumnya kosong di File Explorer, Start
  menu, shortcut desktop, dan Settings › Apps. Kini tampil di semua tempat.

### Diubah

- **Kamera virtual kini bernama "Orbit-Virtual Camera"** (sebelumnya
  "goggles3"). Di OBS, buka source *Video Capture Device* yang sudah ada sekali
  saja dan pilih **Orbit-Virtual Camera** di daftar Device.
- Kamera virtual mengeluarkan 1920×1080 pada 30 fps, dengan bar hitam di
  sekitar gambar goggles. Kamera tersedia selama Goggles3 USB Live terbuka
  dengan **Settings › Output › Virtual camera** aktif; tanpa video kamera
  menampilkan abu-abu gelap, dan saat aplikasi berhenti mengirim kamera
  menampilkan gambar terakhir yang digelapkan.
- Kamera virtual berfungsi di Zoom, Teams, OBS, Discord, browser, dan aplikasi
  lain yang memakai webcam, tetapi tidak di aplikasi Camera bawaan Windows.
- Update dari 1.0.2 di Windows 11 otomatis menghapus kamera lama "goggles3".

## 1.0.2 — 2026-10-20

### Sorotan

- **Semua fitur kini bisa dipakai gratis.** Koreksi lensa, dewarp, LUT,
  streaming, perekaman, dan kamera virtual berfungsi tanpa lisensi, dan batas
  trial 10 menit sudah dihapus. Tanpa lisensi, watermark **UNLICENSED** tampil
  di preview dan tertanam di stream, rekaman, dan kamera virtual, serta output
  tersebut dibatasi 720p30. Dengan lisensi, watermark hilang dan kualitas asli
  tetap terjaga.
- **Live streaming.**
  - *Local streaming*: kirim video asli (tanpa re-encode) ke OBS atau VLC di
    komputer ini atau di jaringan Anda, dengan alamat yang bisa disalin.
  - *Social media streaming*: YouTube, Facebook, Twitch, TikTok, atau server
    RTMP/RTMPS kustom. Stream key disembunyikan secara default; kualitas
    Low/Medium/High.
- **Perekaman.** Simpan tayangan live sebagai MP4, MKV, atau H.264 mentah ke
  folder Movies, dengan tombol **Show** untuk membuka file terakhir. Rekaman
  MP4 ditulis sedemikian rupa sehingga jika aplikasi crash, paling banyak
  hanya detik terakhir yang hilang.
- **Tampilan baru.** Tema gelap yang lebih nyaman dengan teks lebih besar,
  kontrol membulat, dan tombol toggle. Pengaturan terbuka sebagai jendela di
  tengah layar dengan halaman Info & License, Picture, Streaming, Recording,
  Output, System, dan Log.

### Ditambahkan

- **Dewarp (gaya DJI Fly):** preset satu klik untuk mengoreksi distorsi lensa
  agar mendekati tampilan aplikasi DJI Fly. Sesuaikan dengan slider Strength.
- **Stabilisasi software (eksperimental):** mengurangi guncangan kecil pada
  tampilan live, dengan slider Strength. Gambar sedikit di-zoom, dan fitur ini
  bukan pengganti RockSteady/EIS di air unit.
- Slider **Brightness** (−1 sampai +1 EV) dengan tombol reset.
- **Opasitas LUT:** campurkan tampilan LUT dengan gambar asli.
- **Use GPU render** (halaman System, aktif secara default): decode video di
  GPU agar pemakaian CPU lebih rendah, dan otomatis kembali ke decode software
  jika decoder GPU gagal.
- **Kamera virtual "goggles3" di Windows 11:** gunakan tayangan goggles
  sebagai kamera di Zoom, Teams, OBS, dan aplikasi lain. Nonaktif secara
  default; aktifkan di Settings › Output.
- **Tombol bantuan dan tutorial 5 langkah bergambar** tentang kabel USB,
  LiveView sharing, Camera View Recording, dan OTG Wired Connection.
- **Informasi sistem** di pengaturan: ID komputer (bisa disalin), sistem
  operasi, GPU, dan CPU. Berguna saat melaporkan masalah.
- **Update wajib:** jika versi lama sudah tidak didukung, aplikasi meminta
  Anda memperbarui sebelum bisa terhubung.
- Ikon aplikasi baru.

### Diubah

- **Aktivasi lisensi** kini memakai **alamat email dan license key** sesuai
  lisensi yang diterbitkan.
- **Lisensi berlaku per komputer, bukan per goggles.** Satu lisensi bisa
  dipakai dengan goggles apa pun di sejumlah komputer terbatas.
- **Pindah lisensi ke komputer lain kini otomatis.** Tombol **Deactivate this
  computer** dihapus. Komputer tetap terikat selama 7 hari setelah aktivasi;
  setelah itu, mengaktifkan lisensi di komputer lain akan melepaskannya.
- **Sesi lisensi:** lisensi dicek secara online saat aplikasi dibuka. Sesi
  berlisensi berlaku 4 jam sejak aplikasi dijalankan; halaman License
  menampilkan sisa waktunya, dan tombol **Start new session** memperbaruinya.
  Stream atau rekaman yang sedang berjalan tetap berlanjut dan berganti ke
  watermark yang sesuai saat status lisensi berubah.
- Status kini menampilkan **Waiting for camera**, bukan "Waiting feed".

### Diperbaiki

- **macOS 11 ke atas:** decoder video di 1.0.1 bisa gagal berjalan di versi
  macOS yang lebih lama dari versi terbaru.
- **Video lebih mulus dan bersih:** aplikasi kini membaca semua paket jaringan
  dalam setiap transfer USB dan membuang fragmen terlambat dari frame lama,
  sehingga patah-patah dan frame rusak berkurang.
- Mengaktifkan lisensi di tengah sesi trial tidak lagi membuat sesi tetap
  terkena batas waktu trial.

## 1.0.1 — 2026-09-23

- Satu paket macOS universal untuk Mac Apple Silicon dan Intel.
- Installer Windows.
- Live view lewat USB, crop 16:9, koreksi lensa di GPU, dan preset warna LUT.
- Aktivasi lisensi dengan verifikasi offline.
- Pengecekan update otomatis.
