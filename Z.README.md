# SphygmoTest — Digital Sphygmomanometer Testing Interface

SphygmoTest adalah proyek pengembangan antarmuka web untuk monitoring tekanan, pengujian kebocoran, pengukuran laju penurunan tekanan, serta pencatatan hasil pengujian tensimeter digital. Sistem dirancang untuk terintegrasi dengan ESP32 dan sensor tekanan MPX5050GP melalui komunikasi WebSocket.

Proyek ini dikembangkan sebagai media pembelajaran dan prototipe dalam bidang Teknik Elektromedik, khususnya instrumentasi tekanan, pengujian kinerja sphygmomanometer, dan pengembangan sistem monitoring berbasis mikrokontroler.

## Fitur Utama

- **Pressure Gauge:** Visualisasi tekanan berbentuk setengah lingkaran dengan jarum indikator dan rentang tampilan 0–500 mmHg.
- **Pressure Monitoring:** Menampilkan nilai tekanan dalam mmHg dan tegangan keluaran sensor dalam volt.
- **Pressure Graph:** Menampilkan grafik perubahan tekanan berdasarkan data yang diterima.
- **Leak Test:** Menghitung penurunan tekanan dan laju kebocoran berdasarkan tekanan awal, tekanan akhir, dan durasi pengujian.
- **Deflation Rate:** Menghitung laju penurunan tekanan dalam mmHg/menit.
- **WebSocket Integration:** Mendukung penerimaan data JSON dari ESP32.
- **Test History:** Menyimpan dan mengelola riwayat pengujian menggunakan penyimpanan lokal browser.
- **CSV Export:** Mengekspor data pengujian agar dapat dibuka menggunakan Microsoft Excel atau aplikasi spreadsheet lainnya.
- **Responsive Interface:** Antarmuka dirancang untuk desktop dan perangkat seluler.

## Teknologi yang Digunakan

- HTML5
- CSS3
- JavaScript
- SVG untuk visualisasi gauge dan grafik
- ESP32 sebagai mikrokontroler
- MPX5050GP sebagai sensor tekanan
- WebSocket untuk komunikasi data
- LocalStorage untuk penyimpanan riwayat dan pengaturan

## Format Data ESP32

Antarmuka mendukung pesan JSON dengan format berikut:

```json
{
  "pressure": 120.5,
  "voltage": 1.234
}
```

Alternatif nama parameter yang didukung:

```json
{
  "pressure_mmHg": 120.5,
  "voltage_V": 1.234
}
```

Nilai tekanan yang diterima antarmuka harus sudah dikonversi menjadi mmHg oleh firmware ESP32 atau sistem pemrosesan data.

## Cara Menjalankan

1. Unduh atau clone repositori.
2. Buka file HTML utama menggunakan browser modern.
3. Masuk ke menu **Pengaturan**.
4. Masukkan alamat WebSocket ESP32 yang sesuai dengan firmware.
5. Hubungkan perangkat dan pastikan format data JSON sesuai.
6. Pantau pembacaan tekanan, grafik, dan gauge.
7. Simpan hasil pengujian dan ekspor data jika diperlukan.

## Status Pengembangan

Proyek ini merupakan prototipe antarmuka monitoring dan pencatatan pengujian. Integrasi perangkat keras, validasi pengukuran, serta pengujian kinerja perlu dilakukan sebelum hasilnya digunakan untuk keperluan teknis atau klinis.

## Catatan Keselamatan dan Validasi

Gauge dengan rentang 0–500 mmHg merupakan rentang visualisasi perangkat lunak, bukan bukti akurasi pengukuran atau batas kelulusan alat. Validasi harus menggunakan alat standar tekanan yang sesuai dan tertelusur, serta prosedur pengujian yang berlaku.

Sistem ini tidak boleh dianggap sebagai alat kalibrasi tersertifikasi hanya berdasarkan tampilan perangkat lunaknya.

## Lisensi

Lisensi belum ditetapkan. Tentukan lisensi proyek sebelum mengizinkan penggunaan, modifikasi, dan distribusi oleh pihak lain.
