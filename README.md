# Course Review Sentiment Analysis
-----

![image](https://user-images.githubusercontent.com/70729822/193005553-42cd5c3b-410e-4185-831b-7c9d64afa24e.png)
![image](https://user-images.githubusercontent.com/70729822/193005600-01aa27bb-8cd9-4317-8abf-9dd0644dd40d.png)

[Ratemyprofessor](https://www.ratemyprofessors.com) 내 수강평을 활용한 강좌 추천 여부를 분류하는 프로젝트



## 프로젝트 배경
----
[지난 프로젝트](https://github.com/9haeng/Course-recommendation-classification/blob/master/%EB%8B%A4%EC%96%91%ED%95%9C%20%EC%A7%80%ED%91%9C%EB%A5%BC%20%ED%99%9C%EC%9A%A9%ED%95%9C%20%EA%B0%95%EC%A2%8C%20%EC%B6%94%EC%B2%9C%20%EC%97%AC%EB%B6%80%20%EB%B6%84%EB%A5%98.ipynb)에서 리뷰 커뮤니티의 지표와 강의 계획서를 활용했을 때 강좌 추천 여부를 얼만큼 잘 분류해 내는지 알아보았습니다.

해당 프로젝트는 데이터내 수치형 feature만을 활용해서 추천여부를 분류해보았다면,

이번 프로젝트에서는 `comments`, 학생들이 교수의 강좌를 듣고 남긴 수강평만을 활용해 해당 강좌의 추천 여부를 분류할 수 있도록 해보겠습니다.

## 프로젝트 목표
----
`comment` feature를 활용한 감성분석 실시, 강좌 추천/ 비추천 분류


## 프로젝트 과정
- 데이터 소개 및 분석 프로세스 수립
    - 데이터 탐색 및 전처리
        -  결측값, 중복값 처리
    - `Target featrue` 생성
        - `Word Cloud`
- 지도 학습 기반의 분류
    - `Baseline` hyper parameter tuning
    - `TFIDF` x `Classifier` Hyper parameter tuning
- 감성 어휘 사전을 이용한 분류
- New input test

----
![image](https://user-images.githubusercontent.com/70729822/193008435-6cd00cbf-2e33-4e21-ab7f-8931547d99ae.png)
![image](https://user-images.githubusercontent.com/70729822/193008525-62d8bcdd-3184-4892-89e7-acbe0cdd3c92.png)
- 데이터 특징 확인 및 필요한 전처리 수행

![image](https://user-images.githubusercontent.com/70729822/193009036-a17b4ddb-579e-4516-80eb-f5e388abe5ec.png)
- Target feature 생성 후 비추천/ 추천 으로 구분된 수강평 `Word Cloud`

![image](https://user-images.githubusercontent.com/70729822/193010307-6406d631-9fbf-4898-96a2-9a870efb65c4.png)
- `Baseline` 평가

![image](https://user-images.githubusercontent.com/70729822/193010493-86bffabc-3dcf-4897-a92b-aca8ae753ea8.png)
-  `TFIDF` x `Classifier` 하이퍼 파라미터 튜닝 평가

![image](https://user-images.githubusercontent.com/70729822/193010703-087c626a-2c5e-4559-8096-078787caa6cd.png)
- `Classifier` 최적의 모델과 `SentiWordNet` 분류 결과 비교

![image](https://user-images.githubusercontent.com/70729822/193010923-2f44db37-7b48-4ef5-bd3b-630dbcb31672.png)
- 함수 생성을 통한 새 input 예측
 
## 결론 및 후기

30개 정도 되는 수치형 데이터들을 분석해 두 라벨을 분류하는 모델보다 `Tf-idf Vectorizer`를 활용해 텍스트 데이터 내에서 각 단어의 중요도를 분석해 두 라벨을 분류하는 것이 상대적으로 더 정확했다는 점을 알 수 있었습니다.

또한 강좌의 추천/ 비추천을 결정짓는 요소 중 수치형 데이터들의 영향력보다 `comment` feature 하나의 영향력이 더 크다는 점을 알 수 있었습니다.

### 아쉬운 점

런타임 제한시간을 더 많이 확보했다면 하이퍼 파라미터 튜닝 과정에서 `Tfidf vectorizer`와 `Classifier`를 동시에 조절하여 더 이상적인 모델을 얻을 수 있었겠지만 로컬 환경의 제한으로 그렇지 못한 점이 아쉽습니다.

