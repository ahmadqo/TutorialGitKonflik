# TutorialGitKonflik
Untuk dapat terjadinya konflik pada sebuah project di git dibutuhkan minimal 3 orang yaitu sebagai upstream dan dua orang sebagai kontributor.

### Melakukan config untuk remote ke github
    Hal ini hanya dilakukan sekali saja pada saat kita memiliki akun github.

    rbayu@RBAYU:~$ git config --global user.email "imnalaviaqom@gmail.com"
    rbayu@RBAYU:~$ git config --global user.name "qomluciver"
    
### Kontributor pertama dan kedua melakukan fork repo milik upstream    
<img align=center src=pict/qomze-fork.png alt="Repo yang shudah di fork qomzero">
<img align=center src=pict/qumluc-fork.png alt="Repo yang shudah di fork qomluciver">

### Kontributor pertama dan kedua melakukan clone
    rbayu@RBAYU:~$ git clone https://github.com/qomluciver/Kolaborasi.git
        Cloning into 'Kolaborasi'...
        remote: Counting objects: 127, done.
        remote: Compressing objects: 100% (8/8), done.
        remote: Total 127 (delta 5), reused 9 (delta 3), pack-reused 116
        Receiving objects: 100% (127/127), 4.11 MiB | 65.00 KiB/s, done.
        Resolving deltas: 100% (34/34), done.
        Checking connectivity... done.

### Memastikan remote ke upstream sudah berjalan
    rbayu@RBAYU:~/Kolaborasi$ git remote -v
        origin	https://github.com/qomluciver/Kolaborasi.git (fetch)
        origin	https://github.com/qomluciver/Kolaborasi.git (push)
    rbayu@RBAYU:~/Kolaborasi$ git remote add upstream https://github.com/ahmadqo/Kolaborasi.git
    rbayu@RBAYU:~/Kolaborasi$ git remote -v
        origin	https://github.com/qomluciver/Kolaborasi.git (fetch)
        origin	https://github.com/qomluciver/Kolaborasi.git (push)
        upstream	https://github.com/ahmadqo/Kolaborasi.git (fetch)
        upstream	https://github.com/ahmadqo/Kolaborasi.git (push)

### Kontributor pertama dan  kedua melakukan Sync repo
    rbayu@RBAYU:~/Kolaborasi$ git checkout master
        Already on 'master'
        Your branch is up-to-date with 'origin/master'.
    rbayu@RBAYU:~/Kolaborasi$ git status
        On branch master
        Your branch is up-to-date with 'origin/master'.
        nothing to commit, working directory clean
    rbayu@RBAYU:~/Kolaborasi$ git push origin master
        Username for 'https://github.com': qomluciver
        Password for 'https://qomluciver@github.com': 
        Everything up-to-date
    rbayu@RBAYU:~/Kolaborasi$ 

### Kontributor pertama membuat branch
    root@RBAYU:~/Kolaborasi# git checkout -b kontributorsatu
        Switched to a new branch 'kontributorsatu'
    root@RBAYU:~/Kolaborasi# git branch * kontributorsatu master

### KOntributor kedua membuat branch
    root@RBAYU:~/Kolaborasi# git checkout -b kontributordua
        Switched to a new branch 'kontributordua'
    root@RBAYU:~/Kolaborasi# git branch * kontributordua master

### Kontributor pertama push perubahan
    Setelah mengedit file yang diperlukan kemudian kontributor melakukan push ke branch yang telah dibuat.

    root@RBAYU:~/Kolaborasi# git add -A
    root@RBAYU:~/Kolaborasi# git commit -m "#10-Change Title"
        [kontribusipr 8929924] merubah file readme
         1 file changed, 1 insertion(+), 1 deletion(-)
    root@RBAYU:~/Kolaborasi# git push origin kontributorsatu
        Username for 'https://github.com': qomzero
        Password for 'https://qomzero@github.com': 
        Counting objects: 3, done.
        Delta compression using up to 4 threads.
        Compressing objects: 100% (3/3), done.
        Writing objects: 100% (3/3), 361 bytes | 0 bytes/s, done.
        Total 3 (delta 1), reused 0 (delta 0)
        remote: Resolving deltas: 100% (1/1), completed with 1 local object.
        To https://github.com/qomzero/Kolaborasi.git
         * [new branch]      kontributorsatu -> kontributorsatu

### Kontributor kedua push perubahan
    Setelah mengedit file yang diperlukan kemudian kontributor melakukan push ke branch yang telah dibuat.

    root@RBAYU:~/Kolaborasi# git add -A
    root@RBAYU:~/Kolaborasi# git commit -m "#10-Change Title"
        [kontribusipr 8929924] merubah file readme
         1 file changed, 1 insertion(+), 1 deletion(-)
    root@RBAYU:~/Kolaborasi# git push origin kontributordua
        Username for 'https://github.com': qomluciver
        Password for 'https://qomzero@github.com': 
        Counting objects: 3, done.
        Delta compression using up to 4 threads.
        Compressing objects: 100% (3/3), done.
        Writing objects: 100% (3/3), 361 bytes | 0 bytes/s, done.
        Total 3 (delta 1), reused 0 (delta 0)
        remote: Resolving deltas: 100% (1/1), completed with 1 local object.
        To https://github.com/qomluciver/Kolaborasi.git
         * [new branch]      kontributordua -> kontributordua

### Kontributor pertama mengirim Pull Request
<img align=center src=pict/kirim-pr1.png alt="qomzero mengirim PR">

### Kontributor pertama mengirim Pull Request
<img align=center src=pict/kirim-pr2.png alt="qomzero mengirim PR">

### Pull Request masuk ke upstream
<img align=center src=pict/pr-masuk1.png alt="PR masuk ke upstream">

<img align=center src=pict/pr-masuk.png alt="PR masuk ke upstream">

### Merge PR oleh upstream
<img align=center src=pict/merge-pr.png alt="qomzero mengirim PR">

### Terjadi KOnflik
<img align=center src=pict/tjd-konflik1.png alt="Terjadi KOnflik PR">

<img align=center src=pict/tjd-konflik.png alt="Terjadi KOnflik PR">

### Refolf konflik
<img align=center src=pict/resolf-konflik.png alt="Terjadi KOnflik PR">

### Semua kontributor melakukan sync repo kembali agar sama dengan repo upstream
    rbayu@RBAYU:~/Kolaborasi$ git checkout master
        Already on 'master'
        Your branch is up-to-date with 'origin/master'.
    rbayu@RBAYU:~/Kolaborasi$ git status
        On branch master
        Your branch is up-to-date with 'origin/master'.
        nothing to commit, working directory clean
    rbayu@RBAYU:~/Kolaborasi$ git push origin master
        Username for 'https://github.com': qomluciver
        Password for 'https://qomluciver@github.com': 
        Everything up-to-date
    rbayu@RBAYU:~/Kolaborasi$ 
