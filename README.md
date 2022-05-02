# Geant4-install-manual
***
## ​0. 표현 형식 설명 
```shell
 ​(숫자). (제목) : 목차이다. 
 ​- (문장) : 해야하는 행동을 적어둔 문장이다. 
 ​$ (문장) : 터미널에 입력해야 하는 코드를 적어둔 문장이다. 
 ​ # (문장) : 주석 및 설명문이다. 
```
***
## ​1. windows에 wsl 설치하기 
```shell
 ​- '제어판 > 프로그램 > 프로그램 및 기능 - Windows 기능 켜기/끄기'를 선택 >> Linux용 Windows 하위 시스템의 체크박스를 활성화 >> 재부팅 
 ​- 마이크로소프트 앱스토어에서 wsl 설치 
 ​- wsl 실행 및 사용자 계정 설정 
 ​ # wsl 이란? : Windows Subsystem for Linux, windows에서 linux 커널과 프로그램이 돌아가게 해줌 
```
***
## ​2. 유용한 linux 배포 패키지 설치 
```shell
 ​$ sudo apt update 
 ​ # 업데이트 가능한 패키지 리스트 최신화 

 ​$ sudo apt upgrade 
 ​ # 패키지 업데이트 
 ​  
 ​$ sudo apt install gedit neofetch htop tree git wget python3 python3-pip gfortran gnuplot nautilus eog gimp zip cargo okular firefox dialog spyder 
 ​ # gedit : gui 텍스트 에디터 
 ​ # neofetch : 컴퓨터와 os의 사양 및 정보를 알려주는 프로그램 
 ​ # htop : 더 나은 작업관리자 
 ​ # tree : 파일 경로를 tree로 나타내주는 명령어 
 ​ # git : git repository에서 소스코드 다운 및 코드 관리 
 ​ # wget : 인터넷 링크로 파일 다운로드 
 ​ # python3 : python 3.x버전 
 ​ # python3-pip : linux의 패키지 관리자가 apt라면, pip는 python의 패키지 관리자임. 각종 python 라이브러리를 다운받을 때 사용 
 ​ # gfortran : fortran 컴파일러. fortran은 타 언어보다 연산속도가 빨라서 반복 계산에 용이 
 ​ # gnuplot : 터미널에서 바로 그래프를 그리게 해줌 
 ​ # nautilus : 파일 관리자 
 ​ # eog : eye of gnome, gui 이미지 뷰어 
 ​  # gui: Graphical User Interface, windows 3.1이 나왔을 때를 생각하라 
 ​ # gimp : 이미지 편집 툴 
 ​ # zip : zip 파일 압축 관리자 
 ​ # cargo : Rust 언어의 패키지 관리자 
 ​ # okular : pdf 등 문서 뷰어 
 ​ # firefox : 파이어폭스 웹 브라우저 
 ​ # dialog : 터미널 상에서 gui를 만들어주는 라이브러리 
 ​ # spyder : 아주 멋진 python IDE 
 ​  
 ​$ cargo install viu 
 ​ # viu : cli 이미지 뷰어 
 ​  # cli : Command-Line Interface, MS-DOS 시절을 생각하라 
  
 ​$ echo 'PATH=$HOME/.cargo/bin:$PATH' >> ~/.bashrc 
 ​ # echo 'PATH=$HOME/.cargo/bin:$PATH' : 'PATH=$HOME/.cargo/bin:$PATH' 를 출력해라 
 ​  # PATH : 명령어가 들어있는 경로를 지정하는 환경변수 
 ​  # HOME : linux 사용자의 홈 경로 환경변수 
 ​ # >> ~/.bashrc : ~/.bashrc 파일 밑부분에 출력해라 
 ​  # ~/ : linux 사용자의 홈 경로 
 ​  # .bashrc : bash shell(linux terminal)이 시작할 때마다 실행되는 스크립트를 적는 파일 (windows 시작 프로그램 폴더를 생각하면 쉽다.) 
```
***
### ​번외. gedit 설정하기 
```shell
 ​- gedit 실행 >> 편집 >> 기본설정 >> 원하는 설정 선택 
 ​ # 추천 설정 : [보기] 줄 번호 표시, 현재줄 강조, 일치하는 괄호 강조, 
 ​              [편집기] 자동 들여쓰기, 자동 저장, 
 ​              [글꼴 및 색] 원하는 테마 선택 
 ​- gedit 실행 >> 보기 >> 강조모드 >> 원하는 언어 선택 
```
***
### ​번외. 명령어 자동완성 
```shell
 ​- 다음 문장을 ~/.bashrc 파일 맨 밑에 추가 
 ​# ------------------------------- # 
 ​bind 'set show-all-if-ambiguous on' 
 ​bind 'TAB:menu-complete' 
 ​# ------------------------------- # 
```
***
## ​3. wsl에서 gui 한글 입력 설정하기 
```shell
 ​$ sudo apt install fonts-nanum fonts-nanum-coding fonts-nanum-extra 
 ​ # 한글 폰트(나눔체) 설치 

 ​$ sudo apt install uim uim-byeoru 
 ​ # uim이라는 입력기 설치 
 ​ # byeoru라는 입력 방식 설치 
 ​  
 ​$ source ~/.bashrc 
 ​$ uim-pref-gtk 
 ​- [Global setting] >> default input method를 Byeoru로 선택 
 ​- [Byeoru key bindings 1] >> 한영키([on], [off])와 한자키([chinese characters]) 설정 
```
***
## ​4.사용할 Python 라이브러리 설치 
```shell
 ​$ sudo pip3 install pip --upgrade 
 ​ # pip 버전 업그레이드 
 ​  
 ​$ pip3 install matplotlib numpy scipy pandas colorama pillow 
 ​ # matplotlib : python에서 그래프를 그릴 때 쓰는 라이브러리, 매우 강력하다 
 ​ # numpy : 행렬 관련 계산 라이브러리 
 ​ # scipy : 과학용 계산 라이브러리 
 ​ # pandas : 데이터 프레임 라이브러리 
 ​ # colorama : 터미널 창 글자색 관리 라이브러리 
 ​ # pillow : 이미지 처리 라이브러리 
```
***
## ​5. windows에서 wsl 바로가기 만들기 
```shell
 ​- 파일 탐색기에 \\wsl$ 입력 
 ​- 바로가기 만들기 
```
***
## ​6. wsl에서 windows 바로가기 만들기 
```shell
 ​$ ln -s /mnt/c/User/{user name}/desktop . 
 ​ # {user name}엔 본인 컴퓨터의 사용자 명을 넣어야 한다 
```
***
## ​7. Xming 설치 
```shell
 ​ # Xming이란? : linux gui 프로그램 실행을 위해 사용되는 네트워크 기반의 gui 디스플레이 서버 프로그램 
 ​  
 ​- windows에 Xming 프로그램 다운로드, http://www.straightrunning.com/XmingNotes/ 
 ​- 설치 완료 후 Xming을 눌러 실행 
 ​$ echo "export DISPLAY=localhost:0" >> ~/.bashrc 
 ​ # export DISPLAY=localhost:0 : DISPLAY 라느 환경변수를 localhost:0 이라고 선언 
 ​  
 ​$ sudo apt update -y && sudo apt upgrade -y && sudo apt autoremove -y 
 ​ # -y : yes를 선택하는 옵션, && : 명령어를 연달아 실행하게 해줌 
 ​ # apt autoremove : 패키지 업데이트로 쓸모 없어진 기존 패키지를 자동 삭제 
 ​  
 ​$ sudo apt install -y build-essential cmake libexpat1-dev qt5-default libxmu-dev 
 ​ # [win버튼 + R] >> shell:startup 입력을 통해서 나온 시작 프로그램 폴더에 
 ​   Xming 실행 프로그램을 넣으면 컴퓨터가 시작할 때마다 자동적으로 Xming이 켜지게 할 수 있다 
```
***
## ​8. CLHEP 설치 
```shell
 ​ # CLHEP란? : Class Library for High Energy Physics, 일반 수치 프로그래밍, 벡터 산술,  
 ​   기하학, 의사난수 생성 및 선형 대수학을 제공하는 C++ 라이브러리 
 ​    
 ​$ sudo mkdir -p /opt/clhep 
 ​ # sudo : 관리자 권한으로 
 ​ # mkdir -p /opt/clhep : 폴더를 만들되 /opt/clhep 폴더가 없으면 /opt/clhep 폴더를 만들어라 
 ​  
 ​$ cd /opt/clhep 
 ​ # /opt/clhep 폴더로 이동 
 ​  
 ​$ sudo wget https://proj-clhep.web.cern.ch/proj-clhep/dist1/clhep-2.4.4.0.tgz 
 ​ # 관리자 권한으로 clhep-2.4.4.0.tgz 파일을 다운받아라 
 ​ # .tgz 확장자는 linux의 압축파일 확장자, windows의 .zip과 비슷하다 
  
 ​$ sudo tar -xvf clhep-2.4.4.0.tgz 
 ​ # 관리자 권한으로 clhep-2.4.4.0.tgz 파일의 압축을 풀어라 
 ​ # tar 는 압축 및 압축 해제 명령어 
  
 ​$ cd 2.4.4.0 
 ​$ sudo mkdir build 
 ​$ cd build 
 ​$ sudo cmake ../CLHEP -DCMAKE_INSTALL_PREFIX=/opt/clhep/2.4.4.0 
 ​ # cmake : 소스코드 빌드 시 환경변수를 설정해줌 
  
 ​$ sudo make -j `grep -c processor /proc/cpuinfo` && sudo make install 
 ​ # make : 소스코드를 컴파일해라, -j n : 컴파일 시 n개의 코어를 사용해라 
 ​ # `grep -c processor /proc/cpuinfo` : 컴퓨터의 코어 수 반환 
 ​ #  make install : 소스코드를 빌드해라 
```
***
## ​9. Geant4 data file 설치 
```shell
 ​$ sudo mkdir -p /opt/geant4/geant4data 
 ​$ cd /opt/geant4/geant4data 
 ​$ sudo wget https://geant4-data.web.cern.ch/datasets/G4NDL.4.6.tar.gz 
 ​$ sudo wget https://geant4-data.web.cern.ch/datasets/G4EMLOW.7.13.tar.gz 
 ​$ sudo wget https://geant4-data.web.cern.ch/datasets/G4PhotonEvaporation.5.7.tar.gz 
 ​$ sudo wget https://geant4-data.web.cern.ch/datasets/G4RadioactiveDecay.5.6.tar.gz 
 ​$ sudo wget https://geant4-data.web.cern.ch/datasets/G4SAIDDATA.2.0.tar.gz 
 ​$ sudo wget https://geant4-data.web.cern.ch/datasets/G4PARTICLEXS.3.1.1.tar.gz 
 ​$ sudo wget https://geant4-data.web.cern.ch/datasets/G4ABLA.3.1.tar.gz 
 ​$ sudo wget https://geant4-data.web.cern.ch/datasets/G4INCL.1.0.tar.gz 
 ​$ sudo wget https://geant4-data.web.cern.ch/datasets/G4PII.1.3.tar.gz 
 ​$ sudo wget https://geant4-data.web.cern.ch/datasets/G4ENSDFSTATE.2.3.tar.gz 
 ​$ sudo find -name "*.gz" -exec tar -xf {} \; 
 ​ # find -name "*.gz" : 하위 경로내에서 이름이 .gz로 끝나는 파일을 모두 찾아라 
 ​ # -exec tar -xf {} \; : 그리고 모두 압축을 풀어라 
 ​  
 ​$ sudo rm -rf *.gz 
 ​ # rm -rf *.gz : 하위 경로내에서 이름이 .gz로 끝나는 파일을 모두 지워라 
```
***
## ​10. Geant4 설치 
```shell
 ​$ sudo mkdir -p /opt/geant4/10.7.p03 
 ​$ cd /opt/geant4/10.7.p03 
 ​$ sudo wget http://geant4-data.web.cern.ch/geant4-data/releases/geant4.10.07.p03.tar.gz 
 ​$ sudo tar -xf geant4.10.07.p03.tar.gz 
 ​$ sudo mkdir build 
 ​$ cd build 
 ​$ sudo cmake ../geant4.10.07.p03 -DCMAKE_INSTALL_PREFIX=/opt/geant4/10.7.p03 -DGEANT4_BUILD_MULTITHREADED=ON -DGEANT4_INSTALL_DATADIR=/opt/geant4/geant4data -DGEANT4_USE_OPENGL_X11=ON -DGEANT4_USE_QT=ON -DGEANT4_USE_SYSTEM_CLHEP=ON -DCLHEP_DIR=/opt/clhep/2.4.4.0/lib/CLHEP-2.4.4.0 
 ​$ sudo make -j `grep -c processor /proc/cpuinfo`  
 ​$ sudo make install 
 ​ # 꽤 긴시간 소요 
 ​  
 ​$ echo "source /opt/geant4/10.7.p03/bin/geant4.sh" >> ~/.bashrc 
 ​$ source ~/.bashrc 
 ​ # ~/.bashrc 파일을 다시 실행하라 
  
 ​$ env | grep G4 
 ​ # env : 환경변수를 모두 출력하라 
 ​ # | grep G4 : 출력할 문장 중 G4를 포함한 문장만 출력 
```
***
## ​11. Geant4 예제 실행해보기 
```shell
 ​$ mkdir -p ~/geant4_works 
 ​$ cp -r /opt/geant4/10.7.p03/geant4.10.07.p03/examples/basic/B1 ~/geant4_works 
 ​$ cd ~/geant4_works/B1 
 ​$ mkdir build 
 ​$ cd build 
 ​$ cmake .. 
 ​ # .. : 이전 경로 
 ​ # . : 현재 경로 
 ​  
 ​$ make 
 ​$ ./exampleB1 run1.mac 
 ​ # exampleB1 실행 파일을 run1.mac에 적힌 설정대로 실행하라, cli 환경에서 실햄됨 
 ​  
 ​$ ./exampleB1 
 ​ # exampleB1 실행 파일을 실행하라, gui 환경에서 실햄됨 
 ​  
 ​- No such file or directory 관련 에러 발생 시 
 ​$ sudo strip --remove-section=.note.ABI-tag /usr/lib/x86_64-linux-gnu/libQt5Core.so.5 
```
***
## ​12. ROOT 설치 
```shell
 ​ # ROOT란? : Geant4를 만든 CERN에서 개발한 데이터 분석 툴 
  
 ​$ sudo mkdir -p /opt/root/6.26.02 
 ​$ cd /opt/root/6.26.02/ 
 ​$ wget https://root.cern/download/root_v6.26.02.Linux-ubuntu20-x86_64-gcc9.4.tar.gz 
 ​$ tar -xvzf root_v6.26.02.Linux-ubuntu20-x86_64-gcc9.4.tar.gz 
 ​$ echo "source /opt/root/6.26.02/root/bin/thisroot.sh" >> ~/.bashrc 
 ​$ source ~/.bashrc 
 ​$ root 
 ​$ new TBrowser 
 ​$ .q 
```
***
## ​13. CRY 설치 
```shell
 ​ # CRY란? : Cosmic-Ray shower librarY, 우주 방사선 샤워의 분포에 맞춰 랜덤한 입자를 생성하는 라이브러리 
 ​  
 ​$ sudo -p mkdir /opt/cry/1.7 
 ​$ cd /opt/cry/1.7 
 ​$ wget https://nuclear.llnl.gov/simulation/cry_v1.7.tar.gz 
 ​$ tar -zxvf cry_v1.7.tar.gz 
 ​$ cd cry_v1.7 
 ​$ make -j `grep -c processor /proc/cpuinfo`  
```
***
## ​14. CRY 예제 실행해보기 
```shell
 ​$ cd test 
 ​$ make all -j `grep -c processor /proc/cpuinfo` 
 ​$ ./testMain setup.file 1000 
 ​$ ./testOut setup.file 1000 
```
***
## ​15. 미리 만들어 둔 Geant4 코드 및 유용한 코드 다운로드 
```shell
 ​$ cd ~/ 
 ​$ git clone https://github.com/junobonnie/shellplot 
 ​$ cd ~/geant4_works 
 ​git clone https://github.com/junobonnie/Geant4-Auto-Run 
 ​git clone https://github.com/evandde/example_advpg 
```
***
## ​16. 예제 템플릿 코드 다운로드 
```shell
 ​$ mkdir -p ~/geant4_works/template 
 ​$ cd ~/geant4_works/template 
 ​$ git clone https://github.com/evandde/g4_minimal 
 ​$ wget https://github.com/evandde/g4_minimal/archive/refs/heads/examples.zip 
 ​$ unzip *.zip 
```
***
## ​17. Geant4 관련 자료 다운로드 
```shell
 ​$ mkdir -p ~/geant4_docs 
 ​$ cd ~/geant4_docs 
 ​$ wget https://www.cms-kr.org/pub/Main/InkyuPark/2009-NuclearSchool-Lecture1-ROOT.pdf 
 ​$ wget https://www.phys.hawaii.edu/~idlab/taskAndSchedule/HMBv3/presentations/CaT%20Geant4%20Simul.pdf 
 ​$ mkdir geant4_tutorial 
 ​$ cd geant4_tutorial  
 ​$ wget -m https://evandde.github.io/ 
```
***
## ​18. 자기장 관련 코드 다운로드 
```shell
 ​$ mkdir -p ~/geant4_works/field 
 ​$ cd ~/geant4_works/field 
 ​$ wget https://github.com/ejungwoo/opentutorials_Geant4/archive/refs/heads/field_and_uicmd.zip 
 ​$ unzip *.zip 
 ​$ wget https://indico.cern.ch/event/781244/contributions/3251909/attachments/1782359/2901794/MagneticField-v002.pdf 
```
***
## ​19. 여러 라이브러리 다운로드 
```shell
 ​$ mkdir -p ~/another_packages 
 ​$ cd ~/another_packages 
 ​$ wget https://nuclear.llnl.gov/simulation/radsrc_v1.6.tar.gz 
 ​$ wget https://nuclear.llnl.gov/simulation/fission_v2.0.5/fission_v2.0.5.tar.gz 
```
***
## ​20. dyastima 설치 
```shell
 ​- windows에 설치하기 http://cosray.phys.uoa.gr/index.php/dyastima 
 ​- 메뉴얼 다운하기 http://cosray.phys.uoa.gr/apps/DYASTIMA/DYASTIMA_USER_MANUAL.pdf 
```
***
## ​부록. 설치 구조 
```shell
 ​/ ─┬─ opt/ ─┬─ clhep/ ─ clhep-2.4.4.0.tgz 
 ​   │        │ 
 ​   │        ├─ geant4/ ─┬─ 10.7.p03/ ─ geant4.10.07.p03.tar.gz 
 ​   │        │           │ 
 ​   │        │           └─ geant4data/ ─┬─ G4NDL.4.6.tar.gz 
 ​   │        │                           ├─ G4EMLOW.7.13.tar.gz 
 ​   │        │                           ├─ G4PhotonEvaporation.5.7.tar.gz 
 ​   │        │                           ├─ G4RadioactiveDecay.5.6.tar.gz 
 ​   │        │                           ├─ G4SAIDDATA.2.0.tar.gz 
 ​   │        │                           ├─ G4PARTICLEXS.3.1.1.tar.gz 
 ​   │        │                           ├─ G4ABLA.3.1.tar.gz 
 ​   │        │                           ├─ G4INCL.1.0.tar.gz 
 ​   │        │                           ├─ G4PII.1.3.tar.gz 
 ​   │        │                           └─ G4ENSDFSTATE.2.3.tar.gz 
 ​   │        │  
 ​   │        ├─ root/ ─ 6.26.02/ ─ root_v6.26.02.Linux-ubuntu20-x86_64-gcc9.4.tar.gz 
 ​   │        │  
 ​   │        └─ cry/ ─ 1.7/ ─ cry_v1.7.tar.gz 
 ​   │ 
 ​   └─ home/ ─ $USER/ ─┬─ geant4_works/ ─┬─ Geant4-Auto-Run/ 
 ​                      │                 ├─ example_advpg/ 
 ​                      │                 │ 
 ​                      │                 ├─ template/ ─┬─ g4_minimal/ 
 ​                      │                 │             └─ examples.zip 
 ​                      │                 │ 
 ​                      │                 └─ field/ ─┬─ field_and_uicmd.zip 
 ​                      │                            └─ MagneticField-v002.pdf 
 ​                      │ 
 ​                      ├─ geant4_docs/ ─┬─ 2009-NuclearSchool-Lecture1-ROOT.pdf 
 ​                      │                ├─ CaT%20Geant4%20Simul.pdf 
 ​                      │                │ 
 ​                      │                └─ geant4_tutorial/ ─ evandde.github.io/ 
 ​                      │ 
 ​                      ├─ shellplot/ 
 ​                      │ 
 ​                      └─ another_packages/ ─┬─ radsrc_v1.6.tar.gz 
 ​                                            └─ fission_v2.0.5.tar.gz
```
