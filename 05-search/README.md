---
description: >-
  이 문서의 허가되지 않은 무단 복제나 배포 및 출판을 금지합니다. 본 문서의 내용 및 도표 등을 인용하고자 하는 경우 출처를 명시하고
  김종민(kimjmin@gmail.com)에게 사용 내용을 알려주시기 바랍니다.
coverY: 0
---

# 5. 검색과 쿼리 - Query DSL

이번 장은 Elasticsearch의 검색 기능에 대한 전반적인 내용을 모두 설명합니다. 내용이 많지만 Elasticsearch의 동작을 이해하는 데에 중요한 부분이기 때문에 차근차근 읽으면서 잘 숙지하시기 바랍니다.

### 검색 (Search)

\*\*검색(retrieval)\*\*이란 사전적인 의미로

> 1. **책이나 컴퓨터에 들어 있는 자료 중 필요한 자료를 찾아냄**
> 2. **범죄나 사건을 밝히기 위한 단서나 증거를 찾기 위하여 살펴 조사함**

등을 의미합니다. 필자는 데이터 시스템에서의 검색은

> **수많은 대상 데이터 중에서 조건에 부합하는 데이터로 범위를 축소하는 행위**

라고 정의를 합니다.

인터넷 쇼핑몰에 상품이 100만개가 있을 때 검색창에 **"무선 이어폰"** 이라고 입력해서 시스템에 있는 전체 100만개의 상품들 중 무선 이어폰과 연관된 상품만 추려내는 과정을 검색이라고 할 수 있습니다. 검색 엔진 설정에 따라 상품명이 정확히 <mark style="background-color:yellow;"></mark> <mark style="background-color:yellow;"></mark><mark style="background-color:yellow;">**"무선 이어폰"**</mark> 인 것만 보여줄지, <mark style="background-color:yellow;"></mark> <mark style="background-color:yellow;"></mark><mark style="background-color:yellow;">**"소니 무선 이어폰"**</mark> <mark style="background-color:yellow;"></mark><mark style="background-color:yellow;">처럼 전체 상품명</mark> 중에 검색어를 포함하기만 하면 보여줄지, 가격, 출시일 등과 같이 다른 조건들에 대해서는 어떻게 영향을 받도록 할 것인지 등을 결정할 수 있을 것입니다.

상품명이 정확히 **"무선 이어폰"** 인 것만 검색 하도록 조건을 엄격하게 하면 표시되는 결과 수가 적어져서 내가 찾는 상품이 나타나지 않을 수 있을 것입니다.&#x20;

반대로 상품 설명에 **"무선"** 과 **"이어폰"** 이 하나라도 있는 상품을 모두 검색하도록 하면 **"무선 리모컨"**, **"이어폰 케이스"** 같은 상품까지 검색이 되면서 결과가 너무 많아져서 내가 찾는 상품이 묻혀 버릴 수 있을 것입니다.&#x20;

품질이 높은 검색 시스템을 구현하기 위해서는 이렇게 많은 부분들을 고민해야 합니다.



Elasticsearch 는 사용자가 이런 여러가지 검색 조건들에 대해 목표로 하는 검색 기능을 구현할 수 있도록 다양한 기능들을 제공합니다.&#x20;

Elasticsearch 는 데이터를 실제로 검색에 사용되는 검색어인 **텀(Term)** 으로 분석 과정을 거쳐 저장하기 때문에 검색 시 대소문자, 단수나 복수, 원형 여부와 상관 없이 검색이 가능합니다.&#x20;

이러한 Elasticsearch의 특징을 **풀 텍스트 검색(Full Text Search)** 이라고 하며 한국어로 **전문 검색** 이라고도 합니다.

텀(Term)에 대해서는 나중에 텍스트 분석 부분에서 자세히 설명하겠습니다.



### Query DSL (Domain Specific Language)

Elasticsearch 는 검색을 위한 쿼리 기능을 제공합니다. 이런 데이터 시스템에서 제공하는 쿼리 기능을 Query DSL (Domain Specific Language) 이라고 이야기 하며 Elasticsearch 의 Query DSL 은 모두 **json** 형식으로 입력해야 합니다.

{% hint style="warning" %}
Basic 라이센스 이상에서는 표준 SQL 문으로 사용 가능한 **Elasticsearch SQL** 기능을 지원합니다.&#x20;

오라클이나 MySQL 에 익숙한 사람들에게는 처음에는 편할 수 있지만 Elasticsearch 의 모든 검색 기능들을 100% 활용하지 못하기 때문에 json 형식의 쿼리가 다소 생소하더라도 차근 차근 시간을 들여 Elasticsearch 의 Query DSL 을 잘 숙지하며 활용하기를 바랍니다.


{% endhint %}
