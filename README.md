**1. Pendahuluan<br>
1.1 Tujuan Pengujian**<br><br>
Skrip pengujian ini bertujuan untuk memverifikasi fungsionalitas fitur login pada aplikasi web Saucedemo secara menyeluruh. Ini mencakup:<br>
<br>
Skenario Sukses: Memastikan pengguna dapat login dengan kredensial yang valid dan diarahkan ke halaman yang benar.<br>
Skenario Gagal: Memastikan aplikasi menampilkan pesan error yang sesuai ketika pengguna memasukkan kredensial yang tidak valid.<br><br>
**1.2 Lingkup Pengujian**<br>
Skrip pengujian akan mencakup berbagai skenario login, termasuk:<br>
<br>
Login dengan kredensial yang valid<br>
Login dengan username yang salah<br>
Login dengan password yang salah<br>
Login dengan kedua username dan password yang salah<br>
Login dengan field yang kosong<br><br>
**2. Alat dan Teknologi**<br>
Selenium IDE: Alat yang digunakan untuk merekam dan memutar kembali tindakan pada browser.<br>
Browser: Browser yang digunakan untuk menjalankan pengujian (dalam kasus ini, tidak disebutkan secara spesifik dalam gambar).<br>
Bahasa Pemrograman: Selenium IDE menggunakan bahasa scripting sendiri yang cukup mudah dipahami.<br><br>
**3. Langkah-langkah Pengujian<br>
3.1 Skenario Login Sukses**<br>
No.	Command	Target	Value	Deskripsi<br><br>
1	open	https://www.saucedemo.com		Membuka halaman login Saucedemo di browser.<br>
2	set window size	1920x1053		Mengatur ukuran jendela browser agar konsisten selama pengujian.<br>
3	type	css=[data-test="username"]	standard_user	Mengisi field username dengan nilai yang valid.<br>
4	type	css=[data-test="password"]	secret_sauce	Mengisi field password dengan nilai yang valid.<br>
5	click	css=[data-test="login-button"]		Mengklik tombol login untuk mengirimkan data login.<br>
6	assert text	css=.app_logo	Swag Labs	Memastikan teks "Swag Labs" muncul setelah login berhasil.<br>
7	close		Menutup browser setelah pengujian selesai.<br><br>

**3.2 Skenario Login Gagal (Username Salah)**<br>
No.	Command	Target	Value	Deskripsi<br><br>
1	open	https://www.saucedemo.com		Membuka halaman login Saucedemo di browser.<br>
2	set window size	1920x1053		Mengatur ukuran jendela browser agar konsisten selama pengujian.<br>
3	type	css=[data-test="username"]	usererorr876	Mengisi field username dengan nilai yang tidak valid.<br>
4	type	css=[data-test="password"]	secret_sauce	Mengisi field password dengan nilai yang valid.<br>
5	click	css=[data-test="login-button"]		Mengklik tombol login untuk mengirimkan data login.<br>
6	assert text	css=[data-test="error"]	Epic sadface: Username and password do not match any user in this service	Memastikan pesan error yang sesuai muncul.<br>
7	close			Menutup browser setelah pengujian selesai.<br><br>

Catatan: Anda dapat menambahkan lebih banyak skenario gagal dengan mengganti nilai username dan password dengan kombinasi yang berbeda untuk memastikan semua kemungkinan error tercakup.<br><br>
**
4. Evaluasi**<br><br>
Skrip pengujian ini telah berhasil memverifikasi baik skenario login sukses maupun gagal pada aplikasi Saucedemo. Hasil pengujian menunjukkan bahwa aplikasi berfungsi dengan baik dalam memvalidasi kredensial pengguna dan menampilkan pesan error yang sesuai.<br>

