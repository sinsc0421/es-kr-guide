---
coverY: 0
---

# 1.2 SSH, FTP 접속 환경 구성

GCP에서 생성한 VM instance에 접근 하기 위하여 SSH, FTP 접속 환경 설정

### 1. VM instance 접근을 위한 사용자키 생성 (SSH 공개키 인증방식)

**1.Xshell 실행**

**2.Xshell의 메뉴 : 도구 > 사용자 키 생성 마법사(W)...선택**

![](https://emunhi.com/data/img/201808/15162052921.png)

3.**RSA 선택, 2048 키길이 선택 (디폴트)**

![](https://emunhi.com/data/img/201808/15162249842.png)

4.**공개키 쌍을 자동으로 만든 후 다음**

![](https://emunhi.com/data/img/201808/15162353257.png)

5.**사용자 키 암호 입력 (추후 사용함)**

****![](<../../.gitbook/assets/image (20).png>)****

**6. 키생성 완료**

****![](<../../.gitbook/assets/image (9) (1).png>)****

**7. 정보 복사**

* **등록정보 > 공개키**

****![](<../../.gitbook/assets/image (7) (2).png>)****

* 공개키 복사

```
ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAyZW7+JkxXZD1KUyj7OxZQtDw7hUIKjAGcSZGLgR0C8Ium7yC9m4Q2PKmmjjnDXBBp1QbhtNpcudp0vHzS7h805tmTsT0cv/tZ45zUKI0in0Esh6Pufh2jJ5k+sboFquIy4dKMhqo/Zoqvz/lGWe5v3QROHOlckrkm+s4coFf/0aPPOTY3ySEcBt8b/8TFPkf6c4maWwQjqqtENBHiH089lKy0EIN6I3C2ZUJFzOhBxKPq0lwW2LK/NEAlm+f0so/6vNx20pE+7cuxmWMdRjcnVS+tIY3Wfae6ETiRdrF2GUeh0aTiS/Z33/b30z8fZgjnS7oHHrsHRc601lZV3dTBQ== rsa 2048-111422
```

* rsa @@@@ 부분 제외하고 최종 복사

```
ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAyZW7+JkxXZD1KUyj7OxZQtDw7hUIKjAGcSZGLgR0C8Ium7yC9m4Q2PKmmjjnDXBBp1QbhtNpcudp0vHzS7h805tmTsT0cv/tZ45zUKI0in0Esh6Pufh2jJ5k+sboFquIy4dKMhqo/Zoqvz/lGWe5v3QROHOlckrkm+s4coFf/0aPPOTY3ySEcBt8b/8TFPkf6c4maWwQjqqtENBHiH089lKy0EIN6I3C2ZUJFzOhBxKPq0lwW2LK/NEAlm+f0so/6vNx20pE+7cuxmWMdRjcnVS+tIY3Wfae6ETiRdrF2GUeh0aTiS/Z33/b30z8fZgjnS7oHHrsHRc601lZV3dTBQ==
```

### 2. 생성한 SSH 공개키를 GCP에 등록

1.설정 > 메타데이터 선택

2.SSH키 선택

![](<../../.gitbook/assets/image (12).png>)

3\. SSH키추가 (위 데이터 복사)

![](<../../.gitbook/assets/image (3) (2).png>)

위 데이터만 복사하였을때 다음과 같은 에러가 발생한다.

* 에러를 없애기 위해 띄어쓰기 한 뒤 가입한 계정명을 입력한다. (<mark style="color:blue;">**xxxx**</mark>@gmail.com)

ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAyZW7+JkxXZD1KUyj7OxZQtDw7hUIKjAGcSZGLgR0C8Ium7yC9m4Q2PKmmjjnDXBBp1QbhtNpcudp0vHzS7h805tmTsT0cv/tZ45zUKI0in0Esh6Pufh2jJ5k+sboFquIy4dKMhqo/Zoqvz/lGWe5v3QROHOlckrkm+s4coFf/0aPPOTY3ySEcBt8b/8TFPkf6c4maWwQjqqtENBHiH089lKy0EIN6I3C2ZUJFzOhBxKPq0lwW2LK/NEAlm+f0so/6vNx20pE+7cuxmWMdRjcnVS+tIY3Wfae6ETiRdrF2GUeh0aTiS/Z33/b30z8fZgjnS7oHHrsHRc601lZV3dTBQ== <mark style="background-color:blue;">**ericasearch1**</mark>

<mark style="background-color:blue;">****</mark>

### 3. SSH 접속

Xshell 파일(F) > 새로만들기 클릭

![](<../../.gitbook/assets/image (16) (1).png>)

* 호스트 (생성한 외부 IP)

![](<../../.gitbook/assets/image (6) (1).png>)![](<../../.gitbook/assets/image (1) (1) (1).png>)

* 사용자 인증 클릭
  * 사용자이름 : 계정명 입력 (<mark style="color:blue;">**xxxx**</mark>@gmail.com)
  * 인증법방 : public key 선택
    * 설정 클릭 후 생성한 사용자키, 암호 입력

![](<../../.gitbook/assets/image (11) (2).png>)



* 생성된 세션 더블클릭 후 수락 및 저장 클릭

![](<../../.gitbook/assets/image (31).png>)

* 완료

![](<../../.gitbook/assets/image (8) (2).png>)
