
[영어 감정 분석기]
본 연구에서는 공개되어 있는 FRIENDS 데이터를 8가지 감정(anger, disgust, fear, joy, neutral, non-neutral, sadness, surprise)으로 분류하는 Multi-Class Classification 을 수행하였다.


> 수행 내용
1. 데이터 다운로드 및 로드(아스키코드 값 제거 및 감정 클래스 값 코드화)
   -> anger(0), disgust(1), fear(2), joy(3), neutral(4), non-neutral(5), sadness(6), surprise(7)
2. 데이터 전처리(중복 제거, Null값 제거, 영어와 공백, ' 를 제외한 문자 제거)
3. 데이터 정제
   -> 1)소문자로 통일, 2)축약문 교정, 3)영어, 공백, ?, ! 를 제외한 문자 제거 4)정제 후 Null값 제거
   -> 결과 저장(train_data_set.csv / dev_data_set.csv / test_data_set.csv)
4. 토큰화
5. 불용어(Stopword) 제거
6. 표제어 추출(Lemmatization) / 어간 추출(Stemming)
7. 정수 인코딩
8. 패딩
9. RNN-LSTM 모델 설정 및 학습/평가(모델 학습시, 검증 데이터(dev_data) 사용)


> 개요
1. 전체 소스코드 : [영어 감정분석기]_FRIENDS_RNN_LSTM
2. 모델 평가 및 실행 : [영어 감정분석기]_모델 실행 및 평가


> 실행 방법
'[영어 감정분석기]_모델 실행 및 평가' 코드의 en_data.csv 부분에 평가할 새로운 데이터(Private Data) '디렉토리 및 파일명' 명시(아래 코드 참조)
----------------------------------------------------------------------------
eval_data = pd.read_csv('./en_data.csv', engine='python', encoding='utf-8')
----------------------------------------------------------------------------
최종적으로 result_2019512014_이동환.csv 파일로 결과를 확인할 수 있다.


> 데이터 소스(FRIENDS)
http://doraemon.iis.sinica.edu.tw/emotionlines/download.html


> 참고
https://wikidocs.net/22933



