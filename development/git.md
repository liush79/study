## git color
    git config --global color.ui auto

## git global user setting
    git config --global user.email "seungho.ryu@gmail.com"
    git config --global user.name "Seungho Ryu"

## my alias 
    git config --global alias.st status
    git config --global alias.ci commit
    git config --global alias.df diff
    git config --global alias.co checkout
    git config --global alias.br branch

## git ignore
    git config --global core.excludesfile ~/.gitignore_global

## git ignore sample file
    # Byte-compiled  optimized  DLL files
    __pycache__
    *.py[cod]

    # C extensions
    *.so

    # Distribution  packaging
    bin
    build
    develop-eggs
    dist
    eggs
    lib
    lib64
    parts
    sdist
    var
    .egg-info
    .installed.cfg
    .egg

    # IDE
    .classpath
    .project
    .settings
    .idea
    .metadata

## If your git not support HTTPS
    sudo apt-get install libcurl4-openssl-dev
    
    # chenge version to new version
    wget https://www.kernel.org/pub/software/scm/git/git-2.12.0.tar.gz
    tar xvf git-2.12.0.tar.gz
    cd git-2.12.0
     ./configure
    make -j8
    sudo make install

    /usr/local/bin/git clone https://git.domain/
