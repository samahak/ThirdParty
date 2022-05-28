protobuf 3.0.0 compile.

[Windows]
 - cmake 디렉토리에서 cmake .
   * cmake -G "Visual Studio 9 2008"
   * cmake -G "Visual Studio 12 2013"
   * cmake -G "Visual Studio 17 2022" -A x64 or Win32
 - 생성된 sin파일을 열어 컴파일.
   * MT => MD로 변경후 compile.

   * vs2019는 vs2013으로 sin파일 만든 후 v120을 v142로 변경 후 compile.

 

[Android]
 - protobuf 디렉토리에서 configure와 *.sh 파일권한을 777로 변경.
 - build_Android_arm.sh 스크립트 실행.
 - build_Android_arm64.sh 스크립트 실행.


[iOS]
 - /tmp/에 source 이동.
 - autoconf, automake, libtool 설치.
 - automake version을 1.14.1로 맞춤.
   * http://1004lucifer.blogspot.com/2014/11/osx-mac-autotoolsautoconf-automake.html
 - protobuf 디렉토리에서 configure와 *.sh 파일권한을 777로 변경.
 - Desktop에서 build-iOS-protobuf-3.0.0.sh 스크립트 실행.
   * 스크립트의 arch 설정이 비정상적이라 armv7. armv7s. arm64를 한번씩 compile하여 해결.


[Linux]


[cpp source 파일 만들기]
protoc -I=./ --cpp_out=./ ./*.proto
