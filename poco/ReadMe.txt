Poco 1.7.7

[Download]
 - https://pocoproject.org/download/index.html


[Windows]
 - root 디렉토리에서 cmake .
   * cmake -G "Visual Studio 9 2008"
   * cmake -G "Visual Studio 12 2013"
   * cmake -G "Visual Studio 17 2022"
 - 생성된 sin 파일을 열어 poco 컴파일.
   * dll => lib로 파일명이 떨어지도록 Foundation, Net 수정.
     => Foundation, Net의 properties - Configuration properties - General.
     => General - Target Extension - lib.
     => Project Defaults - Configuration Type - lib.


[Android]
 - Android toolchain 생성.
 - .bash_profile에 toolchain PATH 설정(32/64각각 설정).
 - Poco 디렉토리에 poco-1.7.7 디렉토리 이름으로 source를 넣음.
 - build_android.sh 파일의 ABI 값을 CPU에 맞게(arm-v7a, arm64-v8a) 설정 후 각각 build.
 - ./build.sh 1.7.7 8.0 Android CLEAN
   * source파일이 compile 안되는 경우 pwd로 경로 대소문자 확인.
   * source파일이 compile 안되는 경우 ANSI-PC로 source 파일을 설정 해야 정상적으로 compile됨.


[iOS]
 - Poco 디렉토리에 poco source를 넣음.
 - ./build.sh 1.7.7 6.4 iOS CLEAN
  * 재 compile시 Foundation, Net 디렉토리 안의 obj디렉토리 삭제해야 변경 내용 적용됨.
 - 빌드시 xcrun: error: SDK "iphoneos" cannot be located 이런 문구 뜨면서 에러 발생시
	=> sudo xcode-select --switch /Applications/Xcode.app 명령어 입력

lipo -create arm64/libPocoFoundation.a armv7/libPocoFoundation.a armv7s/libPocoFoundation.a -output libPocoFoundation.a
lipo -create arm64/libPocoNet.a armv7/libPocoNet.a armv7s/libPocoNet.a -output libPocoNet.a


[Linux]
 - CMakeList.txt 파일을 lib가 생성되록 수정.
  * file(STRINGS "${PROJECT_SOURCE_DIR}/libversion" SHARED_LIBRARY_VERSION) => file(STRINGS "${PROJECT_SOURCE_DIR}/libversion" STATIC_LIBRARY_VERSION)
  * set( LIB_MODE SHARED ) => set( LIB_MODE STATIC )
 - cmake .
 - make
