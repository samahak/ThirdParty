ffmpeg 4.1.3


[Download]
 - https://ffmpeg.org/download.html


[Windows]
C:\Program Files (x86)\Microsoft Visual Studio 12.0\Common7\Tools\Shortcuts
 - VS2013 x86 Native Tools Command Prompt
 - VS2013 x64 Native Tools Command Prompt

 * V3�� �ǽð� �˻縦 ���� ����.
 * VS2019��  VS2019 x86 Native Tools Command Prompt, VS2019 x64 Native Tools Command Prompt�� ����.

cd C:\MinGW\msys\1.0
 - msys.bat

cd ffmpeg-4.1.3-x86
 - CC=cl ./configure --toolchain=msvc --arch=x86_64 --enable-small --enable-static --disable-shared --disable-doc --disable-programs --disable-symver --disable-debug --disable-network --disable-zlib --disable-avdevice --disable-avformat --disable-avfilter --disable-swscale --enable-dxva2 --disable-everything --enable-encoder=h263 --enable-encoder=mpeg4 --enable-decoder=h263 --enable-decoder=mpeg4 --enable-decoder=h264 --enable-decoder=hevc --prefix=./install
 - make -j8;make install
=> [����] VS2013 x86 Native Tools Command Prompt���� ����� msys.bat������ VS2013�� x86 library compile.

cd ffmpeg-4.1.3-x64
 - CC=cl ./configure --toolchain=msvc --arch=x86_64 --enable-small --enable-static --disable-shared --disable-doc --disable-programs --disable-symver --disable-debug --disable-network --disable-zlib --disable-avdevice --disable-avformat --disable-avfilter --disable-swscale --enable-dxva2 --disable-everything --enable-encoder=h263 --enable-encoder=mpeg4 --enable-decoder=h263 --enable-decoder=mpeg4 --enable-decoder=h264 --enable-decoder=hevc --prefix=./install
 - make -j8;make install
 => [����] VS2013 x64 Native Tools Command Prompt���� ����� msys.bat������ VS2013�� x64 library compile.

 - install ���丮�� include�� lib(.a) ������ ����.

* nvideo codec �߰�.
FFmpeg NVIDIA ��� ( "ffnvcodec") ������

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
64bit�� ��� SDK 21�̻󿡼� �����ϱ⿡ 21 version �̻��� �����ؾ߸� compile ����.
arm compile error �ذ� ��� Ȯ���Ͽ� ����.
 - https://www.jianshu.com/p/484db5ec733f (ũ������ �ؼ��Ͽ� Ȯ��)
ffmpeg-4.1.3 ���丮 �ȿ� build_android_all.sh, build_android_arm.sh, build_android_arm64.sh
./build_android_all.sh ����.


[iOS]
ffmpeg-iOS ���丮 �ȿ� build_ffmpeg_iOS.sh �� ffmpeg-4.1.3 source�� ����.
./build_ffmpeg_iOS.sh ����.
 * �����ϸ� �Ʒ� ��ɾ� ����.
   - sudo xcode-select --print-path
   - sudo xcode-select --switch /Applications/Xcode.app


[Linux]
yum install nasm
./configure --enable-small --enable-static --disable-shared --disable-doc --disable-programs --disable-symver --disable-debug --disable-network --disable-zlib --disable-avdevice --disable-avformat --disable-avfilter --disable-swscale --disable-everything --enable-encoder=h263 --enable-encoder=mpeg4 --enable-decoder=h263 --enable-decoder=mpeg4 --enable-decoder=h264 --enable-decoder=hevc --disable-vaapi --prefix=./install
make
make install
