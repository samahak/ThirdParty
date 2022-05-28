x265 3.1.1


[Download]
 - http://ftp.videolan.org/pub/videolan/x265/


[Windows]
 - CMake 설치 필요.
 - NASM설치(nasm.us) 및 PATH 설정(Windows의 경우).
 - Visual Studio 2013 환경 선택.
   build - vc12-x86 : Visual Studio 2013 32bit.
   build - vc12-x86_64 : Visual Studio 2013 64bit.
 - build - build-all.bat 파일 실행.
 - CMake실행 후 "ENABLE_ASSEMBLY"체크/
 - CMake에서 Configure 누른 후 Generate 누름.
 - build 디렉토리의 "x265.sln" 파일로 VisualStudio 실행.
 - "Debug" 또는 "Release"로 compile.
 - header(x265.h, x265-config.h) 및 lib(x265-static.lib) 파일을 복사.

 * VS2019의 경우 VS2013(v120) 환경에서 구동하여 VS2019(v142)에 맞춰서 build하면 됨.

[Android]
libx265-android-master에 x265 source를 넣고 build.sh script를 실행.
* 아래 export를 필수로 해줘야 함.
  export NDK_ROOT=/Users/do/Desktop/work/LIB_ANDROID/android-ndk-r14b


[iOS]
x265foriOS.zip 압축파일 풀기.
x265foriOS.xcodeproj 로 Xcode 실행.
iOS Deployment Target을 8.0으로 설정.
 * 필요시 x265foriOS 디렉토리 내의 x265 source를 최신 source로 바꾸기.
 * Yuv compile error 발생시 motion.h 파일에서 common/yuv.h 파일을 보도록 수정.


[Linux]
cd build/linux
./multilib.sh
8bit 디렉토리 내에서 libx265.a  파일을 복사.
