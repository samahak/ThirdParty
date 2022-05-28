glib.2.71.0

[참고]
 - https://m.blog.naver.com/pdpdds/221733467947

[Download]
 - https://download.gnome.org/sources/glib/?C=M&O=D


[Windows]
 - 최신 glib소스를 다운로드 한다.
 - python 3.6.x 버전 이상을 설치.
 - meson 설치 : pip3 install meson
 - 64bit의 경우 : x64 Native Tools Command Prompt for VS 20XX 실행
 - 32bit의 경우 : x86 Native Tools Command Prompt for VS 20XX 실행
 - glib 압축을 푼 디렉토리로 이동.
 - build 디렉토리 생성후 build 디렉토리로 이동.
 - Visual Studio 20XX프로젝트 파일 생성 명령 실행 : meson .. --backend=vs
 - build 디렉토리의 glib.sln 파일을 Visual Studio 20XX로 실행.
 - 설정에서 configuration을 Release를 추가.
 - gio, glib, gmodule, gobject, gthread를 컴파일.
 - gio, glib, gobject header 파일을 복사.
 - gio, glib, gobject, gthread lib와 gio, glib, gmodule, gobject, gthread, ffi, intl, z dll을 복사.


[Android]


[iOS]


[Linux]

