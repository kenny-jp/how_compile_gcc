# How to build gcc

#### install dependancies:
```sh
sudo apt install bison \
                 build-essential \
                 flex \
                 libgmp-dev \   
                 libmpc-dev \       
                 libmpfr-dev \
                 texinfo     
```

#### Download GCC sources
[link](https://www.gnu.org/prep/ftp.html#gnu_mirror_list)

#### build and install:
  ```sh 
  tar -xvf gcc-x.y.z.tar.gz
  cd gcc-x.y.z
  ./configure --prefix=/usr/local \
              --enable-languages=c,c++ \
              --disable-multilib \
              --program-suffix=-[gcc_version] \
              --enable-shared \
              --enable-threads=posix \
              --enable-checking=release \
              --enable-bootstrap \
              --enable-lto
  make -j$(nproc)
  make check (optional)
  sudo make install
  ```
