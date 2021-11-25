# GRAPH CONVOLUTIONAL NETWORKS

## Introduction

-   관계, 상호작용과 같은 추상적인 개념을 다루기에 적합하다.
-   소셜 네트워크, 미디어의 영향, 바이러스 확산 등을 연구하고 모델링 할 때 사용할 수 있다.
-   ![image](https://miro.medium.com/max/700/1*4SOlfgA9FjEpbCbfvYtiWw.png)


## Model
![image](https://miro.medium.com/max/700/1*EzSQP50zcYL0zUyRt5ouDA.png)
![image](https://user-images.githubusercontent.com/69898343/143408144-212ff4be-944d-4f87-bbf7-3b7f3f3babee.png)



### Regularization
- 마지막 Layer에서 drop-out과 l2norm 기법을 사용하여 중복된 hidden layer의 문제를 최소화 하였다.
- ![qwq](https://user-images.githubusercontent.com/69898343/133556690-3dc31dec-53e9-462c-bd8a-968c6a0efd81.png)
다음과 같은 기법으로 r이 Bernoulli분포를 따르기 때문에 0 혹은 1의 값을 갖는다.

### Result
![image](https://user-images.githubusercontent.com/69898343/133557331-e901652b-4e90-4b92-818b-77f6401334ff.png)
- Word2vec에서 사전훈련된 단어를 사용할 경우 정확도가 크게 증간한다.
- rand는 그대로 vector적용 X
- static은 word2vec 사전훈련
- non-static은 사전훈련과 동시에 역전파로 계속 vector들이 수정되어 진 학습모델



### 고찰
- 기존 one-hot 벡터로 단어를 표현하는 점에서 벗어나, 단어들끼리의 결합관계를 생성하고 이에 따라 알고리즘이 자동으로 대안의 단어를 학습할 수 있다는 점이 놀라웠다.
![image](https://user-images.githubusercontent.com/69898343/133558199-b43668c8-2bfa-4805-ba42-fbbd75890255.png)
과 같이 non-static이 조금 더 단어에 대하여 연관성을 잘 표시하는 점을 알 수 있었다.
