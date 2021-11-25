# A simple neural network module for relational reasoning

## Introduction

- plug-and-play에 빗대어 어디든 사용이 가능하다고 특징지음
- 관계 추론 즉, 데이터들의 연관성에 따른 학습이 어려운 것을 보완하는 새로운 데이터 학습 모델
- ![image](https://user-images.githubusercontent.com/69898343/137295344-6240fea6-c6b7-46fc-8b69-d6ad126f6ee4.png)

- CLEVR
- ![image](https://user-images.githubusercontent.com/69898343/137295422-e3a44b60-630d-49da-8a7a-430ddbcd98ba.png)

- Sort-of-CLEVR
- bAbI
- Dynamic physical systems
- 의 모델들을 사용함으로써 학습 내용을 토대로 소개
- 하나의 학습 function을 공유함으로써 복잡하지 않아 효과적인 것과, 과적합을 예방할 수 있다고 소개


## Model
- ![image](https://user-images.githubusercontent.com/69898343/137293914-4c8668a3-3871-4f3f-b645-b59e72c66601.png)
g(function)은 전체공유로써 학습에 사용
- g(function)은 관계를 계산하는 단순한 함수이기에, 과적합을 예방 할 수 있으며 일반화를 쉽게 하여 모든 변수에 적용 시킬 수 있다.
- 모든 데이터들을 연관지음으로써, 데이터 순서에 의존하지 않아 랜덤시드의 경우에도 잘 돌아가는 것을 확인 할 수 있습니다.

![image](https://user-images.githubusercontent.com/69898343/137295554-c1fcf270-fd25-49bf-981d-10e232c2e2ef.png)
- 와 같이 CNN을 적용하여 나온 4개의 Layer에 비슷한 특징을 갖고 있는 것들을 쌍으로 만들어 이를 특징으로 분류하여 RN모델을 적용시킵니다.
- ![image](https://user-images.githubusercontent.com/69898343/137295953-7dd23b51-31b1-4c88-9a06-7f54edab28a7.png)
- 여기서는 q가 추가되어 나오는데, 이는 질문을 LSTM을 사용하여 그 질문에 대한 특징을 뽑아내는 것을 의미합니다. 


### Results
- ![image](https://user-images.githubusercontent.com/69898343/137296276-1b8546ba-89f2-4dbf-9dc0-fce9f88c2406.png)
- 다음과 같은 결과를 확인 할 수 있으나, 왜 Human을 넣은건지 이해가 가지 않습니다.


### 고찰
- 학습 데이터를 추론하여 새로운 답을 알아내는 것에 사람에 비하여 부족한 상황이였으나, 이를 가능하다고 보여준 논문의 일부.
- ![image](https://user-images.githubusercontent.com/69898343/137297097-97229bfc-fdf8-4073-bec3-310d4f3480c0.png)
- 와 같이 모션캡쳐 부분에서 크게 사용가능하다.
