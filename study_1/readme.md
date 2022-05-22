# Computer Vision

컴퓨터를 활용하여, 정지 영상 또는 동영상으로부터 의미 있는 정보를 추출하는 방법을 연구하는 학문

### 목표
* naming :영상을 인식해서 어떤 물체인 지 분류   
* captioning :영상을 보고 문장으로 표현   
* 3D structure :영상을 보고 3 차원 구조 형태를 알아냄   
* actions:영상을 보고 어떤 행동을 취할 수 있을 지 판단   
* matching :영상을 다른 각도에서 봤을 때 같은 부분을 찾음   

### Semantic Gap(의미적 차이)
컴퓨터가 이미지를 3차원 배열 값으로 인식하여 생기는 문제   
* viewpoint variation : 객체의 단일 인스턴스는 카메라에 의해 시점 바뀔 수 있음      
* Scale variation : 크기 차이(이미지의 크기뿐 아니라 실제 크기도 포함)   
* Deformation : 객체의 형태 변화   
* Occlusion : 객체의 모든 부분이 보지지 않을 수 있음   
* Illumination conditions(changes) : 조명의 영향으로 픽셀 값 변형   
* Background clutter : 주변환경과 섞일 수 있음   
* Intra-class variation : 분류해야할 클래스의 범위가 많은 경우   
* Ambiguity : 모호성   
* Fine-Grained Categories : 같은 집단안에 다른 분류가 존재할 수 있음(ex 강이지 종)   
![image](https://user-images.githubusercontent.com/81468129/169694994-ad748c68-32fe-4848-9f27-8aa16e49c4c5.png)

### 활용분야
* recognition   
* 3D reconstruction   
* vision +language   
* image edition   
* style transfer   
* generating image   


## Camera
### Homogeneous Coordinates
사진(2D)을 원래모습(3D)를 표현
임의의 0이 아닌 상수 w에 대해 (x, y)를 (wx, wy, w)로 표현하는 것(3차원의 경우에는 (X, Y, Z)를 (X, Y, Z, 1) 나 (wX, wY, wZ, w)로 표현)   
n 차원 점을 n+1 차원으로 만든 좌표계   
<img width="235" alt="image" src="https://user-images.githubusercontent.com/81468129/169705456-f5f6791f-4a28-4622-a401-2683dff4d823.png">   

### Typical Perspective Model













<https://bskyvision.com/643>   
<https://velog.io/@good159897/Image-classificationlect-2>   
<https://darkpgmr.tistory.com/78>   
