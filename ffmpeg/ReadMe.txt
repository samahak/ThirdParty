ffmpeg 4.1.3


[Download]
 - https://ffmpeg.org/download.html


[Windows]
C:\Program Files (x86)\Microsoft Visual Studio 12.0\Common7\Tools\Shortcuts
 - VS2013 x86 Native Tools Command Prompt
 - VS2013 x64 Native Tools Command Prompt

 * V3는 실시간 검사를 끄고 실행.
 * VS2019는  VS2019 x86 Native Tools Command Prompt, VS2019 x64 Native Tools Command Prompt로 실행.

cd C:\MinGW\msys\1.0
 - msys.bat

cd ffmpeg-4.1.3-x86
 - CC=cl ./configure --toolchain=msvc --arch=x86_64 --enable-small --enable-static --disable-shared --disable-doc --disable-programs --disable-symver --disable-debug --disable-network --disable-zlib --disable-avdevice --disable-avformat --disable-avfilter --disable-swscale --enable-dxva2 --disable-everything --enable-encoder=h263 --enable-encoder=mpeg4 --enable-decoder=h263 --enable-decoder=mpeg4 --enable-decoder=h264 --enable-decoder=hevc --prefix=./install
 - make -j8;make install
=> [참고] VS2013 x86 Native Tools Command Prompt에서 실행된 msys.bat에서는 VS2013용 x86 library compile.

cd ffmpeg-4.1.3-x64
 - CC=cl ./configure --toolchain=msvc --arch=x86_64 --enable-small --enable-static --disable-shared --disable-doc --disable-programs --disable-symver --disable-debug --disable-network --disable-zlib --disable-avdevice --disable-avformat --disable-avfilter --disable-swscale --enable-dxva2 --disable-everything --enable-encoder=h263 --enable-encoder=mpeg4 --enable-decoder=h263 --enable-decoder=mpeg4 --enable-decoder=h264 --enable-decoder=hevc --prefix=./install
 - make -j8;make install
 => [참고] VS2013 x64 Native Tools Command Prompt에서 실행된 msys.bat에서는 VS2013용 x64 library compile.

 - install 디렉토리의 include및 lib(.a) 파일을 복사.

* nvideo codec 추가.
FFmpeg NVIDIA 헤더 ( "ffnvcodec") 컴파일

git clone https://git.videolan.org/git/ffmpeg/nv-codec-headers.git
cd nv-codec-headers
make
make install PREFIX=/usr

Win32
PKG_CONFIG_PATH="/usr/lib/pkgconfig" CC=cl ./configure --toolchain=msvc --arch=x86_64 --enable-small --enable-static --disable-shared --disable-doc --disable-programs --disable-symver --disable-debug --disable-network --disable-zlib --disable-avdevice --disable-avformat --disable-avfilter --disable-swscale --enable-dxva2 --disable-everything --enable-encoder=h263 --enable-encoder=mpeg4 --enable-decoder=h263 --enable-decoder=mpeg4 --enable-decoder=h264 --enable-decoder=h264_cuvid --enable-hwaccel=h264_nvdec --enable-decoder=hevc --enable-decoder=hevc_cuvid --enable-hwaccel=hevc_nvdec --enable-cuda --enable-cuvid --enable-nvenc --enable-nonfree --extra-cflags="-I../CUDA/v11.1/include" --extra-ldflags="-L../CUDA/v11.1/lib/Win32" --prefix=./install

x64
PKG_CONFIG_PATH="/usr/lib/pkgconfig" CC=cl ./configure --toolchain=msvc --arch=x86_64 --enable-small --enable-static --disable-shared --disable-doc --disable-programs --disable-symver --disable-debug --disable-network --disable-zlib --disable-avdevice --disable-avformat --disable-avfilter --disable-swscale --enable-dxva2 --disable-everything --enable-encoder=h263 --enable-encoder=mpeg4 --enable-decoder=h263 --enable-decoder=mpeg4 --enable-decoder=h264 --enable-decoder=h264_cuvid --enable-hwaccel=h264_nvdec --enable-decoder=hevc --enable-decoder=hevc_cuvid --enable-hwaccel=hevc_nvdec --enable-cuda --enable-cuvid --enable-nvenc --enable-nonfree --extra-cflags="-I../CUDA/v11.1/include" --extra-ldflags="-L../CUDA/v11.1/lib/x64" --prefix=./install


[Android]
armv7-a / arm64-v8a compile.
64bit의 경우 SDK 21이상에서 지원하기에 21 version 이상을 설정해야만 compile 가능.
arm compile error 해결 방안 확인하여 수정.
 - https://www.jianshu.com/p/484db5ec733f (크롬으로 해석하여 확인)
ffmpeg-4.1.3 디렉토리 안에 build_android_all.sh, build_android_arm.sh, build_android_arm64.sh
./build_android_all.sh 실행.


[iOS]
ffmpeg-iOS 디렉토리 안에 build_ffmpeg_iOS.sh 및 ffmpeg-4.1.3 source를 복사.
./build_ffmpeg_iOS.sh 실행.
 * 실패하면 아래 명령어 실행.
   - sudo xcode-select --print-path
   - sudo xcode-select --switch /Applications/Xcode.app


[Linux]
yum install nasm
./configure --enable-small --enable-static --disable-shared --disable-doc --disable-programs --disable-symver --disable-debug --disable-network --disable-zlib --disable-avdevice --disable-avformat --disable-avfilter --disable-swscale --disable-everything --enable-encoder=h263 --enable-encoder=mpeg4 --enable-decoder=h263 --enable-decoder=mpeg4 --enable-decoder=h264 --enable-decoder=hevc --disable-vaapi --prefix=./install
make
make install
