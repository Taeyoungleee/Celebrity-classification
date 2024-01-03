# Celebrity classification  

## A model that classifies celebrities using celebrity images  

(다양한 CNN 모델을 이용해 연예인 분류 및 성능을 높이기에 주력)  

------------------------------------------------------------------------------------------  
## 데이터  

>  김태희 이미지 약 1300장  
>  김혜수 이미지 약 1300장  
>  마동석 이미지 약 1300장  
>  송중기 이미지 약 1300장
  
-> **train, valid = 8 : 2 비율**    

------------------------------------------------------------------------------------------  
## 이용한 모델  

+ Resnet  
+ EfficientNet  
![캡처3](https://github.com/Taeyoungleee/Celebrity-classification/assets/113446739/3964f0e4-de68-4b6a-addf-473f08321612)  

------------------------------------------------------------------------------------------  
## 방법  

1. 같은 조건에서 다양한 모델을 이용해 성능을 확인하여 적합한 CNN모델 선택  
(성능 그래프의 정확도 및 Loss 함수 추이를 확인함)  
> EfficientNet B1  
    
2. 옵티마이저
> Adam  
  
3. Image 사이즈 변경
> 224 -> 448  
  
4. Batch_size 변경
> 16 ~ 32  

![캡처](https://github.com/Taeyoungleee/Celebrity-classification/assets/113446739/835119ad-8fc3-4596-9285-742422072918)    

------------------------------------------------------------------------------------------  
## 실험  

1. 김태희, 김혜수 분류 및 **Others**(김혜수, 김태희가 아닌 사람) 분류하기  
김태희, 김혜수 이미지 및 다른 인물사진 1300장을 모아 학습 및 검증에 이용

3. 전이학습 이용  
비슷한 스타일의 이미지를 빠르게 재학습하고 이용할 수 있게 전이학습을 이용함  
-> 학습이 더 빠르게 가능해 비슷한 이미지는 모델의 하위층만 학습하여 이용 가능  
-> 데이터의 개수가 적은 경우에도 좋은 방법   

4. 성능 더 올리기  
95%의 정확도를 보이는 모델의 성능을 최대한 더 올려보기  
-> 여러 파라미터 및 옵티마이저 수정  
-> Augmentation 더 다양하게  
-> 분류하는 층을 더 깊게 만들기 **(효과 o)**

------------------------------------------------------------------------------------------  
## 결과 및 인사이트  

+ 간단한 개, 고양이가 아닌 실제 인물로 진행해 더 집중할 수 있었음
+ 파이토치를 실제 프로젝트에 첫 이용
+ A,B 둘다 아니면 C 구조로 모델 구성 성공(다른 방법이 더 있을지 찾아보기)
+ DB에서 데이터를 불러와 학습을 진행해봄

+ 모델을 노트북 캠에 연결하여 실시간으로 이미지를 분류해 내는지 활용
-> **성공적**
