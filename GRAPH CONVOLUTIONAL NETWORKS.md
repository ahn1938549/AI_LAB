# GRAPH CONVOLUTIONAL NETWORKS

## Introduction

-   관계, 상호작용과 같은 추상적인 개념을 다루기에 적합하다.
-   소셜 네트워크, 미디어의 영향, 바이러스 확산 등을 연구하고 모델링 할 때 사용할 수 있다.
-   ![image](https://miro.medium.com/max/700/1*4SOlfgA9FjEpbCbfvYtiWw.png)


## Model
![image](https://miro.medium.com/max/700/1*EzSQP50zcYL0zUyRt5ouDA.png)

![image](https://blog.kakaocdn.net/dn/bQ5Em5/btqAU6Lc3YS/f1GIUGiCugVdgGiwIeY9OK/img.png)

![image](https://user-images.githubusercontent.com/69898343/143408144-212ff4be-944d-4f87-bbf7-3b7f3f3babee.png)

- a는 인접 노드들의 정보를 나타낸 Matrix
- D는 a의 정보값에 대한 평균 또한 후에 한 번 더 곱함으로써, 가중치를 곱하여 가중 평균을 구할 수 있도록 한다. 
    이로써, 낮은 차수에 조금 더 큰 영향력 높은 차수에 영향력을 줄인다. (Gradient Vainshing같은 현상을 예방한다.)
- H는 각 노드의 Feature Matrix를 나타낸다.
- W는 각 노드들의 가중치와 bias를 포함한 정보이다.(Convolution Filter부분)
- 모두 지수에 -1/2가 붙어있는 것은 정규화를 두번 하기 때문이다.

![image](https://user-images.githubusercontent.com/69898343/143410369-30252715-c532-48ff-846b-f12904d963c1.png)
- 그 후 그 식을 1차로 Relu, 2차로 Softmax를 거쳐 라벨에 맞게 결과값을 도출한다. (2차원의 경우)

## Readout

- CNN에서 Fully-connected layer 후에 Softmax와 같은 것을 GCN에서는 Readout이라고 지칭한다.
- 노드들의 순서를 불러오는 점에 따라 값이 다른 문제가 생기는 것을 방지한다.
- 이를 MLP 함수를 통하여 보완한다.



### DataSet
![image](https://baekyeongmin.github.io/images/GCN/dataset.png)
- Citation network : 총 20개의 label을 결과로 학습, 논문 인용횟수와 관련 논문들의 연관성을 나타낸 dataset
- Nell : Never Ending Language Learning 으로 스포츠팀, 회사 등 연관성이 있는 기사들을 분류하고 나타낸 dataset

![image](https://baekyeongmin.github.io/images/GCN/result.png)


