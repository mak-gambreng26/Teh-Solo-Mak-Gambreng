🍵 MAK-GAMBRENG PWA
Spesifikasi Proyek Lengkap
Versi Final --- 22 Mei 2026
Daftar Isi
Visi & Tujuan
Struktur Sistem & Akses
Peran Pengguna
Alur SPG / Gerai
Alur Checker
Monitoring Real-time
Dashboard Owner
Bottom Navigation Owner
Administrasi
Laporan Harian Universal
Entitas Database
Aturan Sistem
Data Awal
Teknologi & Implementasi
Kode Referensi
1. Visi & Tujuan
Visi
MAK-GAMBRENG PWA adalah sistem manajemen usaha minuman teh keliling yang terintegrasi secara digital untuk memantau operasional gerai secara real-time.
Tujuan
Digitalisasi pencatatan penjualan, logistik, dan keuangan.
Transparansi operasional Owner, Checker, dan SPG.
Otomatisasi laporan harian.
Pengendalian stok dengan audit trail lengkap.
2. Struktur Sistem
Role utama:
Role      Akses
Owner     Dashboard utama dan seluruh konfigurasi Checker   Pemeriksaan gerai, tutup gerai, restok SPG       Operasional gerai dan transaksi Publik    Pengiriman es kristal melalui QR
Route:
/
/checker
/[slug-gerai]
/tormonitor
/public/kirim-es/[id]
3. Peran Pengguna
Owner
Hak: - Full akses sistem. - Master data. - Keuangan. - Laporan. - Backup. - Pusat Edit Data.
Kode default:
1234
Kode developer:
reset###3
Checker
Tugas:
Mengecek kondisi fisik gerai.
Validasi uang dan QRIS.
Validasi logistik.
Tutup gerai.
Mengirim restok.
Memberikan alasan jika terjadi selisih.
SPG
Tugas:
Membuka gerai.
Input modal awal.
Melakukan transaksi.
Request restok.
Request es kristal.
Melihat riwayat transaksi.
Aturan:
1 SPG aktif per gerai.
Pendapatan tidak ditampilkan pada halaman SPG.
4. Monitoring
Monitoring adalah pusat pantau real-time.
Karakteristik:
Read only.
Refresh otomatis.
Reset setelah seluruh gerai tutup.
Dark mode.
Komponen:
Omzet real-time.
Jumlah gerai aktif.
Cup terjual.
Ranking menu.
Grafik penjualan.
Aktivitas sistem.
5. Dashboard Owner
11 Kartu Utama
Gerai
SPG Room
Checker Area
Tagihan Es Kristal
Audit Log
History Penjualan
Arsip Transaksi
Arsip Logistik Gerai
Pusat Pesan
Kelola Menu
Daily Kitchen
6. Bottom Navigation Owner
Tab Keuangan
Fungsi:
Working Capital.
Pemasukan.
Pengeluaran.
Profit.
Grafik saldo.
Tab Gudang
Fungsi:
Monitoring stok.
History logistik.
Tambah stok.
Tarik logistik.
Tab Laporan
Fungsi:
Laporan harian.
Export PDF/PNG.
Analisis usaha.
Tab Administrasi
Fungsi:
Setup awal.
Master data.
Backup.
Reset.
Pusat Edit Data.
7. Database Entity
23 entity utama:
Users
Gerai
Menu
LogistikItem
BukaGerai
Transaksi
CheckGerai
TutupGerai
Restok
KitchenDaily
Belanja
Pembayaran
WorkingCapital
DailySummary
LaporanHarian
RankingHarian
StokGerai
Notifikasi
Message
ChatRoom
EsKristal
AuditLog
LogistikHistory
8. Aturan Sistem Utama
Data pending tidak disimpan.
Data valid setelah konfirmasi.
Penjualan langsung masuk Monitoring.
History penjualan hanya menampilkan CUP dan transaksi.
Audit Log bersifat immutable.
Kitchen Daily hanya milik Owner.
Mapping logistik menu wajib tersedia.
QR SPG tidak digunakan.
QR Es Kristal dibuat otomatis.
Reset monitoring dilakukan setelah operasional selesai.
9. Data Awal
Menu
Teh Ekstra Rp10.000
Teh Solo Rp10.000
Teh Jumbo Rp12.000
Teh Susu Rp12.000
Teh Milo Rp12.000
Teh Lemon Rp10.000
Gerai
Sunter
Gampol
Biru
Bengkel
Pasar
18
Walang
Bugis
Alur Laut
SPG
Tika, Salsa, Lilis, Wati, Nurul, Jovita, Jasmin, Titi, Farah
Checker
Rian, Mak-Elang
Logistik
Gula
Air Galon
Gas
Plastik
Seal Cup
Sedotan
Susu
Milo
Cup 22oz Oval
Cup 22oz Datar
Cup 18oz
10. Teknologi
Stack:
Komponen         Teknologi
Frontend         PWA HTML5 CSS3 JavaScript Database Lokal   IndexedDB Backend          Node.js/Firebase/Supabase QR               qrcode.js PDF              jsPDF Grafik           Chart.js Storage          LocalStorage + Cloud
11. Workflow Implementasi
Fase 1
Setup dan master data.
Fase 2
Operasional harian:
Kitchen Daily
↓
SPG buka gerai
↓
Penjualan
↓
Checker cek
↓
Checker tutup
Fase 3
Reset Monitoring
↓
Daily Summary
↓
Laporan
↓
Arsip
12. Kode Referensi
Format ID:
TRX-YYYYMMDD-XXX
BG-YYYYMMDD-XXX
CG-YYYYMMDD-XXX
TG-YYYYMMDD-XXX
RS-YYYYMMDD-XXX
MKGR-YYYYMMDD-XG-YC-ZK
Brand Color
Nama              Hex
Hijau Brand       #008438 Hijau Muda        #F6FFF3 Kuning            #FFD700 Merah Alert       #FF4444 Dark Monitoring   #0A0A0A
MAK-GAMBRENG PWA
Spesifikasi Final --- 22 Mei 2026
