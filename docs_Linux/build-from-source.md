# How to build command from source

> [!NOTE]
> This article provides an example of installing Python.

## Install Development Tools
### Red Hat
```
dnf groupinstall "Development Tools"
```
### Debian
```
apt install -y build-essential
```

## Install Build Tools
### Red Hat
```
dnf install -y openssl-devel bzip2-devel libffi-devel xz-devel sqlite-devel readline-devel ncurses-devel tk-devel zlib-devel libuuid-devel
```
### Debian
```
apt install -y libssl-dev zlib1g-dev libbz2-dev libreadline-dev libsqlite3-dev llvm libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev uuid-dev
```

## Get Source and Extract Files
```
curl -O https://[XXXXXXXXXXXX].tgz
tar -xf Python-3.XX.X.tgz
```

## Configure for Build
```
./configure --prefix=$HOME/<Installation Path>
```

## Build
```
make -j $(nproc)
```
> [!TIP]
> `-j` option sets the number of cores to use for the build.
> `nproc` can get the number of cpu cores.

## Install
```
make install
```

## Add to the PATH
```

```

