# Task Day-2

## A. Apa Itu Terminal?
Trminal adalah jenis dari Command Promt atau Shell, dimana Kita bisa melaukan pembuatan file, folder, membuka akses, dan lain-lain. Sebelum di temukannya GUI (Graphical User Interface), aktivitas komputer ditampilkan dengan terminal, selain itu penggunaan terminal lebih ringan dan lebih efisien.

## B. Text Manipulation.
Didalam terminal Kita bisa melakukan text editor, akan tetapi, ada cara kedua untuk melakukan editting text, yaitu dengan memanipulasinya. Berikut adalah Command-command yang digunakan untuk Text manipulation.

1. Cat

Adalah Command yang memerintahkan untuk melihat isi text dari sebuah file.

```bash
cat (nama file)
```
<img src="Dokumentasi Text Manipulation/Cat 1.png">

* Ket : Untuk melihat isi file.

```bash
cat > (nama file)
```
<img src="Dokumentasi Text Manipulation/Cat 2.png">

* Ket : Untuk membuat file baru dan mengisi text pada file tersebut.

```bash
cat file1 file2 > file3
```
<img src="Dokumentasi Text Manipulation/Cat 3.png">

* Ket : Untuk membuat file baru, dan memasukkan text yang ada pada file1 dan file2 ke file3.

2. Sed
Command untuk merubah text yang ada didalam file.
```bash
sed -i 's/Hello/Hai/g' file3
```
<img src="Dokumentasi Text Manipulation/Sed.png">

3. Echo
Digunakan untuk mencetak pesan dari hasil perintah lain.
```bash
echo "Hello Dumbways" >> file5
```
<img src="Dokumentasi Text Manipulation/Echo 1.png">

* Ket : Memasukkan pesan kepada file5.

```bash
echo "Ganti Apa Aja" > file5
```
<img src="Dokumentasi Text Manipulation/Echo 2.png">

* Ket : Mereplace text pada file5 dengan text "Ganti Apa Aja".

4. Grep
Digunakan untuk mencari text dalam file.
```bash
grep Dumbways file3
```
<img src="Dokumentasi Text Manipulation/Grep 1.png">

* Ket : Untuk mencari kata "Dumbways' pada file3.

```bash
grep -c Dumbways file3
```
<img src="Dokumentasi Text Manipulation/Grep 2.png">

* Ket : Menhitung kata "Dumbways" pada file3.

```bash
grep Dumbways *
```
<img src="Dokumentasi Text Manipulation/Grep 3.png">

* Ket : Untuk mencari kata "Dumbways" terletak pada file apa saja.

5. Sort
Seperti namanya, Command ini berfungsi untuk mensortir isi dari file. Baik secara ascending maupun descanding.
```bash
sort file4
```
<img src="Dokumentasi Text Manipulation/Sort 1.png">

* Ket : Mensortir file secara ascending.

```bash
sort -r file4
```
<img src="Dokumentasi Text Manipulation/Sort 2.png">

* Ket : Mensortir file secara descending.

## C. Membuat Bash Sederhana.
Disini, Saya akan menunujukkan Step by Step pembuatan bash sederhana, disini saya membuat bash untuk menjalankan update dan upgrade, serta bash untuk membuat firewall port 22, 80, 443

### Bash Update dan Upgrade
1. Setelah masuk terminal, Saya melakukan Command.
```bash
nano task-update-upgrade.sh
```
<img src="Dokumentasi Bash Update/Bash Update 1.png">

2. Kita akan diarahkan ke text editor nano. Isi dengan perintah update dan upgrade yaitu,
```bash
sudo apt update
sudo apt upgrade
```
<img src="Dokumentasi Bash Update/Bash Update 2.png">
Kemudian tekan "CTRL+X" jika sudah men-setiing, kemudian tekan "Y" lalu "Enter".

3. Disini Saya melakukan Crosscheck apakah file sudah benar-benar terbuat dengan Command.
```bash
ls
```
<img src="Dokumentasi Bash Update/Bash Update 3.png">

4. Lalu saya melihat Permission yang dimiliki oleh bash tadi dengan Command.
```bash
ls -l
```
<img src="Dokumentasi Bash Update/Bash Update 4.png">

5. Selanjutnya saya akan menambahkan permission eksekusi pada bash tadi menggunakan Command.
```bash
chmod +x task-update-upgrade.sh
```
<img src="Dokumentasi Bash Update/Bash Update 5.png">

6. Jika sudah lakukan eksekusi dan tunggu hingga proses update dan upgrade selesai, menggunakan Command.
```bash
./task-update-upgrade
```
<img src="Dokumentasi Bash Update/Bash Update 6.png">
<img src="Dokumentasi Bash Update/Bash Update 7.png">

### Bash Firewall Port 22, 80, 443
Kurang Lebih Step by Step-nya sama, yang membedakan hanya isi text dari bash tersebut, jadi saya akan memasukkan dokumentasi dari prosesnya.
<img src="Dokumentasi Bash Firewall/Bash Fw 1.png">
<img src="Dokumentasi Bash Firewall/Bash Fw 2.png">
```bash
sudo ufw allow 22
sudo ufw allow 80
sudo ufw allow 443
```
<img src="Dokumentasi Bash Firewall/Bash Fw 3.png">
<img src="Dokumentasi Bash Firewall/Bash Fw 4.png">

Demikian rangkuman materi Hari ke-2, Minggu ke-2, di Stage-1. Akhir kata Terimakasih.