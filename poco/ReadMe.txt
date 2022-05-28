Poco 1.7.7

[Download]
 - https://pocoproject.org/download/index.html


[Windows]
 - root ���丮���� cmake .
   * cmake -G "Visual Studio 9 2008"
   * cmake -G "Visual Studio 12 2013"
   * cmake -G "Visual Studio 17 2022"
 - ������ sin ������ ���� poco ������.
   * dll => lib�� ���ϸ��� ���������� Foundation, Net ����.
     => Foundation, Net�� properties - Configuration properties - General.
     => General - Target Extension - lib.
     => Project Defaults - Configuration Type - lib.


[Android]
 - Android toolchain ����.
 - .bash_profile�� toolchain PATH ����(32/64���� ����).
 - Poco ���丮�� poco-1.7.7 ���丮 �̸����� source�� ����.
 - build_android.sh ������ ABI ���� CPU�� �°�(arm-v7a, arm64-v8a) ���� �� ���� build.
 - ./build.sh 1.7.7 8.0 Android CLEAN
   * source������ compile �ȵǴ� ��� pwd�� ��� ��ҹ��� Ȯ��.
   * source������ compile �ȵǴ� ��� ANSI-PC�� source ������ ���� �ؾ� ���������� compile��.


[iOS]
 - Poco ���丮�� poco source�� ����.
 - ./build.sh 1.7.7 6.4 iOS CLEAN
  * �� compile�� Foundation, Net ���丮 ���� obj���丮 �����ؾ� ���� ���� �����.
 - ����� xcrun: error: SDK "iphoneos" cannot be located �̷� ���� �߸鼭 ���� �߻���
	=> sudo xcode-select --switch /Applications/Xcode.app ��ɾ� �Է�

lipo -create arm64/libPocoFoundation.a armv7/libPocoFoundation.a armv7s/libPocoFoundation.a -output libPocoFoundation.a
lipo -create arm64/libPocoNet.a armv7/libPocoNet.a armv7s/libPocoNet.a -output libPocoNet.a


[Linux]
 - CMakeList.txt ������ lib�� �����Ƿ� ����.
  * file(STRINGS "${PROJECT_SOURCE_DIR}/libversion" SHARED_LIBRARY_VERSION) => file(STRINGS "${PROJECT_SOURCE_DIR}/libversion" STATIC_LIBRARY_VERSION)
  * set( LIB_MODE SHARED ) => set( LIB_MODE STATIC )
 - cmake .
 - make
