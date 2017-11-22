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
#unzip with lzfs
$ ./unzip -d dst pre-thinned2490830240475770608.thinned.signed.dpkg.ipa 
Archive:  pre-thinned2490830240475770608.thinned.signed.dpkg.ipa
   creating: dst/META-INF/
  unlzfsing: dst/META-INF/com.apple.ZipMetadata.plist  
 extracting: dst/META-INF/com.apple.FixedZipMetadata.bin  
   creating: dst/Payload/

#unzip
$ unzip -d dst pre-thinned2490830240475770608.thinned.signed.dpkg.ipa 
Archive:  pre-thinned2490830240475770608.thinned.signed.dpkg.ipa
   skipping: META-INF/com.apple.ZipMetadata.plist  unsupported compression method 99
   ...
   creating: dst/META-INF/
 extracting: dst/META-INF/com.apple.FixedZipMetadata.bin  
   creating: dst/Payload/

```

