# Elastic 가이드 북

> 이 가이드북은 출판을 위해 집필중이던 내용을 Elastic을 처음 시작하시는 분들께 도움이 되고 커뮤니티와 함께 완성 해 나가려는 목적으로 공개하게 되었습니다. 모든 문서에 대한 저작권은 저자인 [**김종민**](http://kimjmin.net)에게 있으며 허가되지 않은 무단 복제나 배포 및 출판을 금지합니다. 본 문서의 내용 및 도표들을 인용하고자 하는 경우 출처를 명시하고 **김종민\(kimjmin@gmail.com\)**에게 사용 내용을 알려주시기 바랍니다.

## 목차

* [1. 서문](01-overview/)
  * [1.1 Elastic Stack 소개](01-overview/1.1-elastic-stack/)
    * [1.1.1 Elasticsearch](01-overview/1.1-elastic-stack/1.1.1-elasticsearch.md)
    * [1.1.2 Logstash](01-overview/1.1-elastic-stack/1.1.2-logstash.md)
    * [1.1.3 Kibana](01-overview/1.1-elastic-stack/1.1.3-kibana.md)
    * [1.1.4 Beats](01-overview/1.1-elastic-stack/1.1.4-beats.md)
* [2. Elasticsearch 시작하기](02-install/)
  * [2.1 데이터 색인](02-install/2.1.md)
  * [2.2 설치 및 실행](02-install/2.2/)
    * [2.2.1 다운로드 설치 및 실행](02-install/2.2/2.2.1-download-install.md)
    * [2.2.2 Unix RPM \(yum\) 설치 및 실행](02-install/2.2/2.2.2-unix-rpm-yum.md)
    * [2.2.3 윈도우 운영체제에서 MSI 파일로 설치](02-install/2.2/2.2.3-msi.md)
  * [2.3 elasticsearch 환경 설정](02-install/2.3-elasticsearch/)
    * [2.3.1 jvm.options](02-install/2.3-elasticsearch/2.3.1-jvm.options.md)
    * [2.3.2 elasticsearch.yml](02-install/2.3-elasticsearch/2.3.2-elasticsearch.yml.md)
    * [2.3.3 노드의 역할 : master, data, ingest, ml](02-install/2.3-elasticsearch/2.3.3-node-settings.md)
    * [2.3.4 커맨드 라인 설정](02-install/2.3-elasticsearch/2.3.4-cofig-on-start-command.md)
* [3. Elasticsearch 시스템 구조](03-cluster/)
  * [3.1 클러스터 구성](03-cluster/3.1-cluster-settings.md)
  * [3.2 인덱스와 샤드 - Index & Shards](03-cluster/3.2-index-and-shards.md)
  * [3.3 마스터 노드와 데이터 노드 - Master & Data Nodes](03-cluster/3.3-master-and-data-nodes.md)
* [4. Elasticsearch 데이터 처리](04-data/)
  * [4.1 REST API](04-data/4.1-rest-api.md)
  * [4.2 CRUD - 입력, 조회, 수정, 삭제](04-data/4.2-crud.md)
  * [4.3 벌크 API - \_bulk API](04-data/4.3-_bulk.md)
  * [4.4 검색 API - \_search API](04-data/4.4-_search.md)
* [5. 검색과 쿼리 -  Query DSL](05-search/)
  * [5.1 풀 텍스트 쿼리 - Full Text Query](05-search/5.1-query-dsl.md)
  * [5.2 Bool 복합 쿼리 - Bool Query](05-search/5.2-bool.md)
  * [5.3 정확도 - Relevancy](05-search/5.3-relevancy.md)
  * [5.4 Bool : Should](05-search/5.4-keyword.md)
  * [5.5 정확값 쿼리 - Exact Value Query](05-search/5.5-exact-value.md)
  * [5.6 범위 쿼리 - Range Query](05-search/5.6-range.md)
* [6. 데이터 색인과 텍스트 분석](06-text-analysis/)
  * [6.1 역 인덱스 - Inverted Index](06-text-analysis/6.1-indexing-data.md)
  * [6.2 텍스트 분석 - Text Analysis](06-text-analysis/6.2-text-analysis.md)
  * [6.3 애널라이저 - Analyzer](06-text-analysis/6.3-analyzer-1/)
    * [6.3.1 \_analyze API](06-text-analysis/6.3-analyzer-1/6.3-analyzer.md)
    * [6.3.2 Term 쿼리](06-text-analysis/6.3-analyzer-1/6.3.1-term.md)
    * [6.3.3 사용자 정의 애널라이저 - Custom Analyzer](06-text-analysis/6.3-analyzer-1/6.4-custom-analyzer.md)
    * [6.3.4 텀 벡터 - \_termvectors API](06-text-analysis/6.3-analyzer-1/6.4.1-_termvectors-api.md)
  * [6.4 캐릭터 필터 - Character Filter](06-text-analysis/6.4-character-filter/)
    * [6.4.1 HTML Strip](06-text-analysis/6.4-character-filter/6.4.1-html-strip.md)
    * [6.4.2 Mapping](06-text-analysis/6.4-character-filter/6.4.2-mapping.md)
    * [6.4.3 Pattern Replace](06-text-analysis/6.4-character-filter/6.4.3-pattern-replace.md)
  * [6.5 토크나이저 - Tokenizer](06-text-analysis/6.5-tokenizer/)
    * [6.5.1 Standard, Letter, Whitespace](06-text-analysis/6.5-tokenizer/6.5.1-standard-letter-whitespace.md)
    * [6.5.2 UAX URL Email](06-text-analysis/6.5-tokenizer/6.5.2-uax-url-email.md)
    * [6.5.3 Pattern](06-text-analysis/6.5-tokenizer/6.5.3-pattern.md)
    * [6.5.4 Path Hierarchy](06-text-analysis/6.5-tokenizer/6.5.4-path-hierarchy.md)
  * [6.6 토큰 필터 - Token Filter](06-text-analysis/6.6-token-filter/)
    * [6.6.1 Lowercase, Uppercase](06-text-analysis/6.6-token-filter/6.6.1-lowercase-uppercase.md)
    * [6.6.2 Stop](06-text-analysis/6.6-token-filter/6.6.2-stop.md)
    * [6.6.3 Synonym](06-text-analysis/6.6-token-filter/6.6.3-synonym.md)
    * [6.6.4 NGram, Edge NGram, Shingle](06-text-analysis/6.6-token-filter/6.6.4-ngram-edge-ngram-shingle.md)
    * [6.6.5 Unique](06-text-analysis/6.6-token-filter/6.6.5-unique.md)
  * [6.7 형태소 분석 - Stemming](06-text-analysis/6.7-stemming/)
    * [6.7.1 Snowball](06-text-analysis/6.7-stemming/6.7.1-snowball.md)
    * [6.7.2 노리 \(nori\) 한글 형태소 분석기](06-text-analysis/6.7-stemming/6.7.2-nori.md)
* [7. 인덱스 설정과 매핑 - Settings & Mappings](7.-settings-and-mappings/)
  * [7.1 설정 - Settings](7.-settings-and-mappings/7.1-settings.md)
  * [7.2 매핑 - Mappings](7.-settings-and-mappings/7.2-mappings/)
    * [7.2.1 문자열 - text, keyword](7.-settings-and-mappings/7.2-mappings/7.2.1.md)
    * [7.2.2 숫자 - long, double ...](7.-settings-and-mappings/7.2-mappings/7.2.2.md)
    * [7.2.3 날짜 - date](7.-settings-and-mappings/7.2-mappings/7.2.3-date.md)
    * [7.2.4 불리언 - boolean](7.-settings-and-mappings/7.2-mappings/7.2.4-boolean.md)
    * [7.2.5 Object 와 Nested](7.-settings-and-mappings/7.2-mappings/7.2.5-object-nested.md)
    * [7.2.6 위치 정보 - Geo](7.-settings-and-mappings/7.2-mappings/7.2.6-geo.md)
    * [7.2.7 기타 필드 타입 - IP, Range, Binary](7.-settings-and-mappings/7.2-mappings/7.2.7-ip-range-binary.md)
  * [7.3 멀티 \(다중\) 필드 - Multi Field](7.-settings-and-mappings/7.3-multi-field.md)
* [8. 집계 - Aggregations](8.-aggregations/)
  * [8.1 메트릭 - Metrics Aggregations](8.-aggregations/8.1-metrics-aggregations.md)
  * [8.2 버킷 - Bucket Aggregations](8.-aggregations/8.2-bucket-aggregations.md)
  * [8.3 하위 - sub-aggregations](8.-aggregations/8.3-aggregations.md)
  * [8.4 파이프라인 - Pipeline Aggregations](8.-aggregations/8.4-pipeline-aggregations.md)

{% hint style="info" %}
  이 가이드북에 있는 대부분의 내용은 [Elastic 공식 도큐먼트](https://www.elastic.co/guide/index.html)를 참고하여 작성되었습니다.
{% endhint %}

