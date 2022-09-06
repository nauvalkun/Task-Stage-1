# Task Day-1

## A. Apa Itu CI/CD?

CI/CD atau Continuous Integration dan Continuous Deployment merupakan metode untuk mengirimkan perubahan code secara terus menerus hingga aplikasi dapat release ke publik dengan otomatis.

Banyak keunggulan apabila kita menggunakan CI/CD, diantaranya dapat menyebarkan Aplikasi sesuai permintaan, Proses yang otomatis sehingga memudahkan pekerjaan, dapat melakukan rollback apabila terdapat Error.

## B. Implementasi CI/CD Menggunakan Cloudflare.

Di dalam Cloudflare terdapat fitur *Pages*, fitur ini berfungsi untuk menempatkan project-project yang sedang, akan, dan sudah di kerjakan.

Melakukan Implementasi CI/CD di Cloudflare, berikut adalah step-stepnya :

1. Mengikuti arahan, Kita di minta untuk Fork pada Repository yang ada pada link berikut : https://github.com/dumbwaysdev/wayshub-frontend .

<img src="Dokumentasi CI-CD/CI-CD 1.jpg">

2. Kemudian, pilih icon Fork yang ada di bagian atas. Otomatis Kita akan dibawa kembali ke akun Github Kita, dan Otomatis Repository sudah terduplikat di akun github kita.

<img src="Dokumentasi CI-CD/CI-CD 2.jpg">

3. Masuk ke akun Cloudflare Kita, dan buat Project baru di Cloudflare Pages, lalu setting bagian akun dan pilih Repository yang akan kita Deploy.

<img src="Dokumentasi CI-CD/CI-CD 3.jpg">

4. Lalu,Pastikan untuk mengisi nama dan branch yang digunakan, kemudian pada bagian build settings pilih framework yang digunakan, pastikan juga untuk memasukkan build commandnya. Jika sudah sesuai langsung klik Save and Deploy.

<img src="Dokumentasi CI-CD/CI-CD 4.jpg">

5. Tunggu proses Deploy hingga selesai.

<img src="Dokumentasi CI-CD/CI-CD 5.jpg">

6. Kita coba buka aplikasi menggunakan domains yang ada, pastikan aplikasi sudah berjalan

<img src="Dokumentasi CI-CD/CI-CD 6.jpg">
<img src="Dokumentasi CI-CD/CI-CD 7.jpg">

7. Sekarang kita coba akan mengedit aplikasi dibagian .html nya, yaitu index.html. Cari file dan Klik ikon Edit.

<img src="Dokumentasi CI-CD/CI-CD 8.jpg">

8. Disini Saya mengedit bagian title dengan menambahkan Nama Saya. Jika sudah, lakukan commit change dengan meng-klik ikon Commit Change

<img src="Dokumentasi CI-CD/CI-CD 9.jpg">

9. Jika sudah, otomatis perubahan akan langsung dibuild pada Cloudflare.

<img src="Dokumentasi CI-CD/CI-CD 10.jpg">

10. Tunggu hingga build selesai, dan Copy domain yang tersedia.

<img src="Dokumentasi CI-CD/CI-CD 11.jpg">

11. Proses CI/CD-pun berjalan lancar.

<img src="Dokumentasi CI-CD/CI-CD 12.jpg">

Demikian rangkuman dan praktek dari materi di Hari ke-1, Minggu ke-2, di Stage-1. Akhir kata Terimakasih