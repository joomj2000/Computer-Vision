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
<img width="156" alt="image" src="https://user-images.githubusercontent.com/81468129/169694202-9dd21c25-d8c3-4df7-be22-a4180997408f.png">   
* Scale variation : 크기 차이(이미지의 크기뿐 아니라 실제 크기도 포함)   
* Deformation : 객체의 형태 변화   
* Occlusion : 객체의 모든 부분이 보지지 않을 수 있음   
* Illumination conditions(changes) : 조명의 영향으로 픽셀 값 변형   
* Background clutter : 주변환경과 섞일 수 있음   
* Intra-class variation : 분류해야할 클래스의 범위가 많은 경우   
* Ambiguity : 모호성   
* Fine-Grained Categories : 같은 집단안에 다른 분류가 존재할 수 있음(고양이 종이 여러개,,)   
![Fine-Grained Categories](https://user-images.githubusercontent.com/81468129/169694116-722e1cb9-557a-426a-8c48-0b4d59e18b4d.jpg)

### 활용분야
* recognition   
* 3D reconstruction   
* vision +language   
* image edition   
* style transfer   
* generating image   
