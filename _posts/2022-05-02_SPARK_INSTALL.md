---
title: " [INSTALL] SPARK 설치,셋팅하기 "
date: 2022-05-02
categories: INSTALL
---


# 1. 우선적으로 다운로드할 목록

## (1) 자바

**[Java SE 8 Archive Downloads (JDK 8u211 and later)](https://www.oracle.com/java/technologies/javase/javase8u211-later-archive-downloads.html)**

- 들어가서 내 컴퓨터에 맞는 버전 설치만 해두자.

## (2) 스파크

• 
    ◦ 설치 URL: **[https://www.apache.org/dyn/closer.lua/spark/spark-3.2.0/spark-3.2.0-bin-hadoop3.2.tgz](https://www.apache.org/dyn/closer.lua/spark/spark-3.2.0/spark-3.2.0-bin-hadoop3.2.tgz)** (2022년 1월 기준)

안전하게 이곳들어가서 

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled.png)

위에서 두번째줄 클릭한다.

여기서 중요한점은 spark-3.2.0 버전을 기억하는것.

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%201.png)

.tgz 압축을 풀기 위해서는 WinRAR 프로그램이 필요하다.

## (3) WinRAR

**[https://www.rarlab.com/download.htm](https://www.rarlab.com/download.htm)**

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%202.png)

내 컴퓨터에 맞는 것을 설치한다.

## (4) winutils

**[https://github.com/cdarlint/winutils](https://github.com/cdarlint/winutils)**

- 2022.04기준 들어가서 아까 우리가 받았던 3.2.0 버전을 눌러준다.

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%203.png)

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%204.png)

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%205.png)

다운로드를 눌러준다.

- C드라이브에 winutils 폴더를 만들고, bin폴더를 차례로 만들어준다.

# 2. 설치를 해보자

## (1) 하둡 폴더 만들기

- 우선 C드라이브에 hadoop 이란 폴더를 하나 생성하고, 아까전에 다운받았던 4가지 설치프로그램을 복사하여 폴더에 넣어둔다.

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%206.png)

- 그럼 이렇게 4개의 파일이 존재하게 된다.
    
    우선 winrar설치를 해주고
    
    spark-3.2.0을 winrar을 이용해 압축을 풀어준다.
    
- 알집이 설치되어 있는 윈도우 11의 경우

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%207.png)

더많은 옵션 보기

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%208.png)

알집이 없는 경우 Extact 어쩌고,,가 떠서 바로 누르면 됐지만, 안뜨는 경우 연결프로그램 winrar지정해서 풀어줬다.

## (2) spark 폴더 만들기

- 그럼 파일이 생성되는데 이름을 spark로 바꿔준다.
- spark 폴더안 파일들을 복사한다.
- C드라이브로 가서 spark 새폴더를 만든다.
- 복사한 spark폴더의 파일들을 새로만든 spark폴더에 붙여넣는다.

## (3) spark > conf 파일 수정

- C드라이브 spark폴더 > conf 폴더를 들어간다.
- [log4.properties](http://log4.properties) 를 메모장을 통해 연다.

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%209.png)

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2010.png)

- 혹시 모를 나중을 위해, 주석처리를 하고 파일을 변경한다.
- log4.rootCategory=ERROR, console
    - 작업 실행 시, 출력하는 모든 logs값들을 업앨 수 있다.

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2011.png)

## (4) 자바 설치

- 아까 다운로드한 자바를 설치해보자.

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2012.png)

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2013.png)

- 체인지 눌러서 경로를 이렇게 바꿔준다

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2014.png)

- 이 화면 나왔을때 변경 눌러서 C드라이브에 새폴더 jre만들고 경로를 지정해준다

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2015.png)

## (5) winutils 설치

- C드라이브에 만들어둔 winutils-bin 있는지 확인해준다.
    - 스파크가 윈도우 로컬컴퓨터가 하둡으로 착각하게 만들 프로그램이다.
- 명령프롬프트 cmd를 관리자 권한으로 열어준다.
- 잘보고 따라한다.

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2016.png)

# 3. 환경변수 설정

- 시스템 환경변수를 설정한다.
    - 필자는 오류가 나서 사용자변수, 시스템 변수 모두 동일하게 만들어줬다.
    
    ![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2017.png)
    
    ![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2018.png)
    
    ![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2019.png)
    
    ![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2020.png)
    
- 새 사용자 변수를 만들어 주고나서, Path를 들어간다
- 아래 코드를 추가한다
    - %SPARK_HOME%\bin
    - %JAVA_HOME%\bin

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2021.png)

- 파이썬 환경설정을 추가한다.

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2022.png)

- 두개의 환경변수 설정이 더 있었으나, 오류가 뜨는 바람에 설정하지 않았다.
    - 원래는 차례로 넣어줬다.
    
    ![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2023.png)
    
- 스파크 실행시 오류가 발생되어  사용자, 시스템 변수 모두에 위와 같은 변수들을 추가했다😂

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2024.png)

# 4. 대망의 스파크 테스트

- 오류가 났었는데 캡쳐를 미쳐 하지 못했다..
- cmd파일을 관리자 권한으로 열고 경로를 C드라이브 spark폴더로 잡는다.

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2025.png)

- 여기서 중요

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2026.png)

- 위의 코드 두줄을 쳤을때 숫자가 나와야 하지만 나는 무슨 0 + 2 부터해서 영어로 한 20줄은 넘는 오류가 뜬것같다.
- 그 이유에선 JAVA환경변수에 예전에 썼던 JAVA와 충돌해서 그런것 같다는 선생님 말씀에, 오늘 지정한 환경변수를 제외한 JAVA를 지우고 했으나 또 오류가 떠서!!!! 결국 아까 말했던 시스템과 사용자 환경변수를 모두 똑같이 추가해주고나서 재부팅 후에야..!!!

![Untitled](/images/2022-05-02_SPARK_INSTALL/Untitled%2027.png)

# 짜란~~ 떴습니다~~박수!