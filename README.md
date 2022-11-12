# Project7
## Langkah-langkah Membuat Raster Mosaicing And Clipping

1. Buka QGIS dan cari file yang diunduh di panel Browser. Perluas file zip individual untuk menampilkan file .hgt. Tahan tombol Ctrl dan pilih semua file individual. Setelah dipilih, seret ke kanvas.

2. Anda akan melihat 11 layer individual dimuat di panel Layers dan ditampilkan di kanvas. Kami akan menggabungkan ubin individual ini menjadi satu mozaik. Pergi ke Memproses ‣ Toolbox.

3. Cari dan temukan GDAL Raster miscellaneous Merge tool. Klik dua kali untuk meluncurkannya.

4. Dalam dialog Gabungkan, klik tombol … di sebelah Input layer. Klik Pilih Semua untuk memilih semua lapisan individu.

5. Seperti disebutkan dalam detail lapisan dataset, tipe data input adalah bilangan bulat bertanda 16-bit. Untuk menjaga integritas data, kita harus menyimpan tipe data yang sama untuk layer gabungan. Pilih Int16 sebagai tipe data Keluaran. Juga format data keluaran default adalah GeoTiff. File GeoTiff bisa menjadi sangat besar jika tidak dikompresi. Pilih Kompresi Tinggi sebagai Profil. Klik Jalankan.

6. Setelah pemrosesan selesai, OUTPUT layer baru akan ditambahkan ke panel Layers. Jika lapisan tidak berada di bagian atas tumpukan, pilih dan seret ke bagian atas panel Lapisan.

7. Anda akan melihat bahwa lapisan OUTPUT berisi data elevasi gabungan dari ubin masukan individual. Visualisasi default hanya menampilkan nilai piksel dalam kisaran 0-255. Namun data kami berisi piksel dengan nilai -14 hingga 2371, menghasilkan rendering kontras yang rendah. Mari kita ubah menjadi visualisasi yang lebih baik. Klik tombol Open the layer Styling panel di panel Layers.

8. Di panel Layer Styling, klik dropdown Render type dan pilih Hillshade renderer. Opsi rendering ini sangat cocok untuk data elevasi.

9. Operasi umum lainnya saat bekerja dengan raster adalah dengan memotong raster ke area yang Anda minati. Untuk tutorial ini, kami akan mengklip layer gabungan ke batas negara untuk Sri Lanka. Temukan file ne_10m_admin_0_countries.zip yang diunduh dan perluas. Seret file ne_10m_admin_0_countries.shp ke kanvas.

10. Pilih layer ne_10m_admin_0_countries yang baru ditambahkan di panel Layers. Klik tombol Select Features by area atau single click pada Attributes Toolbar. Setelah dipilih, klik poligon Sri Lanka untuk memilihnya.

11. Pertahankan seleksi seperti apa adanya dan buka Processing Toolbox. Cari dan temukan GDAL Ekstraksi raster Klip raster dengan alat lapisan topeng. Klik dua kali untuk meluncurkannya.

12. Dalam dialog Clip Raster by Mask Layer, atur OUTPUT sebagai Input Layer. Pilih ne_10m_admin_0_countries sebagai layer Mask, dan centang kotak Selected features only. Masukkan 0,0000 sebagai Menetapkan nilai nodata yang ditentukan ke pita keluaran. Seperti sebelumnya, pilih Kompresi tinggi sebagai Profil. Klik Jalankan.

13. Sebuah OUTPUT layer baru akan ditambahkan ke panel Layers. Pada titik ini, mungkin sulit untuk melihat hasilnya karena kita memiliki terlalu banyak lapisan tumpang tindih yang terlihat. Klik tombol Kelola Tema Peta di panel Lapisan dan pilih Sembunyikan Semua Lapisan.

14. Aktifkan hanya layer OUTPUT terbaru dan beri gaya dengan perender Hilshade seperti yang dilakukan sebelumnya.

15. Lapisan elevasi keluaran gabungan dan subset untuk Sri Lanka sudah siap.

