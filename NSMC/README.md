
[한국어 감정 분석기]
본 연구에서는 공개되어 있는 네이버 영화 리뷰 데이터를 긍정과 부정으로 분류하는 Binary Classification 을 수행하였다.


> 전체 소스코드 : [한국어 감정분석기]_네이버 영화리뷰_RNN_LSTM.ipynb


> 실행 방법
소스코드 순서대로 실행.
학습 모델 생성 후, Private Data로의 평가는 하단의 'Private Data 평가 실행' 아래 코드 실행
1) 함수(sentiment_predict(new_sentence)) 실행

ko_data.csv 부분에 평가할 새로운 데이터(Private Data) '디렉토리 및 파일명' 명시(아래 코드 참조)
----------------------------------------------------------------------------
eval_data = pd.read_csv('./ko_data.csv', engine='python', encoding='utf-8')
----------------------------------------------------------------------------
최종적으로 result_2019512014_이동환.csv 파일로 결과를 확인할 수 있다.


> 수행 내용
1. 데이터 다운로드 및 로드
2. 데이터 전처리
   -> 1)중복 제거, 2)Null값 제거, 3)한국어와 공백을 제외한 문자 제거 4)전처리 후 Null값 제거 5)결과 저장
   => train_data_set.csv / test_data_set.csv
3. 데이터 정제
   -> 1)반복 문자열 교정, 2)띄어쓰기 교정, 3)맞춤법 교정, 4)결과 저장
   => train_last_data.csv / test_last_data.csv
4. 토큰화
5. 불용어(Stopword) 제거
6. 정수 인코딩
7. 패딩
8. RNN-LSTM 모델 설정 및 학습/평가(모델 학습시, 학습 데이터의 20%를 검증용으로 사용)


> 데이터 소스(네이버 영화 리뷰)
https://github.com/e9t/nsmc


> 참고
https://wikidocs.net/44249

