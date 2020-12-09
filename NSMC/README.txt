데이터 소스 : https://github.com/e9t/nsmc
참고 : https://wikidocs.net/44249


> 긍/부정 label 기준
긍정(1) : 영화 평점 7~10 점
부정(0) : 영화 평점 1~4 점


> 실행 방법
전체 소스 코드 하단에 sentiment_predict() 함수를 생성하여 활용할 수 있도록 함.

def sentiment_predict(new_sentence):
    new_sentence = okt.morphs(new_sentence, stem=True) # 토큰화
    new_sentence = [word for word in new_sentence if not word in stopwords] # 불용어 제거
    encoded = tokenizer.texts_to_sequences([new_sentence]) # 정수 인코딩
    pad_new = pad_sequences(encoded, maxlen = max_len) # 패딩
    score = float(loaded_model.predict(pad_new)) # 예측
    result = 0
    if(score > 0.5):
        #print("{:.2f}% 확률로 긍정 리뷰입니다.\n".format(score * 100))
        result = 1
    else:
        #print("{:.2f}% 확률로 부정 리뷰입니다.\n".format((1 - score) * 100))
        result = 0
    
    return result



아래 코드에서 private data 의 파일 디렉토리/파일명.csv 을 작성후 실행하게되면 
위의 sentiment_predict() 함수를 불러와 최종적으로 result.csv 파일이 생성된다.
(private data는 utf-8 의 csv파일이고 리뷰 텍스트의 컬럼은 Sentence라 가정)

eval_data = pd.read_csv('./[전처리]ko_data.csv')
eval_data['Predicted'] = 0

for i in range(len(eval_data)):
    Predicted = sentiment_predict(eval_data['Sentence'][i])
    eval_data['Predicted'][i] = Predicted
    
eval_data.to_csv("result.csv", index=False)




