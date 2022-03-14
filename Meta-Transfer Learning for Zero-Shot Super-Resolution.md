# GRAPH CONVOLUTIONAL NETWORKS

## Introduction
- DownSampling : LR - HR 페어를 만들기 위한 기초적인 절차이며 이는 대부분 Bicubic이라는 알고리즘을 사용한다. 또한 이 과정을 통하여 하나의 그림으로 하나의 Train-set을 만든다.

![일괄편집_일괄편집_02](https://user-images.githubusercontent.com/69898343/158183039-da632746-aa7e-49d2-98bf-900d24447aa7.png)
![일괄편집_일괄편집_10](https://user-images.githubusercontent.com/69898343/158183058-5576e5fb-2313-4e18-bccb-7d5ebbaa3514.png)

- 현재까지 연구중인 Single Image Super Resolution 의 알고리즘은 CNN기반을 사용한 알고리즘이나 
- 이는 학습에 따른 파라미터의 변화가 너무 크며 이미지내의 특이점보다 학습하면서 바뀐 파라미터들에 의존한다는 점에 그림의 특징을 잘 잡아내지 못한다는 단점이 있다. 

![일괄편집_일괄편집_9](https://user-images.githubusercontent.com/69898343/158183107-221b4322-975b-4bfa-8b1d-d0fd58afca8f.png)

- Zero Shot Super Resolution은 이미지 하나의 특정 값을 CNN을 통하여 특징들을 통하여 업데이트 하나 하나의 이미지를 
- 다양한 CNN계층으로 나누기에 시간이 너무 많이 걸리며 연산량이 크다는 단점이 있다. 

- 이에 대한 절충안으로 Meta-Transfer Learning for Zero-Shot Super-Resolution의 Meta-Transfer-Zero Learing 알고리즘을 제시한다.

## Model (MZSR)
![일괄편집_일괄편집_1](https://user-images.githubusercontent.com/69898343/158183036-3f14dde5-c685-4fb3-99fb-dcbb57f5d7c1.png)
- Large scale Learning , Meta - Transfer Learing, Meta Test 3가지의 방법으로 나누어진다.

- Large scale Learning
![4](https://user-images.githubusercontent.com/69898343/158183477-0935a786-04e4-4865-95df-69001d9c89d3.png)
- 다양한 이미지에서 공통적으로 사용되는 인자들을 학습합니다. 이 과정에서 LR을 만듦과 동시에 LR, HR 짝을 생성하며 그 값들을 Error값의 차이와 계산하여 Loss를 최소화 하도록 합니다.

- Meta - Transfer Learing
![일괄편집_일괄편집_3](https://user-images.githubusercontent.com/69898343/158183062-3761ad15-90f8-4e7d-a4c9-cb9361ce50bb.png)
- 학습을 위한 학습이라고도 불리며, 각 커널들에 따른 가중치를 각각 계산하여 추후에 학습에 대한 변화량이 적절하게 이루어지도록 하는 학습입니다.
- 각 task에 맞는 weight값들을 따로 구현해두어 loss의 방향성에 대한 최적화가 빠른 편입니다. 또한 이 연산을 위하여 Covariance Matrix를 사용합니다.
- 전반적인 optimization을 통하여 Test에 대한 에러를 최소화 하는 방향으로 weight값들을 변경시켜 나갑니다.

- Meta Test
- Zero-shot super learning의 방식과 동일하게 하나의 그림으로만 학습하는 과정을 볼 수 있으나 이는 전에 Large scale Learing과 Meta 러닝을 통하여 데이터셋에 대하여 최적화가 되어있으며 weight값 또한 각 그림에 맞게 최적화되는 것을 볼 수 있습니다.

- 전체적인 알고리즘
![일괄편집_일괄편집_5](https://user-images.githubusercontent.com/69898343/158183074-f520a3ae-816c-4c90-ac2c-7025b6e4e60b.png)
![일괄편집_일괄편집_6](https://user-images.githubusercontent.com/69898343/158183081-1f3429b4-7e65-4cbd-adec-1d3cf8a8a58d.png)


### 결과
![일괄편집_일괄편집_7](https://user-images.githubusercontent.com/69898343/158183083-e83f1426-f4ab-425a-9ab7-b47b19bbdf0d.png)
- 10번의 과정만 거쳐도 학습률이 대폭 상승함을 확인 할 수 점을 확인 할 수 있으며, 학습된 모델과 비슷한 성능을 내는 효과를 확인 할 수 있습니다.
- 1 - 10번의 업데이트만으로도 유사한 성능을 확인 할 수 있습니다.

![일괄편집_일괄편집_8](https://user-images.githubusercontent.com/69898343/158183089-bf9152c9-8d8f-456c-a348-ad8c4515f163.png)

