OpenCV 2.4.X

[참고]
 - https://kkokkal.tistory.com/1298
 - opencv-2.4.13.6.zip : original source.
 - opencv_x64.zip : x64 compiled source.
 - opencv_core2413, opencv_highgui2413, opencv_imgproc2413.

[Download]
 - https://github.com/opencv/opencv/releases/


[Windows]
 - CMake 실행.
 - opencv source 및 build 디렉토리 지정(source 디렉토리/build).
 - Configure를 누르고 붉은색 화면 나오면 "core, imgproc" 필수 설정 및 WITH_CUDA 필수 해제후 Configure 누름.
 - Generate 누름.
 - build 디렉토리의 "OpenCV.sln" 파일로 VisualStudio 실행.
 - "Release"로 compile.
 - header 및 lib, dll 파일을 복사.
   (lib로 하는 경우 unresolved external symbol error 발생할 수 있음)
 - x64로 하는 경우 x64설정을 만들고 zlib등 경로를 재지정 필요.

* opencv_16_0_Win32.zip, opencv_16_0_x64.zip : D://에서 압축을 해제하고 VS2019로 컴파일.


[Android]


[iOS]


[Linux]

