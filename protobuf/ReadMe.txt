protobuf 3.0.0 compile.

[Windows]
 - cmake ���丮���� cmake .
   * cmake -G "Visual Studio 9 2008"
   * cmake -G "Visual Studio 12 2013"
   * cmake -G "Visual Studio 17 2022" -A x64 or Win32
 - ������ sin������ ���� ������.
   * MT => MD�� ������ compile.

   * vs2019�� vs2013���� sin���� ���� �� v120�� v142�� ���� �� compile.

 

[Android]
 - protobuf ���丮���� configure�� *.sh ���ϱ����� 777�� ����.
 - build_Android_arm.sh ��ũ��Ʈ ����.
 - build_Android_arm64.sh ��ũ��Ʈ ����.


[iOS]
 - /tmp/�� source �̵�.
 - autoconf, automake, libtool ��ġ.
 - automake version�� 1.14.1�� ����.
   * http://1004lucifer.blogspot.com/2014/11/osx-mac-autotoolsautoconf-automake.html
 - protobuf ���丮���� configure�� *.sh ���ϱ����� 777�� ����.
 - Desktop���� build-iOS-protobuf-3.0.0.sh ��ũ��Ʈ ����.
   * ��ũ��Ʈ�� arch ������ ���������̶� armv7. armv7s. arm64�� �ѹ��� compile�Ͽ� �ذ�.


[Linux]


[cpp source ���� �����]
protoc -I=./ --cpp_out=./ ./*.proto
