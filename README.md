# Monitoring Serangan MITM ARP Spoofing Terhadap Perangkat IoT
Dibuat untuk UAS Keamanan Jaringan Komputer Kelompok 2

## Deskripsi
Repositori ini berisi penelitian mengenai monitoring dan analisis serangan Man-in-the-Middle (MITM) menggunakan teknik ARP Spoofing pada lingkungan Internet of Things (IoT). Penelitian difokuskan pada perangkat ESP32 dalam jaringan lokal terkontrol untuk menganalisis perbedaan karakteristik lalu lintas jaringan antara kondisi normal dan kondisi saat terjadi serangan.

## Tujuan
- Menganalisis dampak serangan ARP Spoofing terhadap perangkat IoT
- Mengidentifikasi perbedaan pola lalu lintas jaringan pada kondisi normal dan serangan
- Mengevaluasi efektivitas Intrusion Detection System (IDS) Snort
- Menunjukkan pentingnya keamanan berlapis pada jaringan IoT

## Metodologi
Penelitian ini menggunakan pendekatan eksperimental kuantitatif dengan perancangan lingkungan jaringan terkontrol. Pengujian dilakukan pada dua kondisi, yaitu kondisi normal dan kondisi serangan. Parameter jaringan diukur secara objektif untuk dianalisis secara komparatif.

## Arsitektur dan Topologi Sistem
Lingkungan pengujian terdiri dari perangkat IoT ESP32, router Mikrotik, VM Kali Linux sebagai attacker, VM Ubuntu Server sebagai IDS Snort, serta Wireshark untuk perekaman lalu lintas jaringan. Seluruh komponen berada dalam satu jaringan WLAN virtual.

## Skenario Serangan
Serangan yang digunakan adalah ARP Spoofing, di mana attacker memalsukan MAC address untuk menempatkan dirinya sebagai perantara komunikasi antara router dan ESP32. Serangan ini memungkinkan intersepsi data meskipun payload telah dienkripsi.

## Monitoring dan Dataset
Monitoring lalu lintas jaringan dilakukan menggunakan Wireshark. Dataset yang dihasilkan berupa file PCAPNG yang dibagi menjadi dataset lalu lintas normal dan dataset lalu lintas serangan. Parameter yang diamati meliputi jumlah paket, protokol, alamat IP, port, ukuran paket, dan interval waktu.

## Metode Analisis
Analisis dilakukan secara komparatif dengan membandingkan karakteristik lalu lintas jaringan antara kondisi normal dan kondisi serangan. Perubahan signifikan pada pola trafik digunakan sebagai indikator serangan MITM.

## Hasil dan Pembahasan
Hasil pengujian menunjukkan bahwa enkripsi melindungi isi data tetapi tidak metadata jaringan. Attacker masih dapat mengamati pola komunikasi, sementara IDS Snort berhasil mendeteksi serangan MITM dan menghasilkan alert sebagai peringatan dini.

## Kesimpulan
Perangkat IoT seperti ESP32 rentan terhadap serangan MITM ARP Spoofing pada jaringan lokal. Penerapan enkripsi dan IDS secara bersamaan terbukti meningkatkan keamanan jaringan IoT melalui mekanisme deteksi dini dan monitoring lalu lintas.

## Tools dan Teknologi
- ESP32
- Kali Linux
- Ubuntu Server
- Snort IDS
- Mikrotik Router
- Wireshark
- Dataset PCAPNG
