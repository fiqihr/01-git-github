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
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (edit-readme-1)
$ git checkout main
Switched to branch 'main'
Your branch is based on 'origin/master', but the upstream is gone.
  (use "git branch --unset-upstream" to fixup)

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
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
Setelah itu kita tinggal melakukan **pull request** pada GitHub.<br/>
![push 2](https://user-images.githubusercontent.com/75562356/135615406-4c03e50c-752f-4ce2-a23a-12bb1093aa6b.png) <br/>
apabila tidak terjadi conflict merge, klik **Merge Pull Request**
![push 3](https://user-images.githubusercontent.com/75562356/135615870-753dfc6a-7cb5-42e5-ba44-d04e84b9b358.png) <br/>
Setelah selesai, klik `Confirm Merge` ,branch yang kita kirimkan tadi sudah dimasukkan ke branch `main`. Setelah itu, merge di komputer lokal:
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git merge edit-readme-1
starting fsmonitor-daemon in 'D:/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Pr
aktik IV/Github/repository-percobaan'
Updating 0c4d34c..981b3bc
Fast-forward
 README.md | 1 +
 1 file changed, 1 insertion(+)
 
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git branch
  edit-readme-1
* main

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git branch -D edit-readme-1
Deleted branch edit-readme-1 (was 981b3bc).

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git branch
* main
```
perintah `git merge` digunakan untuk menggabungkan branch yang aktif dan branch yang dipilih. dan perintah `git branch` berfungsi untuk melihat branch yang ada.
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git pull
remote: Enumerating objects: 8, done.
remote: Counting objects: 100% (8/8), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 4 (delta 0), reused 3 (delta 0), pack-reused 0
Unpacking objects: 100% (4/4), 877 bytes | 97.00 KiB/s, done.
From https://github.com/fiqihr/repository-percobaan
 * [new branch]      edit-readmee-1 -> origin/edit-readmee-1
   0c4d34c..bda3015  main           -> origin/main
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=origin/<branch> main


Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git branch --set-upstream-to=origin/main main
Branch 'main' set up to track remote branch 'main' from 'origin'.

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git pull
Updating 981b3bc..bda3015
Fast-forward
```

### Sinkronsasi ###
Suatu saat kita akan mengedit repo di komputer lain melalui repo lokal dikomputer lain. Untuk itu kita perlu melakukan sinkronsasi. Perintah sinkronsasi bisa dilakukan dengan menggunakan perintah `git pull`.
```bash
$ git pull
```
Perintah ini dikerjakan di direktori tempat repo lokal kita berada.

### Membatalkan Perubahan ###

Pada saat kita membuat repo hendaknya kita membuat branch saat akan melakukan perubahan agar bisa dikelola dengan mudah. Apabila perubahan-perubahan yang kita lakukan salah atau sudah kacau, kita bisa mengembalikannya menjadi bersih seperti sebelum melakukan perubahan-perubahan. Langkah yang harus dilakukan adalah dengan membuat branch terlebih dahulu  baru kemudian melakukan perubahan.<br/>
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
```bash
$ git checkout -b edit-readme-2
Switched to a new branch 'edit-readme-2'

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (edit-readme-2)
$ code README.md

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (edit-readme-2)
$ cat README.md
#repository-percobaan
Ini adalah isi proyek yang kacau
```
Lalu kita kembali ke branch `main`.
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (edit-readme-2)
$ git checkout main
Switched to branch 'main'
M       README.md
Your branch is up to date with 'origin/main'.

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ cat README.md
#repository-percobaan
Ini adalah isi proyek yang kacau
```
perintah `$ git reset --hard` berfungsi untuk membuang semua perubahan yang tidak dikomit. sehingga direktori akan benar benar bersih.
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git reset --hard
HEAD is now at bda3015 Merge pull request #1 from fiqihr/edit-readme-1

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ cat README.md
#repository-percobaan

ini isi proyek
```

### Undo Commit Terakhir ###
Suatu saat, mungkin kita sudah terlanjur mem-*push* perubahan ke repo GitHub, setelah itu kita baru menyadari bahwa perubahan tersebut salah. Untuk itu, kita bisa melakukan `git revert`.
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ cat README.md
ini isi proyek

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git log --oneline
bda3015 (HEAD -> main, origin/main, edit-readme-2) Merge pull request #1 from fiqihr/edit-readme-1
981b3bc (origin/edit-readme-1) Add: mengisi README.md
0c4d34c Add: README.md

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ code README.md

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git add -A

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git commit -m "Add: contents"
[main 5ee8f63] Add: contents
 1 file changed, 1 insertion(+), 1 deletion(-)

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Writing objects: 100% (3/3), 271 bytes | 271.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/fiqihr/repository-percobaan.git
   bda3015..5ee8f63  main -> main

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ code README.md

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git add -A

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git commit -m "Add: contents - 2"
[main 77058d2] Add: contents - 2
 1 file changed, 2 insertions(+), 1 deletion(-)

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 281 bytes | 281.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/fiqihr/repository-percobaan.git
   5ee8f63..77058d2  main -> main

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ cat README.md
ini isi proyek yang diubah 1
Ini isi proyek yang diubah 2

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```
Contoh di atas adalah contoh untuk mengubah README.md dengan beberapa commit. Setelah itu, kita akan mengembalikan ke posisi terakhir sebelum commit terakhir menggunakan perintah `git revert HEAD`. Kemudian akan otomatis membuka teks editor dan kita bisa mengetikkan pesan *revert*(pembatalan commit).
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git revert HEAD
hint: Waiting for your editor to close the file...
[main df915b7] Revert "Add: contents - 2"
 1 file changed, 1 insertion(+), 2 deletions(-)
```
Selanjutnya kita tinggal push ke reppo GitHub.
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git push origin main
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (1/1), done.
Writing objects: 100% (3/3), 303 bytes | 303.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/fiqihr/repository-percobaan.git
   77058d2..df915b7  main -> main

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ cat README.md
#repository-percobaan

ini isi proyek yang diubah
```

Jika commit sudah dilakukan, tetapi masih berada di lokal dan belum di-push ke repo GitHub , cara membatalkannya yaitu:
Pertama dengan melakukan perubahan terlebih dahulu.
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ cat README.md
#repository-percobaan

ini isi proyek yang diubah

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ code README.md

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git add -A

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git commit -m "Add: isi tambahan 1"
[main 5d4ab52] Add: isi tambahan 1
 1 file changed, 3 insertions(+), 1 deletion(-)

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git log --oneline
5d4ab52 (HEAD -> main) Add: isi tambahan 1
df915b7 (origin/main) Revert "Add: contents - 2"
77058d2 Add: contents - 2
5ee8f63 Add: contents
bda3015 (edit-readme-2) Merge pull request #1 from fiqihr/edit-readme-1
981b3bc (origin/edit-readme-1) Add: mengisi README.md
0c4d34c Add: README.md

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git reset --hard HEAD^
HEAD is now at df915b7 Revert "Add: contents - 2"

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ cat README.md
#repository-percobaan

ini isi proyek yang diubah

```
Untuk kembali ke pada saat perubahan yang sudah lama, yang perlu dilakukan adalah melakukan `git revert <posisi>` kemudian edit secara manual dan kemudian di push ke repo.
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ cat README.md
ini isi proyek yang diubah
#repository-percobaan

Perubahan 1
Perubahan 2

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git log --oneline
df915b7 (HEAD -> main, origin/main) Revert "Add: contents - 2"
77058d2 Add: contents - 2
5ee8f63 Add: contents
bda3015 (edit-readme-2) Merge pull request #1 from fiqihr/edit-readme-1
981b3bc (origin/edit-readme-1) Add: mengisi README.md
0c4d34c Add: README.md

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git revert 77058d2
error: could not revert 77058d2... Add: contents - 2
hint: after resolving the conflicts, mark the corrected paths
hint: with 'git add <paths>' or 'git rm <paths>'
hint: and commit the result with 'git commit'
```
Setelah itu, jika dilihat pada file, akan muncul tambahan untuk memudahkan meng-edit. File ini harus di-resolve terlebih dahulu, setelah itu baru di add dan commit:
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main|REVERTING)
$ cat README.md
ini isi proyek yang diubah

Perubahan 1
<<<<<<< HEAD
Perubahan 2

=======
>>>>>>> parent of 77058d2... Add: contents - 2
```
Kemudian file tersebut diedit lalu disimpan.
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main|REVERTING)
$ cat README.md
ini isi proyek yang diubah

Perubahan 1
Perubahan 2 setelah revert

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main|REVERTING)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

You are currently reverting commit 77058d2.
  (fix conflicts and run "git revert --continue")
  (use "git revert --abort" to cancel the revert operation)

Unmerged paths:
  (use "git reset HEAD <file>..." to unstage)
  (use "git add <file>..." to mark resolution)

	both modified:   README.md

no changes added to commit (use "git add" and/or "git commit -a")
```
Setelah itu, melanjutkan proses revert. Saat `git revert --continue` isikan pesan revert.
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main|REVERTING)
$ git add README.md

Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main|REVERTING)
$ git status
On branch main
Your branch is up to date with 'origin/main'.

You are currently reverting commit 77058d2.
  (all conflicts fixed: run "git revert --continue")
  (use "git revert --skip" to skip this patch)
  (use "git revert --abort" to cancel the revert operation)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md
        
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main|REVERTING)
$ git revert --continue
hint: Waiting for your editor to close the file...
[main 2021-10-01T08:38:35.293Z] update#setState idle
[main 50245382] Revert "Add: mengisi 2"
 1 file changed, 1 insertions(+), 2 deletions(-)
```
Setelah itu, kita push.
```bash
Lenovo@LAPTOP-U32K1K3E MINGW64 /d/Kuliah/Semester 3/Metodologi Desain Perangkat Lunak Praktik IV/Github/repository-percobaan (main)
$ git push origin main
Enumerating objects: 8, done.
Counting objects: 100% (8/8), done.
Delta compression using up to 4 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (6/6), 647 bytes | 647.00 KiB/s, done.
Total 6 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/fiqihr/repository-percobaan.git
   cd60244..e929243  main -> main
```
