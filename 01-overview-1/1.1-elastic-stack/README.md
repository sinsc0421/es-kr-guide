---
coverY: 0
---

# 1.2 SSH, FTP 접속 환경 구성

GCP에서 생성한 VM instance에 접근 하기 위하여 SSH, FTP 접속 환경 설정

### 1. VM instance 접근을 위한 사용자키 생성 (SSH 공개키 인증방식)

**1.Xshell 실행**

**2.Xshell의 메뉴 : 도구 > 사용자 키 생성 마법사(W)...선택**

![](https://emunhi.com/data/img/201808/15162052921.png)

3.**보안이 좋은 키유형 RSA 와 키 길이는 적당히 선택 후 다음**

![](https://emunhi.com/data/img/201808/15162249842.png)

4.**공개키 쌍을 자동으로 만든 후 다음**

![](https://emunhi.com/data/img/201808/15162353257.png)

5.**사용자 키 암호는 나중에 사용하므로 잊지 않도록**

****![](<../../.gitbook/assets/image (22).png>)****

**6. 키생성 완료**

****![](<../../.gitbook/assets/image (17).png>)****

**7. 정보 복사**

**등록정보 > 공개키**

****![](<../../.gitbook/assets/image (5).png>)****

* 공개키 복사

```
ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAyZW7+JkxXZD1KUyj7OxZQtDw7hUIKjAGcSZGLgR0C8Ium7yC9m4Q2PKmmjjnDXBBp1QbhtNpcudp0vHzS7h805tmTsT0cv/tZ45zUKI0in0Esh6Pufh2jJ5k+sboFquIy4dKMhqo/Zoqvz/lGWe5v3QROHOlckrkm+s4coFf/0aPPOTY3ySEcBt8b/8TFPkf6c4maWwQjqqtENBHiH089lKy0EIN6I3C2ZUJFzOhBxKPq0lwW2LK/NEAlm+f0so/6vNx20pE+7cuxmWMdRjcnVS+tIY3Wfae6ETiRdrF2GUeh0aTiS/Z33/b30z8fZgjnS7oHHrsHRc601lZV3dTBQ== rsa 2048-111422
```

* rsa @@@@ 부분 제외하고 최종 복사

```
ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAyZW7+JkxXZD1KUyj7OxZQtDw7hUIKjAGcSZGLgR0C8Ium7yC9m4Q2PKmmjjnDXBBp1QbhtNpcudp0vHzS7h805tmTsT0cv/tZ45zUKI0in0Esh6Pufh2jJ5k+sboFquIy4dKMhqo/Zoqvz/lGWe5v3QROHOlckrkm+s4coFf/0aPPOTY3ySEcBt8b/8TFPkf6c4maWwQjqqtENBHiH089lKy0EIN6I3C2ZUJFzOhBxKPq0lwW2LK/NEAlm+f0so/6vNx20pE+7cuxmWMdRjcnVS+tIY3Wfae6ETiRdrF2GUeh0aTiS/Z33/b30z8fZgjnS7oHHrsHRc601lZV3dTBQ==
```

ㄴ
