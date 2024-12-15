# 비디오게임 세일즈 데이터 분석 프로젝트
> 프로젝트 진행 기간 : 2024.09.11~2024.09.16   
> 비디오 게임 순위 차트를 제공하는 vgchart 사이트의 비디오 게임 판매량 데이터를 분석하여 다음분기 게임 장르 및 플랫폼을 제안한 프로젝트입니다.

### 목차
1. 주요분석 내용   
   i.Introduction   
   ii.데이터 준비   
   iii.EDA   
   iV.가설 수립 및 검증   
   V.결론
2. 개인적인 회고
## 1.주요 분석 내용
### 1) Introduction
1. 사전 가정
* 데이터 분석 목표 : 다음분기(2017년도) 게임 기획을 위한 탐색
* 기획 시점 : 2016년 12월 말
* 회사 정보
  * 콘솔게임 개발사
  * 주요 매출은 RPG 게임 IP에서 창출
  * 글로벌 시장에서도 어느정도 인지도 보유
  * 새로운 장르의 게임 개발 역량 보유
2. 문제정의   
  **Key ask** : 다음 분기에 어떤 장르의 게임을 설계해야 하는가?   
    * 지역에 따른 장르 선호도는 다른가?   
    * 연도별 (2014~2016) 게임 트랜드는 어떠한가?   
    * 근 3년간 전 지역에서 Top sales를 보여준 상위 10개 게임은 무엇인가?   

### 2)데이터 준비
1. 분석 대상 데이터
* 최근 추세 확인을 위하여 2014 ~ 2016 기간의 데이터로 한정
* 총 867개의 개별 타이틀 분석
2. 데이터 전처리   
   i.결측값 - 각 컬럼별 결측값 제거 및 대치   
      * `Year`: 271개 제거   
      * `Genre`: 50개 제거   
      * `Publisher` : 58개 “Unknown”으로 변환   
   ii.중복값   
      * Name, Platform 값이 모두 동일한 3개 데이터 제거   
   iii.부정확한 데이터 & 구조   
      * 분석을 위하여 Sales 수치는 Million 단위로 통일
      * 타이틀 당 지역별로 나뉘어진 타이틀은 플랫폼이 동일한 경우 통합   
3. Feature engineering - 기존 컬럼을 활용하여 새로운 컬럼 추가
* `Total` : 전 지역의 판매량을 합한 값
* `Type` : `Platform` 컬럼의 값을 콘솔게임, 휴대용 게임기, PC게임 세가지로 카테고리로 통합

