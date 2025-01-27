---
description: >-
  이 문서의 허가되지 않은 무단 복제나 배포 및 출판을 금지합니다. 본 문서의 내용 포함된 자료를 인용하고자 하는 경우 출처를 명시하고
  김종민(kimjmin@gmail.com)에게 알려주시기 바랍니다.
coverY: 0
---

# 1.1 Elastic Stack 소개

2004년 샤이 배논(Shay Banon)은 Compass 라는 이름의 오픈소스 검색엔진을 개발하였습니다. 샤이 배논이 처음 Compass 검색엔진 개발을 하게 된 계기는 요리 공부를 시작한 아내를 위해 레시피 검색 프로그램을 만들기 위해서였습니다. 레시피 검색 프로그램에 <mark style="background-color:yellow;">**아파치 루씬(Apache Lucene)을 적용하려던 중 루씬이 가진 한계를 보완하기 위해 새로 검색엔진을 만들기 위한 프로젝트를 시작한 것이 계기**</mark>입니다. 2010년 샤이는 Compass를 Elasticsearch라고 이름을 바꾸고 프로젝트를 오픈소스로 공개하였는데, 곧 수많은 검색 개발자들에게 인기를 얻으며 급속도로 성장하기 시작했습니다.\
_(그리고 샤이 배논의 아내는 아직도 레시피 프로그램을 기다리고 있습니다.)_

Elasticsearch 프로젝트는 2012년에 창시자 샤이 배논과 함께 스티븐 셔르만(Steven Schuurman), 우리 보네스(Uri Boness) 그리고 아파치 루씬 커미터인 사이먼 윌너(Simon Willnauer) 4인의 멤버에 인해 네델란드 암스텔담에서 처음 회사로 설립되었으며 집필중인 2019년 현재는 주 본사인 네덜란드 암스테르담과 캘리포니아 마운틴 뷰를 비롯한 전 세계에 직원들이 분포되어 있습니다.

Logstash, Kibana와 함께 사용 되면서 한동안 <mark style="background-color:yellow;">**ELK Stack (Elasticsearch, Logstash, Kibana)**</mark> 이라고 널리 알려지게 된 Elastic은 2013년에 Logstash, Kibana 프로젝트를 정식으로 흡수하여 한 지붕 아래에서 함께 개발을 해 나가고 있습니다. 2015년에는 회사명을 Elasticsearch 에서 Elastic으로 변경 하고, <mark style="background-color:yellow;">**ELK Stack 대신 제품명을 Elastic Stack이라고 정식으로 명명하면서 모니터링, 클라우드 서비스, 머신러닝 등의 기능을 계속해서 개발, 확장**</mark> 해 나가고 있습니다.
