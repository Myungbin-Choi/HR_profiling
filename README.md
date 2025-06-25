# 고성과자 프로파일링을 통한 인력 운영 최적화 프로젝트
<img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white"> <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=MySQL&logoColor=white">

## 프로젝트 개요
### 분석 목적
생산공장의 고성과자 그룹의 생산성 하락 원인을 파악하고, 운영 최적화를 위한 인사이트 도출
- 높은 생산성과 관련 있는 지표를 확인한다
- 생산성이 하락하는 근무 환경을 파악한다
- 고성과 그룹 내 성과 하락의 공통된 패턴을 파악하고 성과 하락 리스크를 조기 탐지한다


### 활용 데이터
최근 6개월 내 구성원 역량 및 행동 기록 데이터
- 보유 컬럼 : 직원 id, 직원 이름, 직원 소속, 직원 역량지표(건강, 힘, 선량함, 손재주, 개방성, 사회성 등), 슈퍼바이저 id, 슈퍼바이저 역량(선량함, 인지력 등), 이벤트 날짜, 이벤트 유형, 실제 효율성 점수, 기록된 효율성 점수 등 


### 수행 역할
- SQL을 통한 전처리 및 데이터 조회
- pandas, matplotlib, seaborn을 활용한 데이터 분석 및 시각화
- Tableau 활용 대시보드 제작 (https://public.tableau.com/views/HR_17484053894510/3?:language=ko-KR&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
![dashboard]
---

### 진행 프로세스 
![process]


## 주요 결과
1) 직원 개인의 단일 역량 지표와 생산성 간의 상관관계 관찰되지 않아, 직원의 개별 역량보다는 환경적/조직적 요인이나 팀 구성의 맥락이 성과에 더 큰 영향을 줄 수 있다
2) 직원-관리자 간의 나이 차이는 성과에 유의미한 영향을 미친다
3) 고성과자 그룹의 경우, '팀워크' 활동 이후 생산성이 감소되는 경향을 보이며, '희생' 활동 이후 개인의 생산성이 높아지는 경향을 보인다
4) '팀워크', '희생' 이벤트 전후 생산성의 변화가 보이며 이벤트 빈도에 따른 성과 변화 양상 차이 존재하기 때문에 해당 이벤트 전후 피드백 및 보상 체계 수립이 필요하다

#### 1. 퍼널 단계별 이탈률
![funnel](https://github.com/Myungbin-Choi/recruitment-platform-funnel/blob/main/funnel.png)
- **__2단계 개인 이력서 작성 단계의 경우, 이탈률은 낮으나 후속 단계 전환에 지속적인 영향을 미칠 수 있다고 판단하여 해당 단계에 대한 현황 분석 진행__**


#### 2. 주요 이탈구간 현황 파악
![funnel_analytics](https://github.com/Myungbin-Choi/recruitment-platform-funnel/blob/main/funnel_analytics.png)
- 단계별 체류시간이 짧을수록 다음 단계로의 전환이 낮다
- 개인 이력서에 대한 확인 및 수정이 잦은 유저의 이탈률이 낮다
- 관련 공고 불러오기 클릭이 잦을수록 다음 단계로의 전환이 높다 등 가설 검증


#### 3. 유저 여정 분석
![user_journey](https://github.com/Myungbin-Choi/recruitment-platform-funnel/blob/main/user_journey.png)
![user_journey_differences](https://github.com/Myungbin-Choi/recruitment-platform-funnel/blob/main/user_journey_differences.png)
- 이력서를 간단히 작성한 유저일수록 탐색 단계에서 빠르게 이탈하는 경향이 있다
- 즉, 플랫폼 내 이력서 작성 경험이 지원서 작성으로 이어지도록 충분히 동기부여되지 못했다
  

### 대시보드
고성과자들의 성과 추이와 특성을 파악하고, 성과 하락에 주의가 필요한 인물을 식별하기 위해 설계함
![dashboard]
- 주요 구성
  - 성과 등급별 최근 생산성 추이
  - 팀별 생산성 편차 그래프
  - 고성과자 특성 요약 및 분포 확인
  - 성과 상승/하락 기준 주의 필요 인원
  - 고성과자 생산성 추이 시계열 그래프


### 제언
- 교육
  - 저연차 직원 육성 프로그램 강화 : 저성과 그룹의 연령이 가장 낮으며, 이는 경험 부족 및 성장 기회 부재와 연결 가능함. 육성 코칭과 멘토링 시스템 도입 필요
  - 세대 간 거리감 줄이는 리더십 교육 : 저성과 팀은 관리자-직원 간 나이차 크며, 이것이 단순 나이차에서 오는 문제라기보다 세대 간 거리감에서 오는 문제에 기인할 가능성 높음
- 보상
  - 희생 행동이 '가시적 기여'로 반영될 수 있는 평가 지표 설계 : 희생 행동의 경우 단기 생산성 상승하지만, 장기 성과 유지에 부정적이기 때문에 자발적 희생이 반복되지 않도록 롤 분담 관리 필요하며 번아웃 리스크 관리 필요 
---

## directory structure
```bash
├── README.md                     - 프로젝트 요약 설명
├── recruitment_funnel.ipynb      <- 분석 통합 파일 (preview 용)
├── recruitment_funnel.py         <- 분석 통합 파일 (code 공유용)
├── 채용플랫폼_요약포트폴리오.pdf        <- 프로젝트 2page 요약 파일
├── 채용플랫폼_포트폴리오.pdf           <- 프로젝트 보고서 요약 파일
├── images                        <- 주요 이미지 파일
│   ├── abtest.png       
│   ├── funnel.png      
│   ├── funnel_anlalytics.png   
│   └── persona.png            
│   └── process.png           
│   └── user_journey.png        
│   └── user_journey_differences.png           
```
