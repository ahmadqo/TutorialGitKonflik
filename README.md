# TutorialGitKonflik
Untuk dapat terjadinya konflik pada sebuah project di git dibutuhkan minimal 3 orang yaitu sebagai upstream dan dua orang sebagai kontributor.

### Melakukan config untuk remote ke github
####Hal ini hanya dilakukan sekali saja pada saat kita memiliki akun github.

    rbayu@RBAYU:~$ git config --global user.email "imnalaviaqom@gmail.com"
    rbayu@RBAYU:~$ git config --global user.name "qomluciver"
    
### Kontributor pertama dan kedua melakukan fork repo milik upstream
<img align=center src=pict/qomze-fork.png alt="Repo upstream yang akan di fork">
<img align=center src=pict/qumluc-fork.png alt="Kontributor Pertama">

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

### Kontributro pertama dan  kedua melakukan Sync repo
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

    root@RBAYU:~/Kolaborasi# nano README.md 
    root@RBAYU:~/Kolaborasi# git add -A
    root@RBAYU:~/Kolaborasi# git commit -m "#10-Cange Title"
    root@RBAYU:~/Kolaborasi# git push origin kontribusipr

### Kontributor pertama mengirim Pull Request
    'kontributordua
