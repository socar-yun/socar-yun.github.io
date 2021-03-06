---
layout: post
title:  "데이터 분석의 힘 후기 및 정리"
subtitle:   "데이터 분석의 힘 후기 및 정리"
categories: etc
tags: book
comments: true
---

- 회사 그룹장님이 추천해주셔서 읽은 책!
	- 사실 제목이 진부한 느낌이었는데, 의외로 2018년에 8월에 나온 신간!
	- 수식을 사용하지 않는 데이터 분석 입문서
	- 인과 관계 분석에 대해 다룸
- 후기
	- 가볍게 읽기 좋은 내용, 생각보다 알찬 내용! 단 일본어 표현이 조금 생소할 수도 있음
	- 우버 사례는 흥미진진!
- [Yes24 링크](http://www.yes24.com/24/goods/64094963)

<img src="https://www.dropbox.com/s/bsh6rwsgbzony9o/2018-12-10%2023.13.16.jpg?raw=1">

---

### Chapter 1. 데이터의 상관관계는 인과관계가 아니다
- 인과 관계를 입증하기 어려운 이유
    - 1) 다른 요인이 영향을 미쳤을 가능성이 있음
    - 2) 인과 관계가 반대일 가능성이 있음
- 상관 관계가 밝혀져도 그것만으론 인과 관계가 있다고 말할 수 없음
- 잠복 변수 V를 최대한 모은 다음 통계 분석에 의해 V의 영향을 배제해야 함
- 문제는 데이터 수가 아닌 편향(bias)
    - 잘못된 데이터 분석에서 도출된 오차

---

### Chapter 2. 최선의 데이터 분석법, RCT
- 잠재적 결과를 이용한 인과관계 분석(potential outcome approach)
    - 가격 인상 후의 전력 소비량을 $$Y_1$$, 인상 전의 소비량은 $$Y_0$$
    - 개입 효과
        - 트리트먼트 효과
        - $$Y_1$$ - $$Y_0$$
        - 가격 인상(X)이 A의 소비량(Y)에 미친 영향
        - 한 사람에 대해 Y1, Y0 2개가 나타날 수 없음
- 개입 집단(treatment group)과 비교 집단(control group)로 나눔
    - 가정 : 가격 인상이라는 개입(X)이 없을 경우 비교 집단의 평균 소비량과 개입 집단의 평균 소비량은 같다
- 무작위 비교 시행 (RCT)
    - AB Test
    - 핵심 : 소비자를 집단으로 나눌 때는 무작위로(random)
    - 실험 전에 두 집단의 평균값의 차는 0이어야 함(정말 무작위라면!)
    - 원칙
        - 1) 적절하게 집단을 나눈다
        - 2) 집단은 반드시 무작위로 나눈다
        - 3) 집단별로 충분한 표본의 수를 채운다
    - 단점
        - 비용, 시간, 노력이 많이 듬
        - 파급 효과가 없어야 함
            - 개입집단에 대한 개입이 비교집단에는 영향을 주지 않는다
            - 대책
                - 1) 개입집단을 어느 수준으로 설정할지 생각
                - 2) 개입효과 외에 개입의 파급효과도 분석할 수 있도록 실험 설계

---

### Chapter 3. 급격한 변화의 경계선을 찾는 RD 디자인

- 회귀 불연속 설계법(RD 디자인)
    - 키워드 : 불연속, 경계선
    - 의료비 본인부담금은 X, 결꽈인 의료 서비스 이용 수는 Y로 표시할 경우 다음과 같은 가정이 필요
        - 만약 경계선에서 본인부담금(X)이 변화하지 않는다면 의료 서비스 이용자 수(Y)도 점프하지 않는다
- 원칙
    - 1) 경계선을 기준으로 한 가지 요인(X)만 비연속적으로 변화하는 상황을 찾아냄
    - 2) 경계선 부근에서 X 이외의 요인이 비연속적으로 변화하지 않는지 검증
- 단점
    - 가상의 데이터에 기초하므로 데이터로 입증하는 것은 불가능
    - 경계선 부근에 있는 사람에 대한 인과관계만 측정할 수 있는 단점
- 지리적 경계선을 이용한 RD 디자인 사례

---

### Chapter 4. 계단식 변화가 있는 곳엔 집군분석

- 집합군 사이의 관계를 통해 인과관계를 밝혀내는 것
- 원칙
    - 1) 계단식 인센티브를 분석에 이용할 수 있는지 확인
    - 2) 분석하고 싶은 변수(X)만 계단식으로 변함. 다른 변수는 계단의 경계점 부근에서 비연속적으로 변화하지 않음
    - 3) 인센티브가 크게 바뀌는 경계선에서의 데이터 집적을 분석해 개인/기업이 인센티브의 변화에 어떻게 반응했는지 검증
- 강점
    - 가정이 성립하면 경선 부근에서 마치 RCT가 실시된 듯한 상황
    - 결과를 그래프로 보여줌
    - RCT가 불가능할 경우 유용
- 약점
    - 분석에 필요한 가정이 성립할 것이라는 근거를 제시할 수는 있지만 입증할 수는 없음
    - 계단식만 가능해서 유용성이 떨어짐

---

### Chapter 5. 시간의 흐름에 따른 패널 데이터 분석
- 패널 데이터 : 복수의 집단에 대해 복수의 기간에 걸쳐 수집한 데이터
- RCT가 불가능할 경우 사용할 수 있는 자연 실험 기법 중 하나
- 이중 차분법(difference in differences methods)
- 원칙
    - 1) 개입을 전후해서 개입집단과 비교집단 양쪽의 데이터를 입수할 수 있는지 확인
    - 2) 평행 트렌드 가정이 성립하는지 검증
    - 3) 평행 트렌드 가정이 성립할 가능성이 높다면 두 집단의 평균값 추이를 그래프로 그려 개입 효과의 평균값을 측정
- 가정
    - 개입이 일어나지 않았다면 개입집단의 평균값과 비교집단의 평균값은 평행한 추이를 보임
- 가정을 위해 조사해야 할 것
    - 개입 이전의 데이터를 모아 개입집단과 비교집단 사이에 평행 트렌드 가정이 성립하는지 조사
    - 개입집단에만 영향을 미친 다른 사건이나 변수가 없었는지 확인

---

### Chapter 6. 데이터는 어떻게 전략이 되는가
- 우버 사례
    - 수요 곡선을 추정하는 프로젝트
        - 목적지를 입력하고 운전자를 부르면 요금이 표시
        - 이 순간 소비자는 표시된 요금으로 운전자를 부를지 말지 선택 ← 수요 곡선을 추정하기 위한 단서
        - 그 가격을 보고 소비자가 서비스를 이용했는지 기록
        - RCT 사용
        - 운전자 수와 이용자 수를 실시간으로 확인해 수급 핍박 지수(surge generator)를 계산
            - 지수가 클수록 거리에 나와있는 운전자 수에 비해 이용자 수가 많음
    - <img src="https://www.dropbox.com/s/3v5cca7txswlr30/2018-12-10%2022.52.53.jpg?raw=1">
        - 가로 : 수요핍박지수
        - 세로 : 우버 택시를 부르려고 했던 소비자 가운데 스마트폰에 가격이 표시된 이후 실제로 운전자를 부른 소비자의 비율
    - 가격이 오르면 얼마나 줄어드는지 수치로 확인
    - <img src="https://www.dropbox.com/s/uk3tdbkdxr1ngnj/2018-12-10%2022.54.33.jpg?raw=1">

---

### Chapter 7. 불량 분석을 피하기 위한 방법
<img src="https://www.dropbox.com/s/5n0b8mqd33cbr7t/2018-12-10%2022.59.41.jpg?raw=1">

- 분석 결과의 외적 타당성
    - X가 Y에 미친 영향을 과학적으로 분석할 수 있음
    - 여기서 얻은 결과는 분석에 사용된 표본에 적용되는 인과관계
    - 분석 결과 인과관계가 도출되면 내적 타당성이 확보되었다고 함
- 실험으로 얻은 분석 결과를 다른 대상에게도 적용할 수 있느냐를 외적 타당성의 문제라고 부름



