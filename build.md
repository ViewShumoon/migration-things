## 目录结构
lichee
    linux-6.8.9
host-tools
    gcc
        riscv64-elf-x86_64
        riscv64-linux-musl-x86_64
        riscv64-linux-x86_64


## 需要的文件
- 新 linux 内核 
- gcc
    确保 host-tools 和 lichee 文件夹同级
    lichee
        
        linux-6.8.9
        ...

    host-tools
        gcc
            riscv64-elf-x86_64
            riscv64-linux-musl-x86_64
            riscv64-linux-x86_64
    然后执行
    ```
        cd lichee
        ln -s ../host-tools ./
    ```

## 复制的文件

    - linux_5.10/drivers/staging/android 复制 android 文件夹
复制到 linux-6.8.9/drivers/staging/ 下


    linux_5.10/include/dt-bindings/reset/cv18 开通的文件
    linux-6.8.9/include/dt-bindings/reset/下


## 命令

git config --global user.name "ViewShumoon" &&
git config --global user.email "ViewShumoon@outlook.com"

ssh-keygen -t rsa  -C "ViewShumoon@outlook.com" -f build

### 编译命令
```
script build-things/log1.log

source build/cvisetup.sh
defconfig sg2002_licheervnano_sd
clean_all && build_all

script  -q
```

### 依赖的包

dtc
bc
rsync

apt update && \
apt install -y pkg-config build-essential ninja-build\
    automake autoconf libtool wget curl git unzip gcc libssl-dev bc\
    squashfs-tools android-sdk-libsparse-utils rsync\
    jq make cmake tclsh scons parallel tree\
    python3-dev python3-pip device-tree-compiler libssl-dev cpio\
    squashfs-tools fakeroot libncurses5-dev flex bison\
    android-libext4-utils bdebstrap proot fakeroot fakechroot\
    bzr ca-certificates cvs file locales mercurial python3\
    python3-flake8 python3-nose2 python3-pexpect subversion\
    ccache gawk diffstat texinfo chrpath socat\
    python3-pip python3-pexpect xz-utils debianutils\
    iputils-ping python3-git python3-jinja2 python3-subunit\
    zstd liblz4-tool libacl1 parted erofs-utils genext2fs mtools\
    fatcat ckermit neovim cscope asciinema libconfuse-dev dosfstools\
    gettext autoconf-archive clang

