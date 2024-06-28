# 앨라스틱 스택

엘라스틱 스택 자체에는 웹 데이터를 직접 수집하는 방법은 없는 것 같다.

##

Elasticsearch, Beats, Logstash, Kibana


주요 구성 요소

    Elasticsearch: 검색 엔진 및 데이터 저장소. 구조화된, 반구조화된, 비구조화된 데이터를 빠르게 저장하고 검색할 수 있습니다.
    
    Beats : 다양한 시스템과 장치에서 로그 및 메트릭과 같은 데이터를 실시간으로 수집하고 Elasticsearch로 전송하는 경량 데이터 수집기입니다. Go 언어

    Logstash: 데이터 수집 파이프라인. 다양한 소스(예: 로그 파일, 시스템 메트릭, API)로부터 데이터를 수집하고, 파싱, 필터링, 변환한 후 Elasticsearch로 전송합니다.

    Kibana: 데이터 시각화 도구. Elasticsearch에 저장된 데이터를 다양한 차트, 그래프, 대시보드 등으로 시각화하여 분석할 수 있도록 합니다.

## Beats

로그 수집기?

## Logstash

**파일에서** input -> filter -> output 파이프라인을 사용해서 데이터 수집
