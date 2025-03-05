# OpenSSL 3.4.1 static library - built with Visual Studio 2022 CE, MinGW-w64 (cross)

## Visual Studio (with VS cmd, unpack the archive with Windows 10 tar)

### 32bit

```bat
perl Configure VC-WIN32 no-apps no-async no-capieng no-deprecated no-docs no-dso no-module no-pinshared no-shared no-tests --prefix=C:\Work\Clamav\openssl\win32\build
```

```bat
:: Optional for multicore build
set CL=/MP

nmake install_dev
```

### 64bit

```bat
perl Configure VC-WIN64A no-apps no-async no-capieng no-deprecated no-docs no-dso no-module no-pinshared no-shared no-tests --prefix=C:\Work\Clamav\openssl\x64\build
```

```bat
:: Optional for multicore build
set CL=/MP

nmake install_dev
```

## MinGW (Currently cross-compiled on Linux)

### x86

```sh
./Configure mingw no-apps no-async no-capieng no-deprecated no-docs no-dso no-module no-pinshared no-shared no-tests --cross-compile-prefix=i686-w64-mingw32- --prefix=`pwd`/../dist
make -jX
make install_dev
```

### x86\_x64 (-D\_WIN32\_WINNT=0x0501)

```sh
./Configure mingw64 no-apps no-async no-capieng no-deprecated no-docs no-dso no-module no-pinshared no-shared no-tests --cross-compile-prefix=x86_64-w64-mingw32- --prefix=`pwd`/../dist64
make -jX
make install_dev
```

### Notes

Add -D\_WIN32\_WINNT=0x0501 to Configure command line if you need Windows XP compatibility.
