# OpenSSL 1.0.2o

## Visual Studio (with cmd, unpack the archive with cygwin tar)

### 32bit
```bat
perl Configure VC-WIN32 --prefix=C:\Work\Clamav\openssl\win32\build
ms\do_nasm.bat
```

edit ms\nt.mak and replace /MT with /MD

```bat
nmake -f ms\nt.mak
nmake -f ms\nt.mak install
```


### 64bit
```bat
perl Configure VC-WIN64A --prefix=C:\Work\Clamav\openssl\x64\build
ms\do_win64a.bat
```

edit ms\nt.mak and replace /MT with /MD

```bat
nmake -f ms\nt.mak
nmake -f ms\nt.mak install
```


## MinGW (with MSYS shell, unpack the archive with MinGW tar)
```sh
perl Configure mingw no-shared --prefix=/c/Work/Clamav/openssl/mingw/build
make depend
make
make install_sw
```
