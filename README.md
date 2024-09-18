# Jarkom-Modul-1-IT42-2024

## Anggota

| Nama                      | NRP        |
| ------------------------- | ---------- |
| Muhammad Ida Bagus Rafi H      | 5027221059 |
| Naufal Syafi` Hakim      | 5027231022 |


### Laporan Challange FTP Login dan Surprise (Dibuat oleh : Muhammad Ida Bagus Rafi Habibie)

#### Ringkasan
File ini berisi data dari paket-paket jaringan yang terekam dalam format teks. Paket-paket ini meliputi berbagai jenis protokol seperti MDNS, SSDP, UDP, dan FTP. Analisis ini akan mengidentifikasi pola-pola komunikasi, peristiwa yang mencurigakan, serta tindakan yang diambil selama sesi jaringan yang terekam.

#### 1. Protokol dan Aktivitas Utama

**MDNS (Multicast DNS)**
- **Paket 1, 2, 33, 34, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67**
  - **Deskripsi**: MDNS digunakan untuk melakukan pencarian nama host dalam jaringan lokal. Paket-paket ini menunjukkan permintaan dan tanggapan untuk nama layanan lokal seperti `_spotify-connect._tcp.local` dan `_microsoft_mcc._tcp.local`.
  - **Frekuensi**: Terjadi secara berkala dalam interval waktu tertentu, menunjukkan bahwa perangkat dalam jaringan sering melakukan pencarian layanan lokal.
  
**SSDP (Simple Service Discovery Protocol)**
- **Paket 3, 5, 6, 7, 8, 45, 46, 48, 49, 50, 82, 83, 90, 91, 92, 93, 94, 95**
  - **Deskripsi**: SSDP digunakan untuk menemukan perangkat dan layanan dalam jaringan. Banyak paket SSDP yang terdeteksi, menunjukkan aktivitas tinggi dalam pencarian perangkat di jaringan.
  - **Frekuensi**: Paket-paket SSDP terlihat sering dipancarkan dalam waktu singkat, menunjukkan pemindaian aktif untuk perangkat.

**UDP (User Datagram Protocol)**
- **Paket 4, 24, 47, 50, 85, 86, 87, 90, 91**
  - **Deskripsi**: Paket UDP dengan port 57621 menunjukkan komunikasi antara dua perangkat, mungkin untuk transfer data atau layanan yang menggunakan UDP.
  - **Frekuensi**: Terdapat pola berulang dalam pengiriman data UDP, dengan interval waktu yang teratur.

**FTP (File Transfer Protocol)**
- **Paket 9-12, 13-17, 20-24, 25-31, 32-38, 40-43, 45-50, 51-57, 58-60, 61-63, 67-78, 80-84, 86-90, 91-96, 97-105, 106-117, 118-120**
  - **Deskripsi**: Aktivitas FTP menunjukkan proses otentikasi dan upaya login. Ada beberapa upaya login yang berhasil dan gagal dengan beberapa username dan password yang berbeda.
  - **Frekuensi**: Ada banyak percakapan FTP dengan beberapa upaya login yang gagal. Beberapa username seperti `letmein`, `abc123`, `mustang`, dan `hunter` digunakan dalam upaya otentikasi.

#### 2. Analisis Keamanan

**Upaya Login FTP yang Gagal**
- Banyak upaya login gagal pada server FTP dengan pesan "530 Login incorrect". Ini menunjukkan adanya percobaan brute-force atau penyerang yang mencoba berbagai kombinasi username dan password.
- Contoh username yang digunakan dalam upaya login termasuk `letmein`, `abc123`, `mustang`, `shadow`, `michael`, `ranger`, dan `hunter`.

**Aktivitas Pencarian Jaringan**
- Frekuensi tinggi permintaan MDNS dan SSDP menunjukkan adanya pemindaian layanan atau pencarian perangkat di jaringan yang bisa menunjukkan aktivitas pemetaan jaringan atau pemantauan.

#### 3. Kesimpulan

- **Komunikasi Jaringan**: Data menunjukkan komunikasi aktif di jaringan dengan frekuensi tinggi pada beberapa protokol. 
- **Keamanan**: Terdapat upaya login yang gagal yang menunjukkan adanya potensi percobaan akses tidak sah ke server FTP. Aktivitas pencarian layanan yang tinggi bisa menunjukkan pemetaan jaringan yang potensial.

