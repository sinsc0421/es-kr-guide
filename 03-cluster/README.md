---
description: >-
  이 문서의 허가되지 않은 무단 복제나 배포 및 출판을 금지합니다. 본 문서의 내용 및 도표 등을 인용하고자 하는 경우 출처를 명시하고
  김종민(kimjmin@gmail.com)에게 사용 내용을 알려주시기 바랍니다.
coverY: 0
---

# 3. Elasticsearch 시스템 구조

Elasticsearch는 대용량 데이터의 증가에 따른 스케일 아웃과 데이터 무결성을 유지하기 위한 클러스터링을 지원합니다.&#x20;



항상 클러스터를 기본으로 동작을 하며 <mark style="background-color:red;">**"1개의 노드"만 있어도 클러스터로 구성**</mark>이 됩니다.
