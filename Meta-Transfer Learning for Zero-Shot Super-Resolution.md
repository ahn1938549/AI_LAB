# GRAPH CONVOLUTIONAL NETWORKS

## Introduction
![02](https://user-images.githubusercontent.com/69898343/158175577-6b092a06-2b30-4b0c-b26f-7fa473fb3979.png)
- 현재까지 연구중인 SISR의 알고리즘은 CNN기반을 사용한 알고리즘이나 이는 내부 정보를 이용하지 않아 외부의존도가 큰 단점이 있다.

![9](https://user-images.githubusercontent.com/69898343/158175908-9502defd-468b-487d-a264-384e8ebe8d35.png)
- ZSSR은 내부의 것을 사용하나 업데이트가 너무 크다. 시간이 너무 많이 걸림 




## Model (MZSR)
- ![1](https://user-images.githubusercontent.com/69898343/158174901-ac307337-3626-469f-8354-ba531352e9b4.png)
- Large scale Learning , Meta - Transfer Learing, Meta Test 3가지의 방법으로 나누어진다.

- Large scale Learning
- ![4](https://user-images.githubusercontent.com/69898343/158171348-b340fdda-cace-4bf7-96cd-3cb3d95bba7d.png)

- Meta - Transfer Learing
- ![3](https://user-images.githubusercontent.com/69898343/158168747-b9629673-228d-4749-a861-53ca011056af.png)

- 전체적인 알고리즘
![5](https://user-images.githubusercontent.com/69898343/158173547-538152a4-e82a-4735-9437-3f548e751315.png)
![6](https://user-images.githubusercontent.com/69898343/158173926-cdfeb416-c1d9-4511-a6cf-32b8909ab662.png)


### 결과
![7](https://user-images.githubusercontent.com/69898343/158174231-04d819e0-327a-4213-b793-8ecabfb28003.png)
10번의 과정만 거쳐도 학습률이 대폭 상승함을 확인 할 수 있다.

![8](https://user-images.githubusercontent.com/69898343/158174641-4c1f2ee4-f499-4afc-9d2b-39451ec0b57c.png)

