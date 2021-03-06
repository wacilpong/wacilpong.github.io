---
title: "After reading <code>"
date: "2020-11-18"
tags: ["review", "computer-science"]
draft: false
og_description: "코드를 읽고 내맘대로 정리해보았다."
---

by Charles Petzold

## Bit

- 모스부호는 점(dot)과 선(dash)으로 이루어진다.
- 단지 점과 선은 깜빡임의 종류일 뿐이다.
- 점자는 이진형태(binary)를 지니며 6개의 형태로 이루어져 있다.
- **모스부호나 점자부호는 각각이 이루어진 요소의 제곱거듭만큼이 조합의 수이다.**
  ex) 모스부호에서 점과 선으로 이루어진 형태가 6개라면 표현할 수 있는 수는 2^6
  ex) 점자부호로 표현할 수 있는 최대의 수는 2^6
- 언어는 단지 부호에 불과하다. 숫자는 만국 공통어!
- 사람의 손가락과 발가락은 10이어서, 10진수가 보통 많이 사용된다.
   - 랍스터에게 적합한 숫자 체계는 4진수
   - 돌고래에게 적합한 숫자 체계는 2진수
   - 참고로 10진수 이외의 수를 셀 때는 그 중간 수를 생략하면 된다.
   - ex) 4진수: 0,1,2,3,10,11,12,13,20...
   - 즉, 모든 숫자 체계에서 가능한 숫자를 모두 사용하면, 그 다음 숫자는 반드시 10이 된다.
- **2진수 체계로 전기를 표현할 수 있게 된다.**
- 전신에 전류가 흐를 때는 1, 그렇지 않을 때는 0
- 수학자 John Wilder Tukey는 후에 컴퓨터가 유행이 되면 더욱 많이 사용할 것이라 생각했다.
- bigit, binit 같은 단어를 고려했지만 결국 `Bit`가 되었다.
- 사용하는 비트수가 많아지면 전달할 수 있는 정보의 양이 많아진다.
- 비트가 추가될 때마다 부호의 수는 두 배가 된다.
  - ex) 2^1은 비트수 1개, 2^2는 2, 2^3은 3, 2^4는 4...
  - 비트수를 구하려면 거듭제곱의 반대인 로그 연산을 하면 된다.
  - ex) 2^7 = 128, log 128의 비트수는 7 (밑수 2 생략함)
- 비트의 관점에서 점자는 6비트짜리 부호로, 생각보다 단순하다.
  - ex) 'code'라는 글자의 점자를 6비트 이진수로 표현하면 아래와 같다.
    100100 101010 100110 100010

<br />
<hr />

## Boolean algebra
- 조지 부울(George Boole)은 논리를 수학적으로 풀려 했고, 부울 대수를 확립했다.
  - 아래 문장을 수식으로 치환할 수 있다.
    ```text
    에냐는 1kg의 두부를 갖고 있다.
    베티는 에냐보다 2배 많은 두부를 갖고 있다.
    카르멘은 베티보다 2kg 많은 두부를 갖고 있다.
    디아는 카르멘보다 3배 많은 두부를 갖고 있을 때,
    디아가 갖고 있는 두부의 양은?

    A = 1
    B = 2 X A
    C = B + 2
    D = 3 X C
    ```
  - 일반적인 숫자뿐만 아니라 종류, 즉 집합에 대해서도 적용할 수 있다.
  - 부울 대수에서 `+`와 `x`기호는 각각 합집합(union)과 교집합(intersection)이다.
    - 고양이 세계에서 F를 암컷 고양이라고 할 때, 아래 수식의 결과값은 '모든 고양이'인 1이다.
      1 + F = 1
    - "하얀색이나 황색의 중성화된 수컷 고양이나, 하얀색이 아닌 중성화된 암컷 고양이, 또는 검정 고양이"
      (M x N x (W + T)) + (F x N x (1 - W)) + B

<br />
<hr />

## Byte
- `작은 부분`을 의미하는 `bite`라는 단어에서 유래했지만 bit와의 혼동을 피하기 위해 byte로 표기하게 되었다.
- 1956년경에 IBM에서 만들어졌다.
- IBM이 8비트인 바이트에 끌린 이유 중 하나는 `BCD`라 불리는 숫자 표시 형식을 저장하기 편리했기 때문이다.
- 아주 우연히도 세계 대부분의 문자를 저장하는 데 아주 이상적인 크기이다.
  - 세계의 대부분 문자가 256문자보다 적기 때문이지만 중국어, 일본어, 한국어의 경우는 아니다.
- 바이트는 흑백사진에서 회색조를 표현하는 단계로 사용하기에도 이상적이다.
  - 사람의 눈이 대략 256단계 정도의 명암을 구분할 수 있기 때문이다.
  - 하지만 대부분의 사람은 10비트인 1024단계를 구분할 수 있다.


<br />
<hr />

## RAM (Random Access Memory)에서 컴퓨터까지
- 새로운 값을 각각의 래치에 저장할 수 있고, 어떤 값이 저장되어 있는지 읽을 수 있는 메모리
  _feat. Random Access Memory by daft punk_
- `래치(latch)`란 데이터 값의 변화를 막을 수 있는 요소이다.
- 주소 값만 바꾸면 래치 중 어디서든 값을 읽고 쓸 수 있으므로 RAM이라고 불리는 것이다.
  - 반대로 값을 순차적으로 읽어야 하는 형태의 메모리는 `선형 메모리(linear memory)`이다.
  - 그러한 메모리에서는 101번지에 저장된 값을 읽으려면 100번지의 값부터 읽어야 한다.
  - 카세트 테이프를 생각해보면 이해하기 쉽다!
- RAM 구성을 종종 RAM배열이라고 부르는데, 8x1 형태라면 배열에 1비트 값을 8개 저장할 수 있다.
- RAM배열에 저장되는 값의 수 = 2^주소에 입력하는 비트 수
- 주소 입력이 1비트 증가할 때마다 메모리 양은 2배 증가한다.
  ```text
  1KB = 1024 byte = 2^10 byte
  2KM = 2048 byte = 2^11 byte
  3KB = 4096 byte = 2^12 byte
  ...
  ```
- 회로에 빗대어 보면, 바이트로 가득 찬 RAM배열의 전원을 끄면 모든 데이터가 사라지게 된다. 이것이 바로 RAM이 휘발성 메모리라고 불리는 이유다.
- `누산기(accumulator)`는 일련의 수를 더하거나 뺄 때 첫 번째 값을 저장하고 있는 래치이다.
- 누산기와 RAM을 조합해 명령을 통해 데이터가 처리되도록 만들 수 있다.
  - 명령에는 로드, 저장, 더하기, 빼기, ...분기(GoTo 명령), 중단 등이 있다.
  - 이는 곧 컴퓨터이다. 아주 기초적인 수준이지만!
  - 릴레이, 전선, 스위치 등은 모두 하드웨어이다.
  - 반대로 메모리에 입력되어 있는 명령어들과 숫자(데이터)들은 소프트웨어이다.
  - 소프트웨어를 작성하는 작업은 보통 컴퓨터 프로그래밍이라고 알려져 있다.


<br />
<hr />

## 마이크로프로세서
- 18세기에서 1940년대까지 컴퓨터(computer)라는 용어는 숫자를 계산하기 위해 고용된 사람인 계산사를 의미했다.
- IC(Integrated Circuit, 집적 회로)를 이용해 컴퓨터 프로세서를 만들면서 전체 프로세서를 하나의 회로 보드 상에 구현하는 것이 가능해졌다.
- 컴퓨터에서 작업에 사용되고 있는 숫자를 저장하기 위해 `스택(stack)`이 사용된다.
  - 어떤 물건을 바닥에서부터 위로 쌓고, 위에 있는 것부터 처리한다.
  - `LIFO(Last-in-first-out)` 형태의 저장 방식이다.
  - 스택은 단지 일반적인 RAM의 일부 영역을 사용한다.
- 마이크로프로세서는 컴퓨터를 구성하는 온갖 요소를 하나의 칩에 집적했다.
  - 최초의 마이크로프로세서는 인텔 4004이다.
  - 오늘날 가정용 컴퓨터의 마이크로프로세서는 거의 1,000,000,000게이트이다.
  - 메모리뿐 아니라 데이터를 전달하고 결과를 확인하도록 입/출력장치도 붙어있다.
  - memory mapped I/O 방식을 통해 메모리가 아닌 주변장치와 통신할 수 있다.
  - 무어의 법칙은 마이크로프로세서에 사용되는 트랜지스터 수가 18개월마다 2배씩 증가할 거라 예측했다.
- 최근 마이크로프로세서는 속도를 향상하기 위한 다양한 기법을 사용한다.
  - 대표적으로 `파이프라인`을 이용한다.
  - 프로세서가 하나의 명령을 수행하는 동안 다음 명령을 미리 읽어오는데, 이때 프로그램 수행 과정에서 분기가 어떻게 이루어질지 예측해 다음 명령어를 읽는 방식이다.

<br />
<hr />

## ascii to unicode
- 8비트가 표준이라서 아스키 부호가 기술적으로는 7비트이지만, 대부분 8비트인 값으로 저장된다.
- 전세계의 언어를 모두 표현하기 위해 아스키 부호를 대체할 유니코드(unicode) 개발을 시작했다.
- 유니코드의 부호 0000h부터 부호 007Fh까지의 처음 128문자는 아스키 문자와 동일하다.
- 유니코드는 하나의 문자를 저장하는 데 2바이트를 사용하지만(아스키는 1바이트), 문자 인코딩 체계의 모호성을 없앨 수 있다.

<br />
<hr />

## 메모리와 저장장치
- 메모리와 저장장치의 가장 큰 차이는 메모리의 휘발성에 대한 부분이다.
- 메모리(RAM, ROM)는 책상과 같아서 어떤 일을 직접 하려면 그 책상 위로 올린다.
- 저장장치는 서랍과 같아서 필요한 일이 있다면 서랍에서 꺼내서 책상 위로 올린다.
- 파일을 저장하고 꺼내는 것은 운영체제라고 불리는 소프트웨어 영역이다.

<br />
<hr />

## Linux from UNIX
- UNIX는 개인용으로 사용하기에는 크고 비싼 컴퓨터들을 위해 설계되었는데, 시분할(timesharing) 기법으로 다수의 사용자가 동시에 시스템을 이용할 수 있도록 했다.
- 터미널이라고 불리는 화면표시장치와 키보드를 가진 장치들이 여러 개 붙어 있고, 운영체제는 동시에 모든 사람에게 서비스를 제공하는 것처럼 보이도록 한다.
- GNU 프로젝트를 통한 소프트웨어는 유닉스와 호환될 수 있도록 만들어졌다.
- 이 프로젝트를 통해 **유닉스 호환 운영체제의 코어(커널)인 Linux 운영체제가 개발되었다.**

<br />
<hr />

## 저수준, 고수준 언어

- 어셈블리어는 컴퓨터의 하드웨어와 밀접한 관계를 가지고 있으므로 보통 저수준 언어라 불린다.
- **고수준 언어는 높은 추상화 수준을 가지는 프로그래밍 언어를 모두 지칭한다.**
  - 고수준 언어는 자신의 문법을 기계어로 변환할 수 있는 컴파일러(compiler)가 있어야 한다.
  - 어셈블리어에 비해 배우기 쉽고, 명확하고, 소스 파일의 크기도 작다.
  - 어셈블리어처럼 특정 프로세서에 의존하지 않으므로 이식성이 좋은 경우가 많다.
  - 그러나 어셈블리어로 작성된 프로그램보다 실행 파일은 더 크고 느릴 수 있다.
- `ALGOL`은 프로그래밍 언어의 원형(archetype)을 다수 포함하지만 더 이상 사용하지 않는 고수준 언어이다.
  ```
  (1) 변수의 할당, 조건문

  begin
    real a, b, c;

    a := 535.43;
    b := 289.771;
    c := a x b;

    print ('The product of ', a, 'and ', b, ' is ', c);


    if a < 0 then
      print ('Sorry, the number was negative);
    else
      begin
      ...
      end
    end
  end
  ```
  ```
  (2) 반복문

  begin
    real array a[1:100];
    integer i;

    for i := 1 step 1 until 100 do
      a[i] := sqrt(i);
  end
  ```
- 가장 많이 사용되고 있는 프로그래밍 언어들은 ALGOL 형식을 가지고, 전통적인 폰노이만 아키텍처에 기반을 두고 있다.

<br />
<hr />

## 인터넷 그래픽에 대하여

- 문자 기반의 화면에서 그래픽 위주의 화면 구성으로 변경되는 과정은 컴퓨터 진화에서 매우 중요하다.
- 화면은 픽셀(pixel, picture element)이라는 작은 사각형 점의 배열로 구성되어 있다.
- 각 픽셀에 사용되는 비트의 수는 종종 색 해상도(color resolution)라 불린다.
- **표현 가능한 색의 수 = 2^픽셀 당 비트의 수**
- 인터넷은 여러 데이터가 중앙에 집중되어 있지 않다는 점에서 초기 통신 시스템과는 다르다.
- 인터넷 그래픽 부분ㅇ서 가장 유명한 것은 HTTP를 이용하는 WWW(World Wide Web)이다.
- 대부분의 웹 브라우저는 HTML 파일을 볼 수 있게 해주며, 검색도 편한데, 이는 텍스트 파일 형식의 장점이기도 하다.
- HTML은 프로그래밍 언어는 아니고 단지 텍스트와 그래픽을 적절히 위치시켜줄 뿐이다.
- 서버 쪽에서 필요한 모든 작업은 CGI(Commen Gateway Interface) 스크립트를 통해 처리할 수 있다.
- 클라이언트 측에서는 Javascript 같은 간단한 프로그래밍 언어를 HTML에 포함해 구동시킬 수 있다.
- 사용자의 웹 브라우저는 HTML 텍스트를 해석하는 것처럼 Javascript 문장을 해석할 수 있게 된다.
- 사용자의 컴퓨터에서 바로 수행시킬 수 있는 프로그램을 웹 사이트에서 직접 제공?
  - Java는 컴파일 결과로 기계어가 아닌 바이트 코드가 생성된다.
  - 이는 JVM(Java Virtual Machine)이라는 가상의 컴퓨터로 구동되는 코드이다.
  - 따라서 어떤 머신에서 어떤 그래픽 운영체제를 사용하는지 상관없이 구동시킬 수 있다.
  - 플랫폼에 독립적인 프로그래밍이 가능하다.