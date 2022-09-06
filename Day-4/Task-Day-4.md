# Task Day-4
## A. Version Control System
Merupakan Tools yang digunakan untuk memanage perubahan yang ada pada kode. Tools ini dapat membantu Developer untuk mentracking perubahan apa saja yang sudah dilakukan.

## B. Git
Git merupakan salah satu jenis dari VCS, Git memiliki fitur "distributed version control" dimana penyimpanan git tidak hanya pada 1 tempat saja. Tetapi semua orang yang terlibat dalam pengkodean proyek akan menyimpan database git, sehingga akan memudahkan dalam mengelola proyek baik offline maupun online. Selain itu git dapat dilakukan secara kolaborasi.

## C. Push App
Berikut adalah Step by Step Push/Upload file ke github :

1. Konfigurasi Git, dilakukan agar nantinya file dapat dipush pada akun yang sudah kita konfigurasikan.
```bash
git config --global user.name "(Username Kalian)"
```
```bash
git config --global user.email (Email Kalian)
```
<img src="Dokumentasi Push App/Push App 1.png">

2. Kemudian, lakukan Command
```bash
git init
```
untuk mengisiasi file agar dapat dibaca dan dipush oleh Git. Sekaligus Saya melakukan remote agar nantinya file secara spesifik dapat dipush pada Repository tujuan. Command
```bash
git remote add origin (SSH/HTTPS dari repository kalian)
```
<img src="Dokumentasi Push App/Push App 2.png">

3. Command
```bash
git add
```
untuk memasukkan file ke condition staged, jika sudah lakukan Command
```bash
git status
```
untuk Crosscheck, Jika file berwarna hijau maka dia sudah berhasil masuk pada kodisi staged dan siap untuk dicommit. Untuk meng-commit bisa menggunakan Command
```bash
git commit -m "(Pesan Commit)"
```
<img src="Dokumentasi Push App/Push App 3.png">

4. Step berikutnya sebelum melakukan Push, Kita check terlebih dahulu branch-nya, dilakukan agar memperjelas nantinya akan dipush pada branch apa di Repository Kita. Gunakan Command
```bash
git branch -a
```
Jika sudah yakin, maka Push dengan Command
```bash
git push origin master
```
maksud "master" disini adalah branch tadi yang sudah kita check.
<img src="Dokumentasi Push App/Push App 4.png">
Di Step ini saya juga langsung membuat branch baru dan masuk kedalam branch baru tersebut dengan Command
```bash
git branch -m (nama branch baru)
```
kemudian check apakah Kita sudah masuk ke branch tersebut.

5. Lakukan hal yang sama seperti di Step-4, dikarenakan ketentuan dari tugas, maka disini saya membuat 3 branch, dan melakukan Push kepada 2 branch sisanya.

<img src="Dokumentasi Push App/Push App 5.png">
<img src="Dokumentasi Push App/Push App 6.png">

Demikian adalah Step atau cara Push file ke github.

## C. Push Simple App
Ini adalah dokumentasi dari Push Simple App, masing-masing Aplikasi Saya buatkan satu Repository, sehingga ada tiga Repository. Kemudian, setiap Repository saya buatkan 3 branch yang bernama Development, Staging, Production.

1. Golang
* Branch Development

<img src="Dokumentasi Push App/Push App Golang 1.jpg">

* Branch Staging

<img src="Dokumentasi Push App/Push App Golang 2.jpg">

* Branch Production

<img src="Dokumentasi Push App/Push App Golang 3.jpg">

2. Nodejs
* Branch Development

<img src="Dokumentasi Push App/Push App Nodejs 1.jpg">

* Branch Staging

<img src="Dokumentasi Push App/Push App Nodejs 2.jpg">

* Branch Production

<img src="Dokumentasi Push App/Push App Nodejs 3.jpg">

3. Python3
* Branch Development

<img src="Dokumentasi Push App/Push App Python 1.jpg">

* Branch Staging

<img src="Dokumentasi Push App/Push App Python 2.jpg">

* Branch Production

<img src="Dokumentasi Push App/Push App Python 3.jpg">

Demikian adalah Rangkuman Materi Bootcamp Hari ke-4, Minggu ke-1, di Stage-1. Akhir kata Terimakasih.