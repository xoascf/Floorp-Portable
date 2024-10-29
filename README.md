# Floorp Portable

**Note: It will only work with the upcoming release of Floorp 11.**

**Warning: This is currently a beta version. Unexpected problems may occur.**


## Requirements ([Pre-built binaries](https://github.com/Floorp-Projects/Floorp-Portable/releases))
* Windows
  * OS: 10, 11 (x86_64)
  * Memory: 8GB+
  * Disk Space: At least 2GB of free disk space.
* Linux
  * CPU Architecture: x86_64, aarch64
  * Memory: 8GB+
  * Disk Space: At least 2GB of free disk space.
  * Packages: bubblewrap, glibc, gtk+, libstdc++, xorg


## How to build
### 1. Get Floorp-Portable source code
```
git clone https://github.com/Floorp-Projects/Floorp-Portable
cd Floorp-Portable
```
### 2. Install Floorp
Create a directory named "core" and place Floorp files in it.

Windows
```
curl.exe -L "https://github.com/Floorp-Projects/Floorp/releases/latest/download/floorp-win64.installer.exe" -o floorp-win64.installer.exe
curl.exe -L "https://www.7-zip.org/a/7zr.exe" -o 7zr.exe
.\7zr.exe x floorp-win64.installer.exe -ir!core
```
Linux
```
export FLOORP_VERSION="{version}" # Replace "{version}" with latest floorp version, for example: `export FLOORP_VERSION="11.19.1"`
curl -L "https://github.com/Floorp-Projects/Floorp/releases/download/v${FLOORP_VERSION}/floorp-${FLOORP_VERSION}.linux-$(uname -m).tar.bz2" -o floorp-files.tar.bz2
mkdir core
tar -xvf floorp-files.tar.bz2 -C core --strip-components 1
```

### 3. Build
Windows
```
.\build.bat
```
Linux
```
./build.sh
```

### 4. Apply the patch
Run the built `patcher (patcher.exe)` to apply the patch.

Windows
```
.\patcher.exe
```
Linux
```
./patcher
```

### 5. Now it is done
The files and directories required to run the portable version are `core` and `floorp (floorp.exe)`.


## Container Runtime
Windows: [libportable](https://github.com/adonais/libportable)
Linux: [Bubblewrap](https://github.com/containers/bubblewrap)
