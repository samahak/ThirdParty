x265 3.1.1


[Download]
 - http://ftp.videolan.org/pub/videolan/x265/


[Windows]
 - CMake ��ġ �ʿ�.
 - NASM��ġ(nasm.us) �� PATH ����(Windows�� ���).
 - Visual Studio 2013 ȯ�� ����.
   build - vc12-x86 : Visual Studio 2013 32bit.
   build - vc12-x86_64 : Visual Studio 2013 64bit.
 - build - build-all.bat ���� ����.
 - CMake���� �� "ENABLE_ASSEMBLY"üũ/
 - CMake���� Configure ���� �� Generate ����.
 - build ���丮�� "x265.sln" ���Ϸ� VisualStudio ����.
 - "Debug" �Ǵ� "Release"�� compile.
 - header(x265.h, x265-config.h) �� lib(x265-static.lib) ������ ����.

 * VS2019�� ��� VS2013(v120) ȯ�濡�� �����Ͽ� VS2019(v142)�� ���缭 build�ϸ� ��.

[Android]
libx265-android-master�� x265 source�� �ְ� build.sh script�� ����.
* �Ʒ� export�� �ʼ��� ����� ��.
  export NDK_ROOT=/Users/do/Desktop/work/LIB_ANDROID/android-ndk-r14b


[iOS]
x265foriOS.zip �������� Ǯ��.
x265foriOS.xcodeproj �� Xcode ����.
iOS Deployment Target�� 8.0���� ����.
 * �ʿ�� x265foriOS ���丮 ���� x265 source�� �ֽ� source�� �ٲٱ�.
 * Yuv compile error �߻��� motion.h ���Ͽ��� common/yuv.h ������ ������ ����.


[Linux]
cd build/linux
./multilib.sh
8bit ���丮 ������ libx265.a  ������ ����.
