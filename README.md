# 분양권 전매와 일반 매매의 가격 차이 알아보기

- 국토교통부 공공데이터 API를 사용해서 분양권 전매와 일반 거래 데이터를 선형 회귀해 특정 평수에서 얼만큼의 가격 차이가 있는 지 알아본다.

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
  pip install matplotlib
  pip install pandas
  pip install numpy
  ```

## 실행 방법

- `master`브랜치를 clone한 후 `main.ipynb`를 순서대로 실행시키면 됩니다.
