# Task Day-3

## A. Aplikasi.
Aplikasi adalah suatu perangkat lunak yang berjalan dan berfungsi spesifik secara langsung untuk pengguna akhir. Aplikasi dapat berjalan mandiri atau bersamaan dengan sekelompok program.

## B. Membuat Simple Application (Nodejs, Golang, Python3).

Kita akan membuat aplikasi sederhana pada server ataupun local, disini saya menggunakan local saya untuk pembuatan Simple Application.

* Golang

Go adalah bahasa pemrograman yang dibuat di Google pada tahun 2009 oleh Robert Griesemer, Rob Pike, dan Ken Thompson. bahasa pemrograman sumber terbuka yang mudah, sederhana, efisien. Selain itu, Go memiliki level yang sama dengan Java.

1. Sebelum membuat Aplikasinya, Kita buat directory terlebih dahulu untuk Aplikasi Golang. Kemudian, download Engine dari Golang-nya dengan Command 
```bash 
wget https://golang.org/dl/go1.16.5.linux-amd64.tar.gz && sudo su
```
Setelah download selesai, Kita otomatis akan dibawa ke root, maka dari itu Kita harus melakukan Command.
```bash
rm -rf /usr/local/go && tar -C /usr/local -xzf go1.16.5.linux-amd64.tar.gz && exit
```
<img src="Dokumentasi Golang/Golang Step-1.png">

2. Selanjutnya, masukkan Path Go pada .bashrc, lakukan Command "sudo nano .bashrc". Kita akan dibawa pada text editor dan Kita scroll ke paling bawah kemudian masukkan Path-nya yaitu.
```bash
export PATH=$PATH:/usr/local/go/bin
```
<img src="Dokumentasi Golang/Golang Step-2.png">

3. Lakukan verifikasi, ini juga untuk memastikan bahwa Golang benar-benar dapat Kita gunakan.

<img src="Dokumentasi Golang/Golang Step-3.png">

4. Buat file dengan Command.
```bash
nano (nama file, bebas).go
```
Nama file saya "index". Tujuannya agar Kita bisa memasukkan Script aplikasinya, setelah itu masukkan Script berikut.
```bash
package main

import "fmt"

func main() {
    fmt.Println("Hello World!")
}
```
Kata "Hello World!" Saya custom menjadi "Do You Need Love?".
<img src="Dokumentasi Golang/Golang Step-4.png">

5. Jalankan Aplikasi Golang dengan Command.
```bash
go run index.go
```
<img src="Dokumentasi Golang/Golang Step-5.png">

6. Saya melakukan Build pada Aplikasi, agar nantinya Aplikasi dapat d gunakan pada Device lain atau dengan kata lain di akses publik. Command untuk build.
```bash
go build index.go
```
Setelah itu, Jalankan Aplikasi yang di bulid dengan Command.
```bash
./index
```
<img src="Dokumentasi Golang/Golang Step-6.png">

* Nodejs

NodeJs adalah runtime untuk lingkungan JavaScript di luar peramban web yang dibangun di atas mesin JavaScript V8.

1. Karena sebelumnya Kita sudah meng-install Engine dan Nodejs, Kita langsung saja pada tahap pembuatan Directory untuk Simple Application Nodejs, kemudian inisiasi Directory dengan Command.
```bash
npm init -y
```
<img src="Dokumentasi Nodejs/Nodejs Step-1.png">

2. Selanjutnya, Install Framework yaitu ExpressJS, gunakan Command berikut untuk installasi.
```bash
npm install express --save
```
<img src="Dokumentasi Nodejs/Nodejs Step-2.png">

3. Buat sebuah file untuk memasukkan script.
```bash
nano index.js
```
Kemudian masukkan Script berikut.
```bash
const express = require("express");
const app = express();
const port = 3000;

app.get("/", (req, res) => {
  res.send("Hello World!");
});

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`);
});
```
Sesuaikan port, disini Saya mengganti kata "Hello World" menjadi "All You Need is Love".
<img src="Dokumentasi Nodejs/Nodejs Step-3.png">

4. Jika sudah, jalankan aplikasi nodejs dengan Command.
```bash
node index.js
```
<img src="Dokumentasi Nodejs/Nodejs Step-4.png">

5. Kita check di web browser untuk memastikan aplikasi berjalan dengan baik.
<img src="Dokumentasi Nodejs/Nodejs Step-5.png">

6. Pada terminal, Saya menambahkan tab kerja agar Kita dapat meng-generate url dari localtunnel. Hal ini dilakukan agar aplikasi yang Kita buat dapat di akses secara publik.
```bash
lt --port 3000
```
7. Lalu Kita check dengan web browser dengan memasukkan url yang sudah di-Generate.
<img src="Dokumentasi Nodejs/Nodejs Step-6.png">
<img src="Dokumentasi Nodejs/Nodejs Step-7.png">

* Python3

Python adalah Python merupakan bahasa pemrograman tingkat tinggi yang diracik oleh Guido van Rossum. Python banyak digunakan untuk membuat berbagai macam program, seperti: program CLI, Program GUI (desktop), Aplikasi Mobile, Web, IoT, Game, Program untuk Hacking.

1. Karena Python3 sudah tersedia secara deafult, maka kita hanya perlu menge-check-nya saja dengan Command.
```bash
python3 -v
```
<img src="Dokumentasi Python3/Python Step-1.png">

2. Seperti sebelumya, buat Directory untuk Simple Application Python. Lalu Install Package Manager dari Python3 yaitu PIP di dalam Directory tersebut.
```bash
sudo apt install python3-pip
```
<img src="Dokumentasi Python3/Python Step-2.png">

3. Berikutnya Install Framework dari python yaitu Flask.
```bash
pip install flask
```
<img src="Dokumentasi Python3/Python Step-3.png">

4. Seperti biasa, buat file untuk memasukkan Script dari aplikasi.
```bash
nano index.py
```
Script-nya
```bash
from flask import Flask
app = Flask(__name__)
@app.route("/")
def helloworld():
    return "Hello World"
if __name__ == "__main__":
    app.run()
```
Kata "Hello World" Saya rubah menjadi "We Need Love"
<img src="Dokumentasi Python3/Python Step-4.png">

5. Jalankan aplikasi dengan Command.
```bash
python3 index.py
```
<img src="Dokumentasi Python3/Python Step-5.png">

6. Check pada web browser.
<img src="Dokumentasi Python3/Python Step-6.png">

7. Seperti pada Nodejs, untuk meg-generate url, saya membuat tab baru, dan melakukan Command.
```bash
lt --port 5000
```
<img src="Dokumentasi Python3/Python Step-8.png">

8. Dan Aplikasipun berhasil diakses secara publik.
<img src="Dokumentasi Python3/Python Step-9.png">

## C. PM2 Sebagai Penjalan Aplikasi Secara Background.

PM2 adalah sebuah Tools yang digunakan agar aplikasi yang kita buat dapat berjalan secara daemon atau secara background, jadi kita tidak harus selalu membuka Server ataupun Local Terminal Kita.

1. Installasi.

Gunakan Command pada Home.
```bash
npm install pm2@latest -g
```
<img src="PM2/Install PM2.png">

2. Penggunaan pada Nodejs.

Kita menuju Directory dari Aplikasi Nodejs Kita, langsung saja masukkan Command.
```bash
pm2 start index.js
```
<img src="PM2/PM2 Nodejs 1.png">

Tutup Terminal kemudian buka web browser dan masukkan
```bash
localhost:3000
```
<img src="PM2/PM2 Nodejs 2.png">

3. Penggunaan pada Python3.

Sama seperti Nodejs, Kita masuk ke Directory Aplikasi Python Kita, kemudian masukkan Command.
```bash
pm2 start index.py --name index --interpreter python3
```
<img src="PM2/PM2 Python 1.png">

Tutup Terminal kemudian buka web bowser dan masukkan.
```bash
localhost:5000
```
<img src="PM2/PM2 Python 2.png">

4. Menghentikan PM2
Caranya masukkan saja Command di dalam Directory Aplikasi.
```bash
pm2 stop (nama file)
```

Begitulah rangkuman materi dari Hari ke-3, Minggu ke-1, di Stage-1. Akhir kata Terimaksih.