x264


[Download]
 - http://ftp.videolan.org/pub/videolan/x264/

[Windows]
run “VS2013 x86 Native Tools Command Prompt” or “VS2013 x64 Native Tools Command Prompt” depending what version (32 or 64-bit) you want to build
change dir to x264 path and run MSYS shell (sh)
from shell run “CC=cl ./configure --disable-cli --enable-static” for x264 configuring
run “make” which should build libx264.lib usable from MSVS
P.S. MSVS builds would be a little bit slower than one build by MinGW

C:\Program Files (x86)\Microsoft Visual Studio 12.0\Common7\Tools\Shortcuts
 - VS2013 x86 Native Tools Command Prompt
 - VS2013 x64 Native Tools Command Prompt

cd C:\MinGW\msys\1.0
 - msys.bat

cd x264
 - CC=cl ./configure --enable-static --disable-asm --disable-cli
 - make -j8;make install
 => VS2013 x86 Native Tools Command Prompt에서 실행된 msys.bat에서는
      VS2013용 x86 library compile.
 => VS2013 x64 Native Tools Command Prompt에서 실행된 msys.bat에서는
      VS2013용 x64 library compile.

 - header(x264.h, x264-config.h) 및 lib(libx264.lib) 파일을 복사.

 * VS2019의 경우 VS2019 x86 Native Tools Command Prompt 에서 32bit 컴파일.
 * VS2019의 경우 VS2019 x64 Native Tools Command Prompt 에서 64bit 컴파일.


[Android]
  x264 압축을 푼다.
  build_android_all.sh, build_android_arm.sh, build_android_arm64.sh 를 x264 디렉토리 안으로 복사.
 * script 파일에서 ^M이 있는 경우 삭제 해야됨
  x264 디렉토리 안에서 ./build_android_all.sh 실행.


[iOS]
  sudo xcode-select --reset
  x264_compile 디렉토리를 만든 후 build-iOS.sh 와 x264 압축을 푼 source를 넣어준다.
  chmod 777 x264/*
  chmod 777 x264/tools/*
  vi x264/configure
  vi x264/config.sub
  vi x264/version.sh
  vi x264/tools/gas-preprocessor.pl
  :set fileformat=unix
  :wq
  ./build-iOS.sh 실행.
  lipo -create thin-x264/arm64/lib/libx264.a thin-x264/armv7/lib/libx264.a thin-x264/armv7s/lib/libx264.a -output libx264.a


[Linux]
CentOS 7.x 기준.
yum install nasm
^M 에러 해결 : set fileformat=unix
 - configure, config.guess, config.sub, version.sh.
./configure --enable-static --disable-asm --disable-cli
make -j8;make install