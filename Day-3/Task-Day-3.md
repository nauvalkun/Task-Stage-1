# Task Day-3

## A. Apa Itu Web Server?
Web Server adalah perangkat lunak atau software yang berfungsi untuk layanan data dan menerima permintaan client baik berupa HTTP atau HTTPS. Contoh dari Web Server adalah Apache2, Nginx, dll.

## B. Installasi Web Server
Pada bagian ini, Saya akan menampilkan dokumentasi Step by Step cara menginstall salah satu Web Server yaitu Nginx.

1. Pastikan Ubuntu Server sudah melakukan update dan upgrade, jika belum lakukan dengan Command.
```bash
sudo apt update; sudo apt upgrade
```
2. Kemudian lakukan Installasi dengan Command.
```bash
sudo apt install nginx
```
<img src="Dokumentasi Nginx/Nginx1.png">

3. Jika sudah lakukan Crosscheck dengan Command.
```bash
nginx -v
```
<img src="Dokumentasi Nginx/Nginx2.png">

4. Untuk melihat status Nginx berjalan atau tidak, lakukan Command.
```bash
sudo systemctl status nginx
```
<img src="Dokumentasi Nginx/Nginx3.png">

5. Silahkan aktifkan sistem nginx menggunakan Perintah.
```bash
sudo systemctl enable nginx
```
<img src="Dokumentasi Nginx/Nginx4.png">

6. Check Nginx melalui web browser dengan cara memasukkan IP Server.
<img src="Dokumentasi Nginx/Nginx5.png">

## C. Reverse Proxy
Reverse proxy adalah suatu konfigurasi yang digunakan untuk mengubah jalur traffic, misalkan aplikasi menggunakan port 3000 tetapi agar dapat di akses melalui port 80 maka harus menggunakan reverse proxy.

Sekarang Saya akan menunjukkan dokumentasi Saya saat melakukan konfigurasi Reverse Proxy dengan Nginx.

1. Pertama-tama Kita akan membuat config Reverse Proxy di directory Nginx. Masukkan Perintah.
```bash
cd /etc/nginx/
```
<img src="Dokumentasi Reverse Proxy/RP1.png">

2. Buat sebuah Directory dengan nama bebas, disini saya menamakan "dumbways", dan check kepemilikan Directory.
```bash
sudo mkdir dumbways
```
<img src="Dokumentasi Reverse Proxy/RP2.png">

3. Ubah kepemilikan Directory agar kedepannya Kita tidak perlu memasukkan Command "sudo" lagi.
```bash
sudo chown ubuntu:ubuntu dumbways
```
<img src="Dokumentasi Reverse Proxy/RP3.png">

4. Masuk ke Directory dumbways.
```bash
cd dumbways
```
<img src="Dokumentasi Reverse Proxy/RP4.png">

5. Tambahkan file untuk konfigurasi Reverse proxy. Beri nama bebas, Saya menamainya "my.reverse-proxy.conf".
```bash
nano my.reverse-proxy.conf
```
<img src="Dokumentasi Reverse Proxy/RP5.png">

6. Lakukan konfigurasi seperti pada gambar. Masukkan IP kalian beserta Port aplikasi di bagian "proxy_pass"

<img src="Dokumentasi Reverse Proxy/RP6.png">

7. Stetlah Kita simpan konfigurasi tadi, berikutnya keluar Directory 1 langkah, lalu lakukan konfigurasi lagi pada nginx.conf
```bash
cd ..
```
```bash
sudo nano nginx.conf
```
<img src="Dokumentasi Reverse Proxy/RP7.png">
<img src="Dokumentasi Reverse Proxy/RP8.png">

8. Kalian akan di bawa pada text editor, kemudian scroll ke bawah dan masukkan lokasi dari proxy kalian tadi.
```bash
include /etc/nginx/dumbways/*;
```
<img src="Dokumentasi Reverse Proxy/RP9.png">

9. Untuk melihat apakah syntax sudah sukses, lakukan Perintah.
```bash
sudo nginx -t
```
<img src="Dokumentasi Reverse Proxy/RP10.png">

10. Lakukan Restart atau Reload pada Nginx agar konfigurasi tadi bisa kita pakai.
```bash
sudo systemctl restart nginx
```
<img src="Dokumentasi Reverse Proxy/RP11.png">

11. Masuk ke Local Server untuk membuat sebuah virtual host. Kemudian masukkan Command
```bash
sudo nano /etc/hosts
```
<img src="Dokumentasi Reverse Proxy/RP12.png">

12. Lalu masukkan IP server dan domainnya.

<img src="Dokumentasi Reverse Proxy/RP13.png">

13. Check di Web Browser dengan cara memasukkan domain yang kita buat. Jika muncul seperti pada gambar, maka Reverse Proxy Kita sudah berjalan dengan baik. Hanya saja dia belum membaca Aplikasi apapun di server.

<img src="Dokumentasi Reverse Proxy/RP14.png">

14. Lakukan Clone terhadap Aplikasi yang disediakan di github ke 2 Server yang sudah dibuat.

<img src="Dokumentasi Reverse Proxy/RP15.png">
<img src="Dokumentasi Reverse Proxy/RP16.png">

15. Kemudian masuk ke Directory yang sudah Kita clone tadi, dan lakukan install module node.js.
```bash
npm install
```
<img src="Dokumentasi Reverse Proxy/RP17.png">
<img src="Dokumentasi Reverse Proxy/RP18.png">

16. Selanjutnya, buka saja server yang menjadi gateway, atau mudahnya server yang kita install Nginx, lalu berikan Command agar aplikasi bisa berjalan.
```bash
npm start
```
<img src="Dokumentasi Reverse Proxy/RP19.png">

17. Jika Aplikasi sudah berjalan akan memiliki tampilan Server seperti pada gambar.

<img src="Dokumentasi Reverse Proxy/RP20.png">

18. Masukkan Domain yang Kita buat pada Web Browser.

<img src="Dokumentasi Reverse Proxy/RP21.png">

## D. Load Balancing

Load Balancing adalah suatu jaringan komputer yang menggunakan metode untuk mendistribusikan beban kerjaan pada dua atau bahkan lebih suatu koneksi jaringan secara seimbang agar pekerjaan dapat berjalan optimal dan tidak overload (kelebihan) beban pada salah satu jalur koneksi.

Selanjutnya, Saya akan melakukan Konfigurasi untuk Load Balance.
1. Masuk kembali ke lokasi file kita melakukan konfigurasi untuk Reverse Proxy.
```bash
sudo nano /etc/nginx/dumbways/my.reverse-proxy.conf
```
<img src="Dokumentasi Load Balancing/LB1.png">

2. Check IP dari Server yang Kita buat melalui Localserver Kita. Karena Saya membuat Server menggunakan Multipass, Maka, menggunakan Command.
```bash
multipass ls
```
<img src="Dokumentasi Load Balancing/LB2.png">

3. Kembali ke text editor pada server, masukkan script tambahan dan masukkan IP Server yang Kita check sebelumnya.
```bash
upstream domain {
    server 10.255.253.32:3000;
    server 10.255.253.41:3000;
}
server {
    server_name mydomain.xyz

    location / {
            proxy_pass https://domain;
    }
}
````
<img src="Dokumentasi Load Balancing/LB3.png">

4. Lakukan check pada konfigurasi dengan Command.
```bash
sudo nginx -t
```
<img src="Dokumentasi Load Balancing/LB4.png">

5. Jika terjadi error pada nginx.service, Lakukan Command.
```bash
sudo service nginx start
```
6. Jika tidak ada langsung saja lakukan restart pada Nginx. Gunakan Command
```bash
sudo systemctl restart nginx
```
<img src="Dokumentasi Load Balancing/LB5.png">

7. Kita jalankan Aplikasi di kedua server.

<img src="Dokumentasi Load Balancing/LB6.png">
<img src="Dokumentasi Load Balancing/LB7.png">

8. Check Domain pada Web Browser.

<img src="Dokumentasi Load Balancing/LB8.png">

9. Matikan Aplikasi pada salah satu server.

<img src="Dokumentasi Load Balancing/LB9.png">
<img src="Dokumentasi Load Balancing/LB10.png">
<img src="Dokumentasi Load Balancing/LB11.png">
<img src="Dokumentasi Load Balancing/LB12.png">

## E. Process Manager 2 (PM2)
Kita melakukan Installasi PM2 pada server, agar Aplikasi dapat berjalan secara Background, atau mudahnya, kita tidak harus membuka terminal server.

1. Jika belum menginstall pm2, lakukan dengan Command.
```bash
sudo npm install pm2@latest -g
```
2. Sekarang Kita jalankan Aplikasi pada server menggunakan PM2. Gunakan Command.
```bash
pm2 start npm --name "frontend1" -- start
```
<img src="Dokumentasi PM2/PM2 1.png">
<img src="Dokumentasi PM2/PM2 2.png">

3. Kita coba logout dari server.
```bash
exit
```
<img src="Dokumentasi PM2/PM2 3.png">
<img src="Dokumentasi PM2/PM2 4.png">

4. Lalu check domain pada Web Browser, dan aplikasi masih bisa di akses.
<img src="Dokumentasi PM2/PM2 5.png">

Demikian rangkuman materi Hari ke-3, Minggu ke-2, di Stage-1. Akhir kata Terimakasih.