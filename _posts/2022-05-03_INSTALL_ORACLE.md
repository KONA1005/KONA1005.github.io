---
title: " [INSTALL] ORACLE 설치하기 "
date: 2022-05-03 
categories: INSTALL
---

# 오라클 설치

- [https://www.oracle.com/kr/database/technologies/oracle19c-windows-downloads.html](https://www.oracle.com/kr/database/technologies/oracle19c-windows-downloads.html)
- 오라클 19c (교재와 같은것 설치) 사양에 맞는것 다운로드 후 설치한다.
- 압축파일을 풀고 설치를 진행한다

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%201.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%202.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%203.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%204.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%205.png)

- 비밀번호는 1234
- 에러나서 소프트웨어만 설정으로 다시 설치한다. (전역데이터베이스 myoracle 설치 해야함)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%206.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%207.png)

실행창은 이렇게 뜸

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%208.png)

- 설치가 제대로 됐나 확인한다.

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%209.png)

- cmd 창을 열어 확인한다 sql_lecture>dir / sql_lecture>cd WINDOWS.X64~~~_db_home>dir

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2010.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2011.png)

- 비밀번호는 동일하다. 1234

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2012.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2013.png)

오류~

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2014.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2015.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2016.png)

- 껏다가 다시 하니까 됐다

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2017.png)

- Database Configuration Assistant 클릭

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2018.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2019.png)

## 테이블스페이스 생성

- 설치 완료후 SQL PLUS 을 킨다.

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2020.png)

- 사용자명 system 비밀번호 1234
- 아래의 코드를 입력한다.

```bash
CREATE TABLESPACE myts DATAFILE 'C:\sql_lecture\oradata\MYORACLE\myts.dbf' SIZE 100M AUTOEXTEND ON NEXT 5M; 
```

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2021.png)

## 사용자 생성

### 1. 사용자 생성하기

- IDENTIFIED = 비밀번호
- 아래의 코드를 입력한다.

```bash
CREATE USER ora_user IDENTIFIED BY kona DEFAULT TABLESPACE MYTS TEMPORARY TABLESPACE TEMP;
```

- 테이블스페이스 임시(TEMP) 테이블, 기본(디폴트)을 명시해 줄 수 있다

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2022.png)

### 2. 롤 부여하기 / 사용자 계정으로 DB 접속하기

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2023.png)

- DBA라는 롤을 부여받으면 오라클에서 제공하는 웬만한 기능은 모두 사용할 수 있다.
- 아래의 코드를 입력한다.
- select user from dual을 입력하면 현재 로그인한 사용자 이름이 출력된다.

```bash
connect ora_user/kona;
```

```bash
select user from dual;
```

## SQL DEVELOPER

- [https://www.oracle.com/kr/database/technologies/oracle19c-windows-downloads.html](https://www.oracle.com/kr/database/technologies/oracle19c-windows-downloads.html)
- 설치

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2024.png)

- 아니오를 누른다.

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2025.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2026.png)

- 비밀번호는 아까 설정한 kona
- 테스트를 누른다.

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2027.png)

- 상태 실패라는 오류가 떴다.

### 오류 해결하기

- cmd에 lsnrctl status 를 입력해본다

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2028.png)

- Oracle Net Configuration Assistant를 실행한다.

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2029.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2030.png)

- 다 디폴트로 (다음만 눌렀다 계속)
- 리스너를 잡아줬다.

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2031.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2032.png)

- 테스트 상태 성공이 떴다. 저장한다.

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2033.png)

- 비밀번호 창에 kona 입력 했다.
- [도구]-[환경설정]-[데이터베이스]-[NLS]

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2034.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2035.png)

- 시간기록형식을 YYYY/MM/DD HH24:MI:SS 으로 변경한다.

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2036.png)

## 스키마설치

- C드라이브에 backup 폴더를 만들어준다.
- [https://github.com/gilbutITbook/006696/tree/master/01%EC%9E%A5%20%ED%99%98%EA%B2%BD%EC%84%A4%EC%A0%95](https://github.com/gilbutITbook/006696/tree/master/01%EC%9E%A5%20%ED%99%98%EA%B2%BD%EC%84%A4%EC%A0%95)
- 밑에 두개 다운후 백업폴더에 옮겨준다.

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2037.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2038.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2039.png)

- cmd 창을 켜고 백업폴더의 경로로 간다.
- 아래 코드를 입력해준다.

```bash
imp ora_user/kona file=expall.dmp log=empall.log ignore=y grants=y rows=y indexes=y full=y
```

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2040.png)

- 마찬가지로 아래 코드를 입력해준다.

```bash
imp ora_user/kona file=expcust.dmp log=expcust.log ignore=y grants=y rows=y indexes=y full=y
```

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2041.png)

![Untitled](/images/2022-05-03_INSTALL_ORACLE/Untitled%2042.png)

- 이렇게 나오면 설치가 끝났다.