# Konfigurasi Git pada Windows OS

[Kembali](README.md)

Saat akan mengkonfigurasi Git, yang perlu dilakukan user adalah memasukkan email dan username yang sesuai.<br/>
Pertama yang bisa dilakukan adalah dengan cara mengatur di command prompt git. Tulis di kolom pencarian *Git Bash* kemudian klik dua kali. Dan tuliskan perintah berikut.
```
$ git config --global user.name "Nama user di GitHub"
$ git config --global user.email email@domain.tld
```
Isikan `user.name` dengan nama kita di GitHub. Dan isikan `user.email` dengan email kita yang sudah digunakan di akun GitHub. Kemudian klik enter untuk mengkonfirmasi perubahan.<br/>
Untuk mengeceknya, bisa digunakan dengan perintah berikut.
```
$ git config --list
user.name=Fiqih Ref
user.email=fiqihref15@gmail.com

```
Maka akan muncul username dan email kita yang sudah dikonfigurasikan.

Kemudian kita bisa membuka file `.gitconfig` pada Drive **C:\Users\nama-user** untuk *(Windows OS)*. Maka akan tampil seperti dibawah ini, karena kita sudah menglonfigurasikan.
```
[user]
	name = Fiqih Ref
	email = fiqihref15@gmail.com
  ```
