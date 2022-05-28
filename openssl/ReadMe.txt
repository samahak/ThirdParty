OpenSSL 1.0.2p

[Windows]

1. �غ�.
   - openssl-1.0.2p.tar.gz �ٿ�ε� : http://www.openssl.org
   - Active-Perl �ٿ�ε� : http://www.activestate.com/activeperl/downloads
   - 7zip �ٿ�ε� : https://www.7-zip.org/

2. tar�� Ǯ��, active-perl, 7zip �� ��ġ�Ͽ� �غ�.
   - �⺻ ��ġ��, c:\perl �Ʒ��� ��ġ��.

3. �����ϱ�
   - D:(������ rebuild_openssl_vs2013.cmd�� ����̹� ���� ����) �� openssl-1.0.2p.tar.gz �̵�.
   - rebuild_openssl_vs2013.cmd Ŭ��.

  * rebuild_openssl_vs2019.cmd ������ ��δ� PC�� �°� ��������� ������ ����.
  * VS2019�� ��� rebuild_openssl_vs2019.cmd Ŭ��.
  * VS2022�� ��� rebuild_openssl_vs2022.cmd Ŭ��.
     - VS2022 ��� ������ �ϴ� PC ��ο� �°� ����.

4. ����� Ȯ��
   - openssl-1.0.2p-32bit-release-static-VS2013 : 32bit header and library.
   - openssl-1.0.2p-64bit-release-static-VS2013 : 64bit header and library.



[Android] - MAC���� Ȯ��.

build_openssl_android.sh ������ Android ������ Ȯ���Ѵ�.
build_openssl_android.sh ���ϰ� openssl-1.0.2p.tar.gz ������ ������ ���丮�� �����Ѵ�.
openssl-1.0.2p.tar.gz ������ ������ openssl-1.0.2p ���丮�� Ǯ���ش�.
./build_openssl_android.sh ����.



[iOS] - MAC���� Ȯ��.

openssl-iOS.zip �� ������ Ǯ���ش�.
./build-libssl.sh --version=1.0.2p --archs="ios_armv7 ios_armv7s ios_arm64" ����.
include, lib(armv7, armv7s arm64) ���丮 Ȯ��.



[Linux] - CentOS 7.5���� Ȯ��.

yum install openssl-devel
(1.0.2k ��ġ)
CMakeList.txt ���Ͽ� ssl, crypto �߰�.

