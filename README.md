# BigDataProgramming Project Team C
## 리뷰추출 코드 설명
### 1.Review_Collection 폴더에 있는 ipynb의 설명입니다.  
동적 웹페이지를 웹크롤링 하기위해서 구글링을 해보니 Selenium을 사용해야했고  
그에 따라서 크롬드라이버가 필요해 크롬드라이버를 설치했습니다.  
코드는 실행하면 자동으로 웹 브라우저를 열고, 지정된 상품 페이지로 이동하여 리뷰와 별점 정보를 추출합니다.     
사용자가 별도로 조작할 필요 없이 모든 과정이 자동으로 진행됩니다.  
파이썬 버젼, **3.12.10**   
**라이브러리 버젼**
- requests, 2.20.0
- selenium, 4.31.0
- pandas, 2.2.3  
---
## 데이터 전처리 및 토큰분류 코드 설명
### 2.Text_Processing 폴더에 있는 ipynb의 설명입니다.
위 리뷰 추출에서 나온 csv파일을 가지고 전처리를 하는 과정입니다.  
먼저 리뷰에서 의미가 없다고 판단되는 특수문자를 제거 후  
불용어를 없애기 위해서 stopwords-ko.txt라는 텍스트에 정리를 해서 불용어를 제거했습니다.   
이후 형태소 분석으로 동사, 형용사, 명사 등 리뷰에서 실질적으로 의미가 있는 품사의 원형을 가져오려고 노력했습니다.    
파이썬 버젼, **3.12.7**  
**라이브러리 버젼**
- pandas, 2.2.2
- konlpy, 0.6.0
- tqdm, 4.66.5
---
## 데이터의 키워드 추출
### 3.KeyWord 폴더에 있는 ipynb 설명입니다.
2.에서 추출한 토큰을 사용하여서 처음에는 각각의 리뷰에 대해서 키워드를 추출해봤습니다.  
하지만 그렇게하니 리뷰마다의 같은 토큰의 유사도가 다르게 나와서  
모든 토큰을 이어붙인 후 키워드를 추출했습니다.  

**사용한 모델 설명**  
해당링크의 허깅페이스에서 모델을 가져왔습니다.  
https://huggingface.co/sentence-transformers/distiluse-base-multilingual-cased-v1  
KeyBERT에서 사용하는 distiluse-base-multilingual-cased-v1 모델은 다국어(한국어 포함)를 지원하는 경량화된(DistilBERT 기반) 모델입니다.  
이는 문서의 의미를 잘 담아내는 문장 임베딩을 생성하여, 빠르고 효율적인 키워드 추출을 가능하게 합니다.  
파이썬 버젼, **3.11.9**
**라이브러리 버젼**
- pandas, 2.2.3
- keybert, 0.9.0
  
각자의 데스크탑에서 코드를 만들다보니 파이썬의 패치버젼이나 라이브러리 패치버젼이 조금씩은 다를 수 있는데  
마이너 버젼이 같으면 괜찮다고 생각됩니다.
