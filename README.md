# OpenSSL 3.5.8 static library - built with Visual Studio 2026 CE, MinGW-w64 (cross)

## Visual Studio (with VS cmd, unpack the archive with Windows 10 tar)

### 32bit

```bat
perl Configure VC-WIN32 no-apps no-async no-capieng no-docs no-dso no-module no-pinshared no-shared no-tests
```

```bat
:: Optional for multicore build
set CL=/MP

nmake DESTDIR=..\build install_dev
```

### 64bit

```bat
perl Configure VC-WIN64A no-apps no-async no-capieng no-docs no-dso no-module no-pinshared no-shared no-tests
```

```bat
:: Optional for multicore build
set CL=/MP

nmake DESTDIR=..\build install_dev
```

## MinGW (Currently cross-compiled on Linux)

### x86

```sh
./Configure mingw no-apps no-async no-capieng no-docs no-dso no-module no-pinshared no-shared no-tests --cross-compile-prefix=i686-w64-mingw32- --prefix=.
make -jX
make DESTDIR=../dist/ install_dev
```

### x86 legacy build (-D\_WIN32\_WINNT=0x0501)

```sh
./Configure mingw no-apps no-async no-capieng no-docs no-dso no-module no-pinshared no-shared no-tests no-sse2 --cross-compile-prefix=i686-w64-mingw32- -D_WIN32_WINNT=0x0501 --prefix=.
make -jX
make DESTDIR=../dist-legacy/ install_dev
```

### x86\_x64 (-D\_WIN32\_WINNT=0x0501)

```sh
./Configure mingw64 no-apps no-async no-capieng no-docs no-dso no-module no-pinshared no-shared no-tests --cross-compile-prefix=x86_64-w64-mingw32- -D_WIN32_WINNT=0x0501 --prefix=.
make -jX
make DESTDIR=../dist64/ install_dev
```

### Notes

Add -D\_WIN32\_WINNT=0x0501 to Configure command line if you need Windows XP compatibility.
