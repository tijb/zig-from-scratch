# zig-from-scratch
Getting Zig up and running from source on a Google Pixelbook (Crostini Debian Bullseye) 

## step list

> Add the LLVM apt key
```
wget -O - https://apt.llvm.org/llvm-snapshot.gpg.key|sudo apt-key add -
```

> Add **LLVM 13** ppa 
```
echo 'deb http://apt.llvm.org/bullseye/ llvm-toolchain-bullseye-13 main
deb-src http://apt.llvm.org/bullseye/ llvm-toolchain-bullseye-13 main' | sudo tee /etc/apt/sources.list.d/llvm.list
```
```
sudo apt update && sudo apt upgrade -y
```

> Install required dev libraries
```
sudo apt install clang-13 libclang-13-dev lld-13 llvm-13-dev -y
```

> Set up `/usr/src` as the home base
```
cd /usr/src && sudo chown $USER:$USER .
```

> Clone zig and zls
```
git clone https://github.com/ziglang/zig
```
```
git clone https://github.com/zigtools/zls
```

> Install Zig build pre-requisites
```
sudo apt-get install -y clang-13 libclang-13-dev libclang-13-dev llvm-13 llvm-13-dev liblld-13 liblld-13-dev
```
> Build Zig
```
cd /usr/src/zig
```
From the [horse's mouth](https://github.com/ziglang/zig/wiki/Building-Zig-From-Source#instructions-1)
```
mkdir build
cd build
cmake ..
make install
```
