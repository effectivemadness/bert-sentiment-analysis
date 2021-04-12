# Sentiment Analysis using BERT

- Data
    - https://github.com/e9t/nsmc

- Usage
    - python bert-sentiment.py

- Preprocess
    - EDA - Exploratory Data Analysis
        - 데이터의 길이, 평균, 분포, 중간값 등 찾아보기
        - outlier 처리 방법 찾기.
        - 문장 구성요소 중 마침표, 물음표, 느낌표 등 "모두가 가지고 있는 특징은 제거하는 방향"
    - 자연어 처리 데이터 전처리
        - Data Clean
            - 필요없는 문자 제거 - 긁어올 때 찌꺼기(HTML tag, etc) 제거 - Beautifulsoup
            - 필요없는 문자 제거 - 영문자는 전부 소문자 처리 or 한글만 남기기 - regex
            - 불용어 처리 - ex. is, am, 감탄사, 조사 etc. - NLTK 불용어 사전 or 자체 제작 불용어 사전

- BERT
    - 양방향을 가지는 마스크 언어 모델.
    - 빈칸 채우기 + 다음문장 예측으로 학습된 모델.
    - 이미 해당 문제로 학습된 모델은 언어에 대한 전반적인 이해를 잘 하고 있고, 이렇게 사전 학습된 지식을 기반으로 다른 문제 해결에 사용될 수 있다.
    - Pretrained model usage : 모델 중간의 특징을 뽑아 활용하는 방식(feature-based), 다른 문제를 해결하기 위한 최소한의 가중치를 추가해 모델을 추가 학습하는 방식(fine-tune)이 있음.
    - BertTokenizer.from_pretrained(), tokenizer.encode_plus() ftn으로 인코딩.
    - bert 출력에 dense 하나 붙여 해당 문장이 긍정인지 부정인지 인식하는 모델 구성

- "텐서플로 2와 머신러닝으로 시작하는 자연어 처리" 책의 [코드](https://github.com/NLP-kr/tensorflow-ml-nlp-tf2)를 기반으로 기록용으로 작성하였습니다.