# OpenSSL 1.1.1b - with Visual Studio 2005 (and maybe newer)

## Visual Studio (with VS cmd, unpack the archive with cygwin tar)

### 32bit
```bat
perl Configure VC-WIN32 -D_WIN32_WINNT=0x0501 no-dynamic-engine no-capieng no-shared no-async no-dso --prefix=C:\Work\Clamav\openssl\win32\build
```

You may need to disable `/WX` in `Configurations/10-main.conf` before running Configure,
just remove the line:

```perl
CFLAGS           => add("/WX"),
```

```bat
:: Optional for multicore build
set CL=/MP

nmake
nmake install_dev
```


### 64bit
```bat
perl Configure VC-WIN64A no-dynamic-engine no-capieng no-shared no-async no-dso --prefix=C:\Work\Clamav\openssl\x64\build
```

```bat
:: Optional for multicore build
set CL=/MP

nmake
nmake install_dev
```


## MinGW (Currently cross-compiled on Linux)
```sh
./Configure mingw no-shared no-dynamic-engine no-capieng no-async no-dso --cross-compile-prefix=i686-w64-mingw32- --prefix=`pwd`/../dist
make -jX
make install_dev
```
