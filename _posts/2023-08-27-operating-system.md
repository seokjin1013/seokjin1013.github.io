---
layout: post
title: 운영체제 정리하기
date: 2023-08-27 22:03 +0900
category: [Background]
tag: [Operating System]
---

# 운영체제

사용자와 하드웨어 사이의 중계자로서 프로그램을 실행, 관리, 제어하는 시스템 소프트웨어

컴퓨터가 켜질 때 처음으로 적재

컴퓨터 자원을 독점적으로 관리

1. 운영체제는 **모든 컴퓨터의 자원을 관리**한다.
* 하드웨어 자원 - CPU, 캐시, 메모리, 키보드, 마우스 디스플레이, 하드디스크, 프린터
* 소프트웨어 자원 - 응용프로그램
* 데이터 자원 - 파일, 데이터베이스

2. 운영체제는 **자원에 대한 독점 권한**을 갖는다.
* 자원에 대한 모든 관리 권한은 운영체제에게만 있음.
* 자원 할당, 자원 공유, 자원 액세스, 자원 입출력 등의 권한.

3. 운영체제는 **관리자**이다.
* 실행 중인 프로그램 관리, 메모리 관리, 파일과 디스크 장치 관리, 입출력 장치 관리, 사용자 계정 관리

4. 운영체제는 **소프트웨어**이다.
* 커널이라고 불리는 핵심 코드, UI/도구 및 프로그램 (탐색기, 작업관리자, 제어판), 장치를 제어하는 디바이스 드라이버로 구성

운영체제는 컴퓨터 자원 관리의 효율성과 컴퓨터 사용의 편리성을 위해 존재한다.

CPU/프로세스 관리, 메모리 관리, 파일시스템 관리, 장치 관리, 네트워크 관리, 보안 관리, 기타 관리

응용소프트웨어는 하드웨어를 사용하고 싶으면 운영체제에게 요청한다. 운영체제는 하드웨어, 파일 등 자원 관리 목적 프로그램에게 메모리, 프로세서, 파일, 장치 관리, 하드웨어에 대한 독점 사용하여 공통 서비스를 제공한다.

'     | 운영체제    | 응용소프트웨어
---------|-----------|-------------
목적     | 컴퓨터 하드웨어나 응용소프트웨어 등 자원 관리 | 컴퓨터 사용자들의 요구를 충족시킬 수 있도록 설계된 소프트웨어
기능     | 프로세스, 메모리, 파일 시스템, 입출력 장치 등 자원 관리와 사용자 관리 | 소프트웨어를 만든 특정 목적만 수행
개발 언어 | C/C++, 어셈블리어 | C/C++ 뿐만 아니라 Java, Python, C# 등 다양한 언어
실행     | 부팅 시 메모리에 적재되어 실행을 시작하여 컴퓨터를 끌 때까지 실행 | 사용자가 명령을 통해 실행시키거나 종료
자원에 대한 접근 권한 | 컴퓨터의 모든 자원에 대해 배타적 독점 사용 권한 | 컴퓨터 자원을 사용하고자 할 때 반드시 운영체제에게 요청

# 운영체제의 역사

## 고정프로그래밍 방식

1940년대 전자식 디지털 컴퓨터가 만들어지기 시작하는 시대

운영체제에 대한 개념이 없음

소프트웨어와 하드웨어의 분리 개념이 없음 (모든 것이 하드웨어로 제작)

이 시대의 프로그래밍이란 종이에 프로그램을 구현하는 스위치와 전선 연결도를 작성하고 배선판에 전선을 연결한 뒤 프로그램을 기계에 고착시키는 것이다. 하나의 명령을 구성하기 위해 여러 가닥의 전선이 필요했고 프로그램 전체 구축에 수천 개의 전선을 연결하며 수 일이 소요되었다. 새로운 프로그램을 작성할 때마다 반복했다.

* 1941년, 독일, Z3 computer
* 1944년, 영국, Colossus (독일군의 암호를 해독하기 위함)
* 1943-1945년, 미국, ENIAC (최초의 전자식 컴퓨터, 방 하나를 가득 메우는 크기의 30톤 장비, 진공관이 약 18000개로 구성되었다.)

## 내장프로그래밍 방식 (Stored Programming)

1945년 폰 노이만이 제안

내장 프로그램 컴퓨터는 CPU와 메모리를 분리 (CPU 안에는 제어장치, 연산장치, 레지스터가 있음)

소프트웨어와 하드웨어를 분리 (실행할 프로그램을 메모리에 담아 CPU가 프로그램을 실행)

프로그램은 입력 장치를 통해 메모리에 적재된다. 프로그램은 펀치카드에 구멍을 뚫어 작성하였고 카드리더기로 프로그램을 메모리로 읽어들일 수 있었다.

* 1951년, EDVAC

## 프로그램 로더

1950년대 운영체제에 대한 개념이 생기기 시작

IBM701 메인 프레임 컴퓨터는 IBM이 1954년에 만들어 판매하지 않고 대여만 했던 컴퓨터였다. 어떤 소프트웨어도 제공하지 않았어서 사용자가 모든 것을 해야 했다. IBM 컴퓨터를 사용하는 법은 다음과 같다.
1. 프로그램 개발자 (=오퍼레이터)가 이름을 적어 대기명단에 올린 뒤 자신의 차례가 되기를 기다린다.
2. 자신의 차례가 되면 주어진 시간 15분안에 컴퓨터실에 들어가 카드 입력장치, 프린터, 테이프 장치 등을 확인하고 컨트롤 패널 앞에 선다. 프로그램의 입력, 실행, 출력을 모두 개발자가 컨트롤 패널을 통해 제어한다.
3. 카드 천공기를 통해 펀치카드에 프로그래밍을 한다. 모두 이진수로 펀치해야 한다. (이 후 어셈블리어로 펀치하도록 개선되었다.)
4. 펀치 카드를 카드 리더기에 쌓고 컨트롤 패널의 LOAD 버튼을 눌러 컴퓨터를 가동한다. (부트스트랩)
5. LOAD버튼은 한 장의 카드만 읽는 것으로 끝난다. 카드 한 장에는 최대 24개의 명령을 작성할 수 있다. LOAD버튼이 눌러지면, 카드 리더기를 이용하여 첫 번째 카드에 작성된 프로그램이 메모리의 0번지부터 순서대로 적재시키고 0번지 실행을 시작한다.
6. LOAD 버튼 대신 수동으로 프로그램을 입력하고 실행시키기 위해 컨트롤 패널에서 Enter Instruction 버튼, Start Button 등을 눌러 실행시킬 수도 있다.

IBM 701 개발자는 관행적으로 첫 번째 카드에는 다음 카드에 작성된 프로그램을 메모리에 적재하는 코드만 작성하고 두 번째 카드부터 목적하는 프로그램을 작성하였다. 그러다보니 첫 번째 카드는 항상 비슷하게 펀치되었고 프로그램 작성에 시간낭비임을 느끼게 되고 이를 해결하기 위해 로더 프로그램(목적 프로그램을 읽어들이는 코드)이 만들어지게 되었다.

로더 프로그램은 모든 컴퓨터에 공통적으로 필요한 것이고, 로더 프로그램이 오늘날 운영체제로 발전한 것이다. 로더 프로그램은 운영체제의 가장 기본적인 기능인 사용자의 명령을 받아 저장 장치에 담긴 프로그램을 메모리에 적재하는 기능을 수행하였다.

## 원시 운영체제 GM OS

1955년 IBM의 고객인 GM(General Motors)가 개발한 GM OS는 펀치카드에 찍힌 프로그램을 메모리로 로딩하는 로더 프로그램이 탑재되어있다. 로더 프로그램은 그 당시 모니터라고 불렀고, 목적 프로그램을 테이프에 저장하여 필요할 때마다 실행하였다(자기테이프 저장방식은 펀치카드보다 속도가 빠르다). GM OS는 사용자의 프로그램을 읽어 실행시켜준다는 점에서 최초의 운영체제라고 할 수 있다.

1. 개발자가 컨트롤 패널에서 로더 프로그램 (모니터) 를 메모리에 적재
2. 로더 프로그램이 사용자 프로그램을 메모리에 적재
3. 사용자 프로그램 실행

## 최초의 운영체제 GM-NAA I/O

1956-1957년 GM은 IBM 701의 처리속도를 높인 IBM 704를 주문하였고 GM은 3가지 문제점을 분석해낸다.

1. 많은 개발자들이 대기번호를 뽑고 자신의 차례를 기다림
2. 개발자가 프로그램을 실행시키기 위해 시스템을 설정하는 동안 컴퓨터가 놀게 됨
3. 카드 입력장치나 테이프 입력 장치를 제어하는 프로그램 코드와 하드웨어 서비스 루틴은 개발자가 별도로 알아서 작성하게 되어있는데, 이는 일반 개발자에게 많은 지식을 요구하게 하는 것이었다.

최초의 정식적인 운영체제 GM-NAA I/O는 GM과 NAA(North American Aviation)이 공동으로 개발하였다. 고가의 컴퓨터를 효율적으로 사용하기 위해 모니터 프로그램을 확장하여 구현하였다. 다음과 같은 운영체제로서의 모습을 갖추게 되었다.
1. 배치 방식으로 작동
2. 사용자 입출력을 다루는 코드는 메모리에 상주
3. 카드 입출력, 테이프 입출력, 프린터 출력 등 모든 입출력 장치를 제어하는 루틴을 라이브러리 형식으로 갖추고 프로그램 사이에 공유됨

GM NAA I/O는 메모리에 어셈블러 코드, 로더 프로그램, 공통 입출력 코드 및 메인 코드가 상주한다.
* 어셈블러 코드- 사용자가 어셈블리어로 프로그램을 작성할 수 있게 해줌. 이 프로그램은 기계어로 번역됨.
* 로더 프로그램- 사용자 프로그램을 하나씩 메모리에 적재
* 공통 입출력 코드 및 메인 코드- 장치 입출력을 다루는 프로그램 코드와 운영체제 시작 코드

GM-NAA I/O의 실행 과정은 다음과 같다.
1. 사용자가 작성한 펀치카드를 카드 리더기를 통해 테이프 장치에 읽어놓음
2. 입출력 메인 코드가 실행되어 자기 테이프 장치는 사용자 프로그램을 읽어서 기계어로 번역하고 테이프에 저장
3. 로더 프로그램으로 목적 프로그램을 적재 및 실행

# 운영체제의 발전

## 운영체제가 없었을 때
* 개발자가 펀치 카드에 프로그램을 작성
* 컴퓨터는 한 번에 한 개의 작업만 실행
* 컴퓨터는 개발자가 셋업하는 동안 유휴상태가 됨

## 배치 운영체제
* 개발자와 관리자를 구분
* 개발자는 펀치카드를 입력 데크에 두고 결과를 기다림
* 배치 운영체제는 자동으로 테이프 장치에 대기 중인 프로그램을 한 번에 하나씩 적재하고 실행
* 오늘 날의 배치 처리는 비대화식이고, 유닉스와 리눅스에는 cron, at, batch 명령이 있다. 낮은 우선순위에서 백그라운드로 실행시킨다.

## 다중프로그래밍 운영체제
* CPU 작업과 I/O 작업이 번갈아가며 반복되는 형태에서는 I/O작업이 일어나는 동안 CPU가 유휴상태가 되는 것을 개선
* 미리 메모리가 수용할만큼의 여러 개의 프로그램을 메모리에 적재
* 프로그램을 실행하다가 I/O가 발생하여 대기하게 되면 메모리에 적재된 다른 프로그램 실행
* 오늘날 모든 운영체제는 다중프로그래밍 운영체제이다.

다중프로그래밍 도입으로 발생한 이슈
* 큰 메모리 이슈- 여러 프로그램을 동시에 메모리에 올려놓기 위해서 큰 메모리가 요구됨
* 프로그램 메모리 할당 및 관리 이슈- 몇 개의 프로그램을 적재할지, 어디에 적재할지, 프로그램 당 메모리 크기를 어떻게 잡아야 할지 등의 이슈
* 메모리 보호 이슈- 프로그램이 다른 프로그램 영역을 침범하지 못하게 막는 방법이 필요
* CPU 스케줄링과 컨텍스트 스위칭- 실행시킬 프로그램을 선택하는 **스케줄링**이 필요, 프로그램 실행 상태를 저장할 **컨텍스트** 정의, 컨텍스트 스위칭 필요
* 인터럽트 개념 도입- 운영체제는 I/O 장치로부터 입출력 완료를 전달받는 방법이 필요
* 동기화- 여러 프로그램이 동일한 자원을 액세스할 때 발생하는 문제를 해결
* 교착 상태 해결- 프로세스들이 서로 상대가 가진 자원을 요청하면서 교착상태가 발생할 수 있음.

## 시분할 다중프로그래밍 운영체제
* 다중프로그래밍 운영체제와 거의 동시에 연구가 시작되어, 그 당시의 다중프로그래밍과 배치 처리의 문제점 2가지를 개선하기 위함 (비대화식 처리방식, 느린 응답시간, 오랜 대기시간)
* 1959, MIT John McCarty교수에 의해 연구됨
* 빠른 프로그래밍 디버깅이 필요했던 McCarty 교수
* 사용자에게 빠른 응답을 제공하는 대화식 시스템 제안
  - 터미널(키보드 + 모니터 + 전화선 + 모뎀)
  - 사용자는 터미널로 메인 컴퓨터에 원격 접속 (터미널은 각 개발자가 가지고 있고, 터미널과 연결된 모뎀과 메인프레임 컴퓨터에 부착된 모뎀이 전화선으로 연결되어 원격으로 신호를 주고받음)
  - 시간을 나누어 돌아가면서 각 터미널의 명령을 처리
* 1962, CTSS(Compatible Time Sharing System) 시분할 시스템 개발

## 개인용 운영체제

* 시분할 시스템은 사용자가 많아지면 응답속도가 저하되고, 터미널이 있는 전산실에서만 컴퓨터를 사용할 수 있었다는 불편함이 있었음
* 개인용 컴퓨터, 원격 접속 없이, 가정에서 혼자 사용하는 컴퓨터가 필요해짐
* 1971년, Intel 4004, 마이크로프로세스 CPU 장치를 통한 마이크로 컴퓨터 (개인용 컴퓨터)
* 메인프레임이나 미니컴퓨터에 비해 저렴함.
* 1980년, 개인용 운영체제 MS-DOS

MS-DOS는 부팅 프로그램이 들어있는 ROM이 장착되어있는데, 부팅 프로그램(=부트스트랩 코드, BIOS)은 컴퓨터를 부팅시키는 프로그램이다. 부팅 프로그램이 실행되면 하드웨어를 모두 테스트한 뒤 디스크의 특정 영역에 저장된 MS-DOS 운영체제 코드를 메모리에 적재한다. 이후 Windows, Mac OS, Linux가 생겨났다.

## 그 외

### 임베디드 운영체제

임베디드 컴퓨터는 자동차, 비행기 제어 시스템, 공장, 디지털 TV등 가전제품이나 산업현장 기계, 상용 제품에 내장된 특정 목적을 위한 소형 컴퓨터이다. 임베디드 운영체제는 임베디드 컴퓨터에서 장치를 제어하고 작동시키는 기능을 한다. (WinCE, Embedded Linux)

### 모바일 운영체제

모바일 컴퓨터는 하드웨어의 발전으로 휴대가능한 크기로 들고 다닐 수 있는 모바일 장치에 들어가는 컴퓨터이다. 적외선 장치, 지문인식기, 배터리 등의 장치를 내장한다. 모바일 운영체제는 모바일 컴퓨터를 운영하기에 특화된 운영체제이다.

### 운영체제 종류

* 데스크톱 운영체제- Windows, MacOS, Linux
* 서버 컴퓨터 운영체제- Unix계열 Linux, FreeBSD, Windows Server, MacOS 서버
* 모바일 운영체제- Android, iOS, BlackBerry, Bada, Symbian, Windows Mobile
* 임베디드 운영체제- WinCE
* 실시간 운영체제- PSOS, VxWorks, VRTX, RT-Linux, Lynx

### 아키텍처 종류

* 폰노이만 아키텍처- 다른 작업을 명령하고 싶으면 전선을 수정해야 했던 고정 프로그래밍 방식을 개선하여 프로그램만 바꾸면 다른 작업을 시킬 수 있도록 범용성을 향상시킨 구조
* 하버드 아키텍처- 프로그램 메모리와 데이터 메모리가 합쳐져 있어 병목현상이 컸던 폰노이만 아키텍처를 개선하여 명령용 버스와 데이터용 버스를 분리시킨 구조

현대의 컴퓨터는 폰노이만 아키텍처처럼 프로그램 메모리와 데이터 메모리는 한데 있지만 하버드 아키텍처처럼 데이터버스, 주소버스, 제어버스로 나뉜 형태를 띠고 있다.

# 컴퓨터 시스템

컴퓨터 시스템은 응용프로그램 층, 운영체제 층, 컴퓨터 하드웨어 층으로 나뉘어있다.

* 하드웨어는 운영체제로부터 배타적 독점적 지배를 받음
* 응용프로그램은 하드웨어에 직접 접근이 허가되지 않음
* 운영체제는 응용프로그램의 요구를 들어 하드웨어를 조작함

시스템 버스
: CPU, off-chip 캐시메모리, RAM을 연결하는 버스

I/O 버스
: 하드웨어 장치(네트워크 제어기, 디스플레이, 프린터 등)를 연결하는 버스

## 하드웨어

CPU
: 프로그램 코드를 해석하여 실행하는 중앙처리장치. 컴퓨터의 가장 핵심 장치이고 전원이 공급될 때 작동이 시작되며 메모리에 적재된 프로그램을 실행한다.

메모리
: CPU에 의해 실행되는 프로그램 코드와 데이터가 적재되는 공간. 프로그램은 실행되기 위해서는 반드시 메모리에 적재되어야 한다.

캐시 메모리
: CPU처리속도가 메모리 입출력 속도에 비해 빠르게 발전하여 느린 메모리 때문에 CPU의 대기시간이 늘게 되었던 것을 개선하고자 CPU와 메모리 사이에 설치된 소량의 빠른 메모리
* 온칩 캐시- CPU 내부의 캐시, 오늘날 대부분의 캐시는 온칩 캐시이다.
* 옵칩 캐시- CPU 외부의 캐시

캐시 메모리가 있는 경우 프로그램을 실행시키면 메인 메모리로 적재된 다음 캐시로 옮겨지고 캐시 메모리 상에서 프로그램 실행

장치
: 키보드, 프린터, 스캐너 등

버스
: 하드웨어와 데이터를 주고받기 위해 디지털 신호가 지나가는 여러 가닥의 선을 다발로 묶어 부르는 용어
* 주소 버스, 데이터 버스, 제어 버스로 구성
* 주소- 메모리, 입출력 장치, 저장 장치 내에 있는 저장소(레지스터)에 대한 번지 (0부터 시작)

CPU는 메모리나 입출력 장치에 값을 쓰거나 읽을 때 반드시 주소를 발생

* 시스템 버스- CPU, 캐시, 메모리 등 빠른 하드웨어 사이에 데이터 전송
* I/O 버스- 상대적으로 느린 입출력 장치들로부터 입출력 데이터 전송

I/O Controller & control circuit

* 입출력 장치를 제어하기 위한 하드웨어
* 입출력 장치에 명령 하달
* 메모리와 입출력 장치, CPU와 입출력 장치 사이에 데이터 전달 중계
* DMAC(Direct Memory Access Controller), INTC(Interrupt Controller)등을 포함

58P

CPU
: 메모리 액세스 시 주소 발생

32비트 CPU, 32비트 운영체제, 32비트 컴퓨터란?

1. CPU에 32개의 주소선이 있음, CPU가 최대 엑세스 할 수 있는 메모리가 4기가바이트
2. CPU에 입출력되는 32개의 데이터선이 있음, 한 번에 32비트 읽고 쓰기 가능

CPU 명령
: CPU가 해석하고 실행하는 기계 명령

* C언어나 자바 등의 소스코드와는 다름. CPU를 설계하는 기업이 명령어 개수, 형태, 동작, 이름을 결정
* CPU 명령의 개수는 수십개에서 수백개
* 서로다른 CPU끼리 명령어가 호환되지 않음

CPU 레지스터

* PC(Program Counter)- 다음에 실행할 명령의 메모리 주소 저장
* IR(In)