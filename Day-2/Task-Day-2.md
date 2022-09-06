# Task Day-2

## A. Apa Itu Network?
Network adalah Jaringan yang memudahkan pengguna 1 dengan yang lainnya untuk bisa bertukar informasi dan data, berbagi resource dll, yang terhubung melalui transmisi Kabel atau Tanpa Kabel (Wireless).

## B. Setup Networking Pada Ubuntu Server.
Setup Networking, dilakukan, agar Server yang Kita gunakan bisa mendapat akses internet, bisa mengakses remote, dan memliki alamat IP sendiri.

1. Seperti pada rangkuman sebelumnya, lakukan Command pada Ubuntu Server
```bash
sudo nano /etc/netplan/00-installer-config.yaml
```
Disini sekaligus Kita Apply yang sudah Kita Setup dengan Command
```bash
sudo netplan apply
```
<img src="Setup Network/Setup Nw Step-1.jpg">
Ket : IP awal memiliki Address 104, saya rubah menjadi 103.

2. Test Ping untuk memastikan Address yang dirubah dapat di akses. Command
```bash
ping 8.8.8.8
``` 
atau
```bash
ping google.com
```
<img src="Setup Network/Setup Nw Step-2.jpg">

3. Setelah itu melakukan Update dan Upgrade saat Kita sudah berhasil melakukan remote kepada Server, agar Server selalu up-to-date.

<img src="Setup Network/Setup Nw Step-3.jpg">

4. Berikutnya, Kita coba install Aplikasi Apache2. Command
```bash
sudo apt install apache2
```
<img src="Setup Network/Setup Nw Step-4.jpg">

5. Setelah installasi selesai, Kita check apakah Aplikasi Apace2 berjalan di Server, cara menge-checknya adalah dengan Command
```bash
sudo systemctl status apache2
```
<img src="Setup Network/Setup Nw Step-5.jpg">

6. Berikutnya Kita Check di Web Browser agar semakin meyakinkan bahwa Apache2 dapat berjalan dengan baik. Masukkan saja IP yang tadi sudah Kita Setup ke Web Browser.

<img src="Setup Network/Setup Nw Step-6.jpg">

## C. Localtunnel
Penginstallan Localtunnel dilakukan, agar Kita bisa berbagi layanan Website dari Lokal Komputer maupun Server Kita ke Publik dengan akses Url yang diberikan oleh Localtunnel. Berikut tahapan installasi Localtunnel :

1. Install Engine terlebih dahulu dengan Command
```bash
sudo apt install curl
```
<img src="Localtunnel/Localtunnel Step-1.jpg">

2. Kemudian Download Nodejs dengan Command
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
```
<img src="Localtunnel/Localtunnel Step-2.jpg">

3. Kemudian Command
```bash
exec bash
```
untuk menjalankan Nodejs yang sudah Kita Download.

Command 
```bash
nvm install 14
```
untuk menginstall Nodejs V.14.
<img src="Localtunnel/Localtunnel Step-3.jpg">

4. Berikutnya Install Localtunnel dengan Command
```bash
npm install -g localtunnel
```
<img src="Localtunnel/Localtunnel Step-4.jpg">

5. Generate url dengan Command
```bash
lt --port 80
```
ini berupa http.
Lakukan penge-check-an pada Web Browser dan Smartphone.
<img src="Localtunnel/Localtunnel Step-5.jpg">
<img src="Localtunnel/Localtunnel Step-6.jpg">
Ket : Penge-check-an di Browser PC.
<img src="Localtunnel/Localtunnel Step-7.jpg">
Ket : Penge-check-an di Browser Smartphone menggunakan Jaringan Seluler

Kesimpulan, Kita berhasil berbagi layanan Website secara Publik.

Mungkin itu Resume untuk Hari ke-2, Minggu ke-1, di Stage-1. Akhir Kata Terimakasih