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
