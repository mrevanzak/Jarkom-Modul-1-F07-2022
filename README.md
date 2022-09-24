# JARKOM Modul 1

## Daftar isi

- [Anggota Kelompok](#anggota-kelompok)
- [Nomer 1](#nomer-1)
- [Nomer 2](#nomer-2)
- [Nomer 3](#nomer-3)
- [Nomer 4](#nomer-4)
- [Nomer 5](#nomer-5)
- [Nomer 6](#nomer-6)
- [Nomer 7](#nomer-7)
- [Nomer 8](#nomer-8)
- [Nomer 9](#nomer-9)
- [Nomer 10](#nomer-10)
- [Kendala](#kendala)

## Anggota Kelompok

| NRP        | NAMA                       |
| ---------- | -------------------------- |
| 5025201145 | Mochamad Revanza Kurniawan |
| 5025201208 | Bagus Febrian Dali Hidayat |
| 5025201241 | Jabalnur                   |

## Nomer 1
Sebutkan web server yang digunakan pada "monta.if.its.ac.id"! 
> nginx/1.10.3
```
http.server
```
<img width="468" alt="image" src="https://user-images.githubusercontent.com/73029778/191952888-6bf88901-4d7c-4333-b747-2fd74a8069c6.png">

## Nomer 2
Ishaq sedang bingung mencari topik ta untuk semester ini , lalu ia datang ke website monta dan menemukan detail topik pada website “monta.if.its.ac.id” , judul TA apa yang dibuka oleh ishaq ?
> Evaluasi untuk kerja User File System  (FUSE)
```
http.request.uri contains "detailTopik"
```
Setelah difilter, klik File -> Export Objects -> HTTP, lalu save all. jalankan file htmlnya di local nanti keliatan judul TAnya di page 194 <br>
<img width="468" alt="image" src="https://user-images.githubusercontent.com/73029778/191953053-9c3f2639-1a1b-450c-8255-106e80ed287a.png">

## Nomer 3
Filter sehingga wireshark hanya menampilkan paket yang menuju port 80! 
```
tcp.dstport == 80
```
<img width="468" alt="image" src="https://user-images.githubusercontent.com/73029778/191953191-3a02710c-3616-4d04-ba09-ad2dd24bf47d.png">

## Nomer 8
Untukk dapat mencari informasi terkait percakapan antara dua mahasiswa tentang tindakan kecurangan pada kegiatan praktikum.
Untuk mendapatkan informasi kita dapat menerapkan filter terhadap tcp yang mengandung kata "jawaban".
```
tcp contains jawaban
```
<img width="468" alt="image" src="https://user-images.githubusercontent.com/60770478/192085094-07d56e0b-36a0-4cbe-b7ab-d434a917aa40.png">

Setelah itu, kita akan menelusuri seluruh percakapan yang ditemukan dengan cara klik kanan lalu follow, dan ditemukan di salah satu percakapan terdapat pembahasan yang membicarakan terkait tindakan kecurangan pada kegiatan praktikum.

<img width="468" alt="image" src="https://user-images.githubusercontent.com/60770478/192085211-2bc4e308-4574-4f89-80f2-659e58908e1a.png">

Pada percakapan tersebut, ditemukan informasi yaitu
- Decrypte yang dipakai untuk mendapatkan file jawaban = openssl
- Metode yang digunakan dalam decrypte = des3
- File yang ingin didecrypte = salt
- Password file yang sudah didecrypte (Nama karakter anime kembar lima) = nakano
- Port yang digunakan untuk mengirim file = 9002

## Nomer 9
File dikirim melalui port 9002, sehingga akan dicari paket yang berasal dari port 9002
```
tcp.srcport == 9002
```
Setelah itu paket yang ditemukan akan diklik kanan lalu follow untuk melihat isi paketnya.

<img width="468" alt="image" src="https://user-images.githubusercontent.com/60770478/192085523-a5e96447-5570-496d-a1f7-e47e3fe1b873.png">

File yang ditemukan dalam paket tersebut kemudian akan diekstrak dalam bentuk raw dan diberi nama file F07.des3

File hasil ekstrak akan didecrypte menjadi flag.txt menggunakan informasi yang ditemukan pada soal nomor 8.

<img width="468" alt="image" src="https://user-images.githubusercontent.com/60770478/192085756-79aea11e-a53e-4339-89eb-efea3999247c.png">

## Nomer 10
Password rahasia dari organisasi bawah tanah yang ditemukan dalam file flag.txt adalah JaRkOm2022{8uK4N_CtF_k0k_h3h3h3}

<img width="468" alt="image" src="https://user-images.githubusercontent.com/60770478/192085899-199cb423-b9ef-40a3-8a45-f348d2fc80ed.png">

## Kendala
Kebingungan dengan password untuk decrypt :D
