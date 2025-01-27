---
description: >-
  이 문서의 허가되지 않은 무단 복제나 배포 및 출판을 금지합니다. 본 문서의 내용 및 도표 등을 인용하고자 하는 경우 출처를 명시하고
  김종민(kimjmin@gmail.com)에게 사용 내용을 알려주시기 바랍니다.
coverY: 0
---

# 2. Elasticsearch 시작하기

이번 장 부터는 본격적으로 Elasticsearch를 다루어 보도록 하겠습니다. 먼저 <mark style="background-color:red;">**데이터 색인**</mark>과 <mark style="background-color:red;">**REST API 구조**</mark>에 대해서 조금 더 설명한 후에 Elasticsearch를 설치하고 실행 해 보도록 하겠습니다.

Elasticsearch는 자바로 개발되었기 때문에 자바 실행이 가능한 환경이라면 어디서든 구동이 가능합니다. 보통은 유닉스 운영체제에서의 구동을 기준으로 하기 때문에 이 책에서도 <mark style="background-color:red;">**유닉스 환경**</mark>을 기준으로 설명을 진행하겠습니다. 리눅스 또는 맥OS 같은 유닉스 계열 운영체제의 사용자는 앞으로 책에서 설명할 내용을 따라 실습을 하면 됩니다. 윈도우 운영체제 사용자는 뒤에서 설명할 Kibana의 Dev Tool을 가지고 실습을 하면 됩니다.
