# Task Day-1

## A. Apa Itu DevOps?
Merupakan singkatan dari 2 kata, yaitu Developmet dan Operation. Dari 2 Kata ini bisa disimpulkan bahwa DevOps bekerja sebagai penghubung antara Development dan Operation. Agar bisa lebih cepat beradaptasi terhadap pembaruan product sehingga saat deployment minim hambatan dan berjalan lancar.

## B. Install Ubuntu Server

### 1. Environment Untuk Server
Untuk melakukan installasi Ubuntu Server, Kita perlu terlebih dahulu menentukan Environment yang akan digunakan. Berikut adalah Step by Step-nya :

1. Mencari lokasi file Ubuntu Server yang sudah Saya download.

<img src="Dokumentasi/Installing Step-1.jpg">

2. Lalu, mengisi kolom Nama, Username, dan Password.

<img src="Dokumentasi/Installing Step-2.jpg">

3. Menentukan Memory Penyimpanan yang akan digunakan oleh Ubuntu Server. Disini Saya menggunakan 20GB.

<img src="Dokumentasi/Installing Step-3.jpg">

4. Kemudian Setup RAM, CPU, dan Network Adapter.

<img src="Dokumentasi/Installing Step-4.jpg">
Ket : RAM 2048MB atau 2GB

<img src="Dokumentasi/Installing Step-5.jpg">
Ket : CPU 1 Core

<img src="Dokumentasi/Installing Step-6.jpg">
Ket : Network Adapter menggunakan "Bridge"

## 2. Installing Ubuntu Server
Setelah menentukan Environment, kita akan dibawa ke tampilan Installasi Ubuntu Server

1. Pemilihan Bahasa. Sesuai dengan arahan, Saya menggunakan Bahasa Inggris.

<img src="Dokumentasi/Installing Step-7.jpg">

2. Kemudian Setup Networking. Pilih saja ens33, kemudian Kita akan di arahkan untuk memilih IP, pilihlah IPv4.

<img src="Dokumentasi/Installing Step-8.jpg">

3. Berikutnya, ubah "IPv4 Method" menjadi Manual, dan Kita masukkan Subnet, Address, Gateway, dan Nama Server. Sesuaikan Alamat IP dengan jaringan yang tersambung dengan kalian. Untuk menge-checknya bisa menggunakan Command
```bash
ipconfig
```
Untuk OS Windows dan dilakukan di CMD, dan menggunakan Command
```bash
ip a
```
Untuk OS Linux Ubuntu.

<img src="Dokumentasi/Installing Step-9.jpg">

4. Setelah Kita simpan Setup Networkingnya, Kita diarahkan untuk memilih apakah Storage-nya akan di set Otomatis atau Custom. Disini Saya memilih Custom.

<img src="Dokumentasi/Installing Step-10.jpg">

5. Pilih bagian "freespace", dan kemudian pilih "Add GPT".

<img src="Dokumentasi/Installing Step-11.jpg">
Ket : Memory Swap 2GB, Swap adalah Memory yang akan di ambil apabila RAM Kita sudah penuh.

<img src="Dokumentasi/Installing Step-12.jpg">
Ket : Memory Root Menggunakan sisanya. Root adalah Memory yang digunakan untuk menyimpan aplikasi-aplikasi yang Kita Install.

6. Memasukkan Nama, Nama Server, Username, dan Password.

<img src="Dokumentasi/Installing Step-13.jpg">

7. Install OpenSSH.

<img src="Dokumentasi/Installing Step-14.jpg">
Ket : Ini dilakukan agar Server yang Kita buat dapat Kita remote oleh Local Kita.

8. Proses Finishing Ubuntu Server.

<img src="Dokumentasi/Installing Step-15.jpg">

9. Jika Finishing sudah selesai, Selamat Server yang Kita buat kini sudah ada. Untuk masuk ke Server, masukkan Username dan Password yang tadi Kita buat saat melakukan installasi.

<img src="Dokumentasi/Installing Step-16.jpg">

10. Dikarenakan ada kesalahan saat Saya menentukan alamat IP, Saya melakukan Setup Network kembali dengan menggunakan Command.
```bash
sudo nano /etc/netplan/00-installer-config.yaml
```
<img src="Dokumentasi/Installing Step-17.jpg">
<img src="Dokumentasi/Installing Step-18.jpg">

11. Kemudian, meng-apply Setup Network dengan Command "sudo netplan apply", dan melakukan test Ping untuk memastikan bahwa Server benar-benar sudah mendapat akses internet.

<img src="Dokumentasi/Installing Step-19.jpg">
<img src="Dokumentasi/Installing Step-20.jpg">

Mungkin, begitulah Resume dari pelajaran Hari ke-1, Minggu Ke-1 di Stage-1. Akhir Kata Terimakasih.