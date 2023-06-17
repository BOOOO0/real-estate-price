# 분양권 전매와 일반 매매의 가격 차이 알아보기

- 국토교통부 공공데이터 API를 사용해서 분양권 전매와 일반 거래 데이터를 선형 회귀해 특정 평수의 서울시 전체 평균 가격이 얼만큼 차이가 있는 지 알아본다.

## 공공데이터 신청

- 공공데이터 API의 신청이 필요합니다. 아래 두개의 API를 신청하고 발급받은 자신의 인코딩 키, 디코딩 키를 사용해야 합니다.

- [분양권 전매 신고 자료](https://www.data.go.kr/tcs/dss/selectApiDataDetailView.do?publicDataPk=15056782)
- [아파트 매매 실거래 상세 자료](https://www.data.go.kr/tcs/dss/selectApiDataDetailView.do?publicDataPk=15057511)

## Service Key 저장

- `api_keys.py` 파일을 생성해 인코딩 키와 디코딩 키를 각각 `encoding_key`, `decoding_key`로 저장합니다.

- 저장된 키는 `main.ipynb`에서 호출됩니다.

## 패키지 설치

- ```
  pip install jupyter
  pip install ipykernel
  pip install scikit-learn
  pip install beautifulsoup4
  pip install matplotlib
  pip install pandas
  pip install numpy
  ```

## 실행 방법

- `master`브랜치를 clone한 후 `main.ipynb`를 `visual studio code`와 같은 에디터를 사용하거나 [jupyter.org](https://jupyter.org/try-jupyter/retro/)에서 View -> Open Files에 `main.ipynb`를 업로드한 후 첫번째 셀 부터 순서대로 실행시키면 됩니다.

## 주의 사항

- GUI 개념이 없는 wsl2 우분투와 같은 환경에서는 실행이 되지 않을 수 있습니다.

- 이 경우 `visual studio code`의 wsl 관련 extension을 통해 우분투를 서버로 한 상태에서 `visual studio code`의 실행이 가능하다면 `visual studio code`에서 실행이 가능합니다.

- 공공데이터의 일일 트래픽 제한이 있고 이 프로젝트는 호출하는 횟수에 대해 크게 고려하지 않았기 때문에 호출 부분을 여러 번 실행시킨다면 금방 제한이 될 수 있습니다.

- API마다 방식이 다르기 때문에 url에 명시한 인코딩 키, 디코딩 키 부분이 다를 수 있습니다.

- 일반적으로 API 승인은 1시간 정도 후 되지만 하루가 지나도 API의 승인이 되지 않는 경우가 있습니다. 문의를 통해 해결 가능합니다.

## 결과 분석

- 분양권 전매의 평균가가 일반 매매보다 확실히 높게 형성되어 있으며 평수가 커질 수록 그 차이가 커지는 것을 확인할 수 있습니다.
