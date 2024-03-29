# Project4_Rindu-Pelita-M
Membuat repository baru dengan menggunakan akun GitHub pribadi, kemudian unggah tugas Python 5: OOP ke repository tersebut dan undang mentor @abdulghif sebagai kolaborator. Selanjutnya, mendokumentasikan homework pada file Readme.md.

## TASK 1
### Import Library
Pada program ini menggunakan library pandas yang di inisialisasi dengan nama pd
### Class MarketingDataETL
Pembuatan Class MarketingDataETL yang mana ini adalah kelas utama yang memiliki tiga metode: extract(), transform(), dan store().
### Metode extract()
1. Metode ini digunakan untuk mengekstrak data dari file CSV yang disebut "marketing_data.csv" yang terletak di direktori "/content/".
2. Data diekstrak menggunakan fungsi pd.read_csv() dari pandas dengan separator yang ditentukan sebagai ';'.
3. Setelah data diekstrak, metode mencetak data sebelum transformasi dilakukan dan mengembalikan data tersebut.
### Metode transform()
1. Metode ini melakukan transformasi pada data yang telah diekstrak.
2. Jika kolom 'purchase_date' ada dalam data, metode ini mengubah tipe data kolom tersebut menjadi tipe datetime menggunakan pd.to_datetime().
3. Kemudian, baris dengan nilai null dalam kolom 'purchase_date' dihapus menggunakan dropna().
4. Data yang telah ditransformasi dicetak ke konsol dan disimpan kembali dalam atribut data.
5. Metode ini mengembalikan data yang telah ditransformasi.
### Metode store()
1. Metode ini bertanggung jawab untuk menyimpan data yang telah diolah.
2. Jika objek kelas memiliki atribut data, metode ini menyimpan data tersebut dalam file CSV dengan nama "marketing_data_processed.csv" tanpa menyertakan indeks.
3. Jika tidak ada data yang tersedia, metode ini mencetak pesan bahwa tidak ada data untuk disimpan.
### Pemanggilan Metode
Setelah kelas MarketingDataETL diinisialisasi sebagai objek data, metode extract() dipanggil untuk mengekstrak data, diikuti oleh metode transform() untuk mentransformasi data tersebut, dan terakhir metode store() untuk menyimpan data yang telah diolah ke dalam file CSV.

## TASK 2
### Import Library
Pada task 2 ini, kita membutuhkan library Pandas yang akan diinisialisasi dengan nama np
### Class TargetedMarketingETL
1. Class ini mewarisi fungsionalitas dari kelas MarketingDataETL.
2. Class ini memiliki beberapa metode didalamnya yaitu : segment_customers(), transform() dan store_segmented_data().
### Metode segment_customers()
1. Metode ini membagi pelanggan ke dalam tiga segmen berdasarkan jumlah yang dihabiskan oleh mereka: 'Low Spending', 'Medium Spending', dan 'High Spending'.
2. Pengelompokan dilakukan dengan menggunakan kondisi-kondisi yang ditentukan dan fungsi np.select() dari NumPy.
### Metode transform()
#### Pemanggilan Metode transform() dari Kelas Induk:
Pertama, metode transform() dari kelas induk (MarketingDataETL) dipanggil menggunakan super().transform(). Ini memungkinkan kelas turunan (TargetedMarketingETL) untuk memanfaatkan fungsionalitas yang ada di kelas induk tanpa perlu mengulangi kode yang sama.
#### Pemanggilan Metode segment_customers():
Setelah metode transform() dari kelas induk selesai dieksekusi, metode segment_customers() dari kelas turunan (TargetedMarketingETL) dipanggil. Metode ini adalah bagian tambahan dari transformasi yang spesifik untuk kelas turunan. Ini bertanggung jawab untuk mengelompokkan pelanggan berdasarkan jumlah yang dihabiskan oleh mereka, dan menambahkan kolom baru yang menunjukkan segmen pengeluaran pelanggan ke dalam data.

### Metode store_segmented_data()
1. Metode ini bertanggung jawab untuk menyimpan data yang telah di-segmentasi ke dalam file Excel.
2. Data disimpan dalam format Excel menggunakan metode to_excel() dari pandas.

### Pemanggilan Metode
1. Pada bagian ini, objek targeted_etl dibuat menggunakan kelas TargetedMarketingETL dengan memberikan nama file CSV "marketing_data.csv" sebagai argumen.
2. Kemudian, dilakukan ekstraksi, transformasi, dan penyimpanan data dengan memanggil metode yang sesuai dari objek targeted_etl.
