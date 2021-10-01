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

## Mengelola Repo ##

### Mengubah Isi - Push Tanpa Branching dan Merging ###

Setelah clone repo ke komputer lokal, semua aktivitas dilakukan di komputer lokal kita dan hasilnya nanti akan di-push ke remote repository di GitHub. Perubahan perubahan yang bisa dilakukan antara lain:
1. Menghapus File
2. Mengedit File
3. Membuat file / direktori baru
4. Menghapus direktori

Untuk melakukannya bisa menuliskan perintah berikut.<br/>
Karena disini saya menggunakan teks editor vscode, maka bisa dituliskan `$ code 'nama file yang akan dibuat' `. Jika menggunakan vim maka bisa menggunakan perintah `$ vim 'nama file yang akan dibuat' `
```
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ code README.md
```
Kemudian perintah `$ cat README.md` digunakan untuk melihat isi dari file tersebut tanpa harus membuka teks editor. File yang akan dilihat disini yaitu `README.md`.<br/>
Lalu ada perintah `$ git status` yaitu digunakan untuk melihat status dari repo kita, sudah dilakukan perubahan atau belum.<br/>
```
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git status
starting fsmonitor-daemon in 'D:/Kuliah/Semester 3/Metodologi Desain Perangkat L
unak Praktik IV/Github/repository-percobaan'
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md

nothing added to commit but untracked files present (use "git add" to track)

```
`On branch main` menandakan bahwa kita sedang berada di dalam branch main. <br/>
`No commits yet` menandakan bahwa kita belum melakukan commit apapun.<br/>
`Untracked files` menunjukan bahwa ada file yang belum di track. file itu bernama `README.md`. <br/>
lalu akan muncul perintah `git add` yang digunakan untuk melakukan perubahan atau penambahan isi file. Agar file `README.md` bisa di commit, kita harus menyimpan dulu di *Staging Area* untuk kemudian baru bisa di commit. <br/> 
```
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git add -A

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git commit -m "Add: README.md"
[main (root-commit) 0c4d34c] Add: README.md
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git push origin main
info: please complete authentication in your browser...
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 219 bytes | 219.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/fiqihr/repository-percobaan.git
 * [new branch]      main -> main
```
perintah `$ git commit` artinya kita telah melakukan perubahan yang kemudian akan direkam untuk repo kita. `-m "<commit message>` digunakan untuk memberikan pesan dari commit yang sudah kita lakukan. pesan diatas yaitu `"Add: README.md"`.<br/>
`$ git push origin main` adalah perintah yang mengatakan "tekan komit di cabang lokal bernama main ke remote bernama origin". Setelah ini dijalankan, semua hal yang terakhir di sinkronkan dengan asal akan dikirim ke repositori jarak jauh.

### Mengubah Isi Dengan Branching dan Merging ###

Dengan menggunakan cara ini, setiap kali akan melakukan perubahan, perubahan itu dilakukan di komputer lokal dengan membuat suatu *cabang* yang nantinya digunakan untuk menampung perubahan-perubahan tersebut. Setelah itu, cabang itu yang akan dikirim ke repo GitHub untuk dimintai review kemudian digabungkan (`merge`) ke main. Secara umum, repo yang dibuat biasanya sudah mempunyai satu branch yang disebut dengan `main`. Cara ini lebih aman, terstruktur, terkendali, dan mempunyai history yang lebih baik. Jika perubahan yang kita buat sudah terlalu kacau dan kita menyesal, maka ada cara untuk "membersihkan" repo lokal kita. Secara umum, langkahnya adalah sebagai berikut:

1. Buat branch untuk menampung perubahan-perubahan
2. Lakukan perubahan-perubahan
3. Add dan commit perubahan-perubahan tersebut ke branch
4. Kembali ke repo main
5. Buat pull request di GitHub
6. Merge pull request di GitHub
7. Merge branch untuk menampung perubahan-perubahan tersebut ke main.
8. Selesai.

```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git checkout -b edit-readme-1
Switched to a new branch 'edit-readme-1'

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (edit-readme-1)
$ code README.md

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (edit-readme-1)
$ cat README.md

# Repository Percobaan
```
perintah `$ git checkout -b edit-readme-1` digunakan untuk membuat branch baru yang bernama `edit-readme-1`.<br/>

```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (edit-readme-1)
$ git status
On branch edit-readme-1
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (edit-readme-1)
$ git add -A

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (edit-readme-1)
$ git commit -m "Add: mengisi README.md"
[edit-readme-1 981b3bc] Add: mengisi README.md
 1 file changed, 1 insertion(+)
 ```
Informasi diatas menjelaskan bahwa kita telah memodifikasi file `README.md` di dalam branch baru yang bernama `edit-readme-1` dan telah melakukan commit.
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (edit-readme-1)
$ git checkout main
Switched to branch 'main'
Your branch is based on 'origin/master', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
```bash
$ git status
On branch main
Your branch is based on 'origin/master', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

nothing to commit, working tree clean

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git branch --unset-upstream

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git status
On branch main
nothing to commit, working tree clean
```
`$ git branch --unset-upstream` digunakan untuk menghilangkan informasi upstream untuk nama branch apabila tidak ada branch yang ditentukan,dan defaultnya adalah branch saat ini.
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git push origin edit-readme-1
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (3/3), 268 bytes | 268.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'edit-readme-1' on GitHub by visiting:
remote:      https://github.com/fiqihr/repository-percobaan/pull/new/edit-readme-1
remote:
To https://github.com/fiqihr/repository-percobaan.git
 * [new branch]      edit-readme-1 -> edit-readme-1
```
