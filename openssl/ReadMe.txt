OpenSSL 1.0.2p

[Windows]

1. 준비물.
   - openssl-1.0.2p.tar.gz 다운로드 : http://www.openssl.org
   - Active-Perl 다운로드 : http://www.activestate.com/activeperl/downloads
   - 7zip 다운로드 : https://www.7-zip.org/

2. tar는 풀고, active-perl, 7zip 은 설치하여 준비.
   - 기본 설치시, c:\perl 아래에 설치됨.

3. 빌드하기
   - D:(없으면 rebuild_openssl_vs2013.cmd의 드라이버 정보 수정) 에 openssl-1.0.2p.tar.gz 이동.
   - rebuild_openssl_vs2013.cmd 클릭.

  * rebuild_openssl_vs2019.cmd 내부의 경로는 PC에 맞게 수정해줘야 컴파일 성공.
  * VS2019의 경우 rebuild_openssl_vs2019.cmd 클릭.
  * VS2022의 경우 rebuild_openssl_vs2022.cmd 클릭.
     - VS2022 열어서 컴파일 하는 PC 경로에 맞게 수정.

4. 결과물 확인
   - openssl-1.0.2p-32bit-release-static-VS2013 : 32bit header and library.
   - openssl-1.0.2p-64bit-release-static-VS2013 : 64bit header and library.



[Android] - MAC에서 확인.

build_openssl_android.sh 파일의 Android 설정을 확인한다.
build_openssl_android.sh 파일과 openssl-1.0.2p.tar.gz 파일을 동일한 디렉토리로 복사한다.
openssl-1.0.2p.tar.gz 파일의 압축을 openssl-1.0.2p 디렉토리에 풀어준다.
./build_openssl_android.sh 실행.



[iOS] - MAC에서 확인.

openssl-iOS.zip 의 압축을 풀어준다.
./build-libssl.sh --version=1.0.2p --archs="ios_armv7 ios_armv7s ios_arm64" 실행.
include, lib(armv7, armv7s arm64) 디렉토리 확인.



[Linux] - CentOS 7.5에서 확인.

yum install openssl-devel
(1.0.2k 설치)
CMakeList.txt 파일에 ssl, crypto 추가.

