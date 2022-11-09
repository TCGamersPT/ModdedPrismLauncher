# Windows

### Requirements

- [MSYS2](https://www.msys2.org)
- [Open JDK 8 or later](https://adoptium.net)

### Preparing MSYS2

Open MSYS2 CLANG64 and run the following commands to install dependencies:

```sh
pacboy -S toolchain:p cmake:p ninja:p qt5-base:p qt5-svg:p qt5-imageformats:p quazip-qt5:p extra-cmake-modules:p ninja:p ccache:p
```

### Setting up the build 

Git clone the repo in CMD to your desired folder

```bash
git clone --recursive https://github.com/TCGamersPT/ModdedPrismLauncher.git
```

Open MSYS2 CLANG64 and run the following:

```bash
cd "C:\Users\youruser\thefolderwherethegitcloneis"
```

Setup CMAKE build instructions:

```bash
cmake -Bbuild -DCMAKE_INSTALL_PREFIX="C:\Users\youruser\createafoldertostorethelauncheranditsfiles" -DENABLE_LTO=ON -DCMAKE_OBJDUMP=/mingw64/bin/objdump.exe -DCMAKE_BUILD_TYPE=Release -G Ninja
```

Run the build

```bash
cmake --build build
```

Install the built launcher to the folder you setup in `-DCMAKE_INSTALL_PREFIX`

```bash
cmake --install build
```

Since this was built with Qt5, we need to copy over OpenSSL DLLs to allow our launcher to pull files from the internet, run the following command to do so

```
cp /clang64/bin/libcrypto-1_1.dll /clang64/bin/libssl-1_1.dll "pathtothelauncher'sfolder"
```


After all these steps the launcher is ready to use.

# Credits for this dumbed down guide

- [Prism Launcher building guide](https://prismlauncher.org/wiki/development/build-instructions/#windows) - this guide is based off theirs.
- [YTPCmc](https://github.com/YTPCmc)

# If you have issues building, you can look out for help in our [discord](https://discord.tcgamers.tk)
