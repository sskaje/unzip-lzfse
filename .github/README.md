# Unzip with lzfse 

This project is modified based on unzip-6.0

Read more: https://sskaje.me/2017/08/unzip-with-lzfse-support/

## Build

### Build lzfse 

```
$ git clone https://github.com/lzfse/lzfse.git
$ cd lzfse
$ make
$ sudo make install
```


### Build unzip-lzfse

```
$ git clone https://github.com/sskaje/unzip-lzfse
$ git checkout lzfse
$ cd unzip-lzfse
$ export LZFSE_PATH=/usr/local
$ make -f unix/Makefile all
```

## Usage

try 
```
unzip -h
```

e.g.
```
$ ./unzip -d test ../pre-thinned12345678.thinned.signed.dpkg.ipa
```
