# Tugas-4-OAK
# NAMA  : Raisya Salshabilla 
# NIM   : 09011382429147
# KELAS : SKU2A
# Organisasi dan Arsitektur Komputer 

## Contoh kasus Pipeline Processing 
## Apa itu Pipeline Processing?
**Pipeline processing** adalah metode pelaksanaan tugas atau operasi secara berurutan, di mana setiap tugas diteruskan ke tahap pemrosesan berikutnya tanpa menunggu penyelesaian tugas sebelumnya. Ini adalah teknik komputasi paralel yang sangat efisien yang memungkinkan pelaksanaan beberapa tugas secara bersamaan, sehingga menghasilkan peningkatan hasil dan kinerja keseluruhan.


## Kasus Penggunaan: Pipeline Processing – Keystone Data Pipeline (Netflix)

### Kasus:
- Pelaporan dan analisis waktu nyata.
- Streaming data dari perangkat IoT.
- Streaming data dari penggunaan aplikasi.

### Contoh: Keystone Data Pipeline dari Netflix
### Latar Belakang

Sebagai salah satu platform streaming terbesar di dunia, **Netflix** menangani miliaran event setiap hari. Event ini mencakup informasi seperti:
- Apa yang ditonton pengguna.
- Di mana dan kapan video diputar.
- Bagaimana pengguna berinteraksi dengan aplikasi (klik, scroll, crash, buffering, dll).

Untuk memastikan pengalaman pengguna yang optimal dan mendukung pengambilan keputusan berbasis data secara real-time, Netflix memerlukan sistem pemrosesan data yang cepat, andal, dan sangat skalabel.

Tantangan utama:
- Volume data sangat besar (big data).
- Butuh respons instan untuk deteksi anomali, rekomendasi konten, dan performa sistem.
- Perlu sistem yang fleksibel dan mampu menangani berbagai jenis data (semi-terstruktur, time series, logs, dll).

Solusinya adalah membangun **Keystone Data Pipeline**, sebuah sistem stream processing real-time internal Netflix.

---

### Struktur Pipeline Netflix (Keystone Data Pipeline)

#### 1. Data Ingestion (Pengumpulan Data)
- Sumber data: ribuan perangkat (TV, smartphone, browser, smart TV).
- Gunakan **Apache Kafka** sebagai message broker untuk mengalirkan data secara real-time.
- Jenis data: pemutaran video, klik tombol, buffering, error, crash report, dll.

#### 2. Stream Processing
- Tools utama: **Apache Flink** atau **Apache Samza**.
- Proses yang dilakukan:
  - **Pembersihan data** (data cleansing).
  - **Transformasi** (ekstraksi informasi penting).
  - **Deteksi anomali** secara langsung.
  - **Agregasi data** (misalnya, menghitung jumlah penonton per detik).

#### 3. Routing dan Storage
- Data hasil pemrosesan dikirim ke berbagai jalur penyimpanan dan sistem:
  - **Amazon S3 / Hadoop (HDFS)** → untuk analisis batch.
  - **Elasticsearch** → untuk pencarian cepat.
  - **DynamoDB / Cassandra** → untuk kebutuhan kueri real-time.
  - **Redshift / Apache Druid** → untuk analytics dashboard.

#### 4. Consumption Layer (Pemanfaatan Data)
Data yang sudah siap digunakan oleh berbagai tim:
- **Tim rekomendasi konten** → untuk menyesuaikan konten dengan preferensi pengguna.
- **Dashboard pemantauan layanan** → untuk tim operasional.
- **Sistem alert** → untuk mendeteksi dan merespon masalah teknis secara otomatis.

![image](https://github.com/user-attachments/assets/ac8194ce-f71c-490e-bf36-7eddd2913979)

---

### Kesimpulan
Keystone Data Pipeline dari Netflix merupakan contoh nyata implementasi **pipeline processing** berbasis **real-time stream processing** dalam skala besar. Dengan memanfaatkan arsitektur yang modular dan teknologi seperti Kafka, Flink, dan Elasticsearch, Netflix mampu:
- Mengelola miliaran event per hari secara efisien.
- Menyediakan insight dan reaksi instan terhadap perilaku pengguna dan performa sistem.
- Mendukung berbagai tim internal melalui data yang bersih, relevan, dan dapat diakses secara real-time maupun batch.
Hal ini menunjukkan bahwa pipeline processing sangat penting dalam sistem yang membutuhkan **kecepatan, skalabilitas, dan ketahanan data**, terutama dalam industri berbasis layanan digital seperti video streaming.

### Sumber : https://blog.skyvia.com/what-is-data-pipeline/ dan https://netflixtechblog.com/evolution-of-the-netflix-data-pipeline-da246ca36905




