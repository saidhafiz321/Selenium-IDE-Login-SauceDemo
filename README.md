1. Pendahuluan
1.1 Tujuan Pengujian
Skrip pengujian ini bertujuan untuk memverifikasi fungsionalitas fitur login pada aplikasi web Saucedemo. Secara spesifik, skrip ini akan:

Memastikan pengguna dapat masuk ke aplikasi dengan kredensial yang valid.
Memeriksa apakah setelah login, pengguna diarahkan ke halaman yang benar (halaman utama).
1.2 Lingkup Pengujian
Skrip ini fokus pada skenario login yang sukses dengan menggunakan kredensial pengguna standar (standard_user dan secret_sauce). Skrip ini tidak mencakup skenario error seperti:

Login dengan kredensial yang salah
Login dengan field yang kosong
Error pada elemen halaman
2. Alat dan Teknologi
Selenium IDE: Alat yang digunakan untuk merekam dan memutar kembali tindakan pada browser.
Browser: Browser yang digunakan untuk menjalankan pengujian (dalam kasus ini, tidak disebutkan secara spesifik dalam gambar).
Bahasa Pemrograman: Selenium IDE menggunakan bahasa scripting sendiri yang cukup mudah dipahami.
3. Langkah-langkah Pengujian
No.	Command	Target	Value	Deskripsi
1	open	https://www.saucedemo.com		Membuka halaman login Saucedemo di browser.
2	set window size	1920x1053		Mengatur ukuran jendela browser agar konsisten selama pengujian.
3	type	css=[data-test="username"]	standard_user	Mengisi field username dengan nilai "standard_user".
4	type	css=[data-test="password"]	secret_sauce	Mengisi field password dengan nilai "secret_sauce".
5	click	css=[data-test="login-button"]		Mengklik tombol login untuk mengirimkan data login.
6	assert text	css=.app_logo	Swag Labs	Memastikan teks "Swag Labs" muncul setelah login berhasil, sebagai indikator bahwa pengguna telah masuk ke halaman utama.
7	close			Menutup browser setelah pengujian selesai.

Ekspor ke Spreadsheet
4. Penjelasan Detail
Locator: Skrip menggunakan CSS selector untuk menemukan elemen di halaman web. Ini adalah metode yang cukup fleksibel untuk mengidentifikasi elemen.
Assertion: Perintah assert text digunakan untuk memverifikasi apakah teks tertentu muncul di halaman. Ini adalah cara sederhana untuk memastikan bahwa pengujian berjalan sesuai harapan.
5. Evaluasi
Berdasarkan skrip di atas, dapat disimpulkan bahwa skrip ini berhasil mengotomatiskan proses login ke aplikasi Saucedemo dengan menggunakan kredensial yang valid. Namun, perlu diingat bahwa ini hanya merupakan skenario pengujian yang sangat sederhana. Untuk mendapatkan hasil pengujian yang lebih komprehensif, perlu ditambahkan skenario pengujian lainnya, seperti:

Skenario negatif: Melakukan login dengan kredensial yang salah, field kosong, atau kombinasi yang tidak valid.
Skenario batas: Menguji dengan berbagai jenis input, seperti karakter spesial, panjang password yang berbeda, dll.
Skenario pengguna: Menguji dengan berbagai jenis pengguna (misalnya, pengguna terdaftar, pengguna baru).
