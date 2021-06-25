### 고려대학교 컴퓨터정보통신대학원 빅데이터융합학과 - 빅데이터와 정보검색
#### Elasticsearch 기반의 문서 검색 및 QA 시스템

##### 실행환경
- Amazon Linux 2 AMI (HVM), SSD Volume Type / t2.medium (+EBS)
- Elasticsearch 7.12.1 / Kibana 7.12.1
- Python 3.x
  * AWS EC2 Instacne는 2021년 6월 25일 이후 중지
 
###### 구현
1) 데이터 셋
- 영어 위키 덤프 파일(https://dumps.wikimedia.org/enwiki) 다운로드
- https://dumps.wikimedia.org/enwiki/20210520/enwiki-20210520-pages-articles-multistream1.xml-p1p41242.bz2
- https://dumps.wikimedia.org/enwiki/20210520/enwiki-20210520-pages-articles-multistream2.xml-p41243p151573.bz2
- https://dumps.wikimedia.org/enwiki/20210520/enwiki-20210520-pages-articles-multistream3.xml-p151574p311329.bz2
- https://dumps.wikimedia.org/enwiki/20210520/enwiki-20210520-pages-articles-multistream4.xml-p311330p558391.bz2
- https://dumps.wikimedia.org/enwiki/20210520/enwiki-20210520-pages-articles-multistream5.xml-p558392p958045.bz2


2) WikiExtractor
- https://github.com/attardi/wikiextractor
* WikiExtractor를 통해 추출하면 디렉토리에 각 100개의 파일(wiki_00~wiki99)이 생성된다.


3) Elasticsearch 구축
- AWS EC2 Instance(t2.medium)
- Elasticsearch 7.12.1 (http://13.209.84.139:9200)
- Kibana 7.12.1 (http://13.209.84.139:5601)
 
 
4) Elasticsearch ↔ Python(Jupyter)
- pip install elasticsearch
 
 
5) 데이터 적재/인덱싱(색인) 및 확인 : 약 54만건
- Python code 참조
- 데이터 확인(Python 및 Kibana Discover, Dev Tools 등)


6) 데이터 검색(BM25)
- 데이터 검색(Python 및 Kibana Discover, Dev Tools 등)


7) 학습 모델(pytorch_model.bin)
- pytorch 기반 HuggingFace의 모델과 학습 방법을 참조해서 제작
  (created by: 서재형, 임희석 (고려대학교 자연어처리 연구실))

8) 


