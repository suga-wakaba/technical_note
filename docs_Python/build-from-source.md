# Build from Source

```
dnf group install "Development Tools"
dnf install -y openssl-devel bzip2-devel libffi-devel xz-devel sqlite-devel readline-devel ncurses-devel tk-devel zlib-devel libuuid-devel
curl -O https://www.python.org/ftp/python/3.x.x/Python-3.x.x.tgz
tar -xf Python-3.x.x.tgz
./configure --enable-optimizations --with-lto --prefix=<install path>
make -j $(nproc)
make install
```
