#1. 설치 필요 프로그램

1.innosetup-6.7.2.exe (exe file 포함해서 배포-설치 할 수 있게 만들어 주는 것)
2.pyinstaller : python code를 실행 파일(exe나 dll로 만들어주는 것)


#2. exe file 만들기
Test.py라는 파일을 exe만들기

pyinstaller --onefile --windowed --add-data "logo.png;." --add-data "Background_Img.png;." --icon="D:\my_icon.ico" Test.py

1. pyinstaller의미: "PyInstaller 프로그램을 실행해줘."패키징 작업을 시작하는 기본 명령어입니다.
2. --onefile의미: "결과물을 딱 하나의 .exe 파일로 만들어줘."이 옵션이 없으면
   PyInstaller는 실행 파일뿐만 아니라 수많은 .dll 파일과 폴더들이 담긴 디렉터리를 생성합니다.
   --onefile을 넣으면 이 모든 것을 하나의 깔끔한 단일 파일로 압축해 줍니다. 배포하기 가장 편한 형태가 되죠.
3. --windowed (또는 -w)의미: "프로그램 실행할 때 까만색 콘솔(CMD) 창 띄우지 마."GUI(지정된 화면 창이 있는)
   프로그램에 필수적인 옵션입니다. 만약 메모장이나 계산기 같은 프로그램을 만들었는데, 실행할 때마다 뒷배경에
   까만 콘솔 창이 같이 뜨면 지저분해 보이겠죠? 그걸 숨겨주는 역할을 합니다.
4. --add-data "logo.png;." 및 --add-data "Background_Img.png;."의미:
   "내 파이썬 코드가 사용하는 이미지 파일들도 .exe 파일 안에 같이 집어넣어 줘.
   "구조는 "원본_파일_경로;복사될_내부_경로" 형식입니다.logo.png;.
   $\rightarrow$ 현재 폴더에 있는 logo.png 파일을 빌드된 프로그램의 루트(주소 상 가장 기본이 되는 위치, .)에
   넣으라는 뜻입니다.세미콜론(;)은 윈도우(Windows) 운영체제에서 경로를 구분할 때 사용하는 기호입니다. 
