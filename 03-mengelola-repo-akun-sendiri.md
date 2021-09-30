# Mengelola Repository di akun sendiri

[Kembali](Readme.md)

### Langkah-langkah membuat Repository(repo) di GitHub.<br/>
1. Mengklik tanda + pada bagian atas kanan disamping menu profil. Kemudian pilih **New Repository**
![repo 1](https://user-images.githubusercontent.com/75562356/135461506-4997b908-f0aa-4613-8c22-aea86bfbaa99.png)
2. Kemudian user akan diarahkan pada tampilan seperti dibawah ini.
![repo 2](https://user-images.githubusercontent.com/75562356/135462042-18e58eaf-6ee2-4c6a-ba66-5c077fdb87fb.png)
3. Beri nama repository pada kolom **Repository name**. Kemudian berikan deskripsi repository bila perlu. Atur juga jangkauan repo,**Public** atau **Privat**. Lalu kita juga bisa menambahkan sebuah file **README.md** yang dibuat langsung oleh sistem ke repo kita. kemudian bisa juga dengan mengisi radio button **Add .gitignore** atau juga kita bisa menambahkan lisensi di repo kita tersebut.
4. Klik ```Create Repository``` untuk menyelesaikan pembuatan Repository.

### Clone Repository ###
Clone adalah suatu proses menyalin repository dari GitHub ke komputer untuk bisa diedit secara offline di perangkat kita.<br/>
Cara clone repository yaitu dengan menggunakan perintah ```$ git clone https://github.com/username/nama-repo```
1. Pilih folder yang akan kita gunakan untuk menaruh clone repo dari GitHub
2. Kemudian klik kanan dan pilih ```Git Bash Here```
3. Akan muncul cmd Git.
```
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github
$ git clone https://github.com/fiqihr/repository-percobaan.git
Cloning into 'repository-percobaan'...
warning: You appear to have cloned an empty repository.
```
Jika repo yang di clone merupakan repo kosong, maka muncul peringatan *warning: You appear to have cloned an empty repository.*

Di semua repository selalu memiliki branch(cabang). Branch tersebut otomatis dibuat oleh sistem dan memiliki nama default *master*. tetapi untuk sekarang ini telah terjadi perubahan istilah menjadi *main*. Untuk itu kita perlu mengganti branch tersebut dari *master* ke *main*. Perintah untuk melakukan perubahan:
```
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/
$ cd repository-percobaan
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (master)
$ git branch -m main
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$
```
perintah `cd`(change directory) digunakan untuk memindah lokasi. Perintah `$ git branch -m main` untuk memindahkan branch ke dalam `main`.<br/>
Jika sudah terdapat tulisan ```(main)``` maka branch sudah berpindah ke *main*
