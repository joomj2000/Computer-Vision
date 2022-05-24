# Computer Vision

컴퓨터를 활용하여, 정지 영상 또는 동영상으로부터 의미 있는 정보를 추출하는 방법을 연구하는 학문   
    
컴퓨터 비전의 연구 분야는 크게 여섯 가지로 구분.    
영상에서 대상을 찾는 검출(Detection), 영상을 여러 개의 픽셀 집합으로 나누는 분할(Segmentation), 찾은 대상이 무엇인지 식별하는 인식(Recognition), 유형에 맞게 분리하는 분류(Classification), 영상의 해상도 등 품질을 높이는 개선(Enhancement), 손실된 영상을 복구하는 복원(Restoration) 영역   
<br/>
<br/>
### 목표
* naming :영상을 인식해서 어떤 물체인 지 분류   
* captioning :영상을 보고 문장으로 표현   
* 3D structure :영상을 보고 3 차원 구조 형태를 알아냄   
* actions:영상을 보고 어떤 행동을 취할 수 있을 지 판단   
* matching :영상을 다른 각도에서 봤을 때 같은 부분을 찾음   
<br/>
<br/>   
   
### Semantic Gap(의미적 차이)
컴퓨터는 직관적인 판단이 불가능하여 문제 발생. (컴퓨터는 이미지를 3차원 배열 값으로 인식함)   
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
<br/>
<br/>           
      
### 활용분야
컴퓨터 비전은 얼굴 인식 기술, 의료 이미지 분석, 자율주행차, 보안 감시 등 다양한 영역에서 활용    

* recognition : 얼굴 인식 등 
* 3D reconstruction: 영상 속 물체 의 형상을 3차원 모델로 복원하는 기술    
* vision +language   
* image edition : 저해상도를 고해상도를 바꾸는 등 
* style transfer   
* generating image   
<br/><br/>   

* 제조업 : 완성된 부품의 이미지를 촬영하여 정상 제품 이미지와 비교함-> 결함 확인 (머신비전)
* 리테일 : 쇼핑객 분석하여 제품 배치, 재고 파악, 고객 통계자료 파악-> 위험과 운영비용 줄이고 매장내 트래픽 최적화에 이용
* 자율주행자동차 : 객체를 감지하여 입력받은 시각 정보 처리
* 의료서비스 : mri, x-ray등의 이미지 검사-> 이상징후 감지   
* 콘텐츠 구성 : 이미지, 영상에서 객체를 식별하고 감성을 분석한 데이터를 이용하여 콘텐츠 구성
* 광학문자인식 : 이미지나 영상데이터에서 문자나 숫자정보 추출하여 활용
* 안면 인식: 사람의 얼굴을 인식하고 나아가 나이, 감정, 행동 인식 가능

+ 실제로 컴퓨터 비전을 사용하여 작물을 효율적으로 재배하는 차세대 농업 로봇을 제작하는 회사인 Farmwise존재.
  먹는 작물과 잡초긔 차이를 컴퓨터비전을 통해 식별하는 기술을 사용. 농약을 사용하지 않아도 된다는 장점이 있음.    
  

### 활용분야
컴퓨터의 학습은 딥모델과 빅데이터로 이루어짐

* 딥모델
3x3 크기의 c라는 이미지를 1,0,-1의 값으로 표현한다고 가정할때 C=[1 1 1;1 0 0;1 1 1]으로 표현이 가능함.   
C라는 행렬에 어떠한 값을 곱하였을때만 기준값보다 크게 나오도록 설정한다면 다른 입력값과 구분 가능!(C만 통과되는 층만들기)   
C를 걸러내는 필터는 3x3에서 1,0,-1이 가능하기 떄문에 3^9가됨.   
하나로만 완벽한 필터링이 불가능하기 때문데 이러한 행렬의 곱은 여러개이며 이를 hidden layer이라고 함   
컴퓨터는 입력값에 hidden layer에 해당하는 여러 행렬 곱을 곱하여 원하는 출력값을 얻도록 학습하는 (컴퓨터 입장에서는 수의 배열만 외우고 있는 것이 됨)

       
 <br/>    
 <br/>   
 <br/>       
 <br/>        
        
## Camera    
### Homogeneous Coordinates      
사진(2D)을 원래모습(3D)를 표현      
임의의 0이 아닌 상수 w에 대해 (x, y)를 (wx, wy, w)로 표현하는 것(3차원의 경우에는 (X, Y, Z)를 (X, Y, Z, 1) 나 (wX, wY, wZ, w)로 표현)   
n 차원 점을 n+1 차원으로 만든 좌표계    
<img width="235" alt="image" src="https://user-images.githubusercontent.com/81468129/169705456-f5f6791f-4a28-4622-a401-2683dff4d823.png">   

### Typical Perspective Model
image plane는 원점을 Left top 위치로 설정하기때문에 px,py만큼의 보상 필요   
x->fx/z+px, y->fy/z+py   
   
<img width="320" alt="image" src="https://user-images.githubusercontent.com/81468129/169744705-dce8b126-c205-4877-9cca-b095fac9e79f.png">  

### word coordinate frame   
우리가 사물(물체)의 위치를 표현할 때 기준으로 삼는 좌표계.(문제에 따라서 우리가 임의로 잡아서 사용가능)   
카메라에서의 2차원 점은 camera coordinate로 표현한 것이기 때문에 carmera 위치에 따라 물체의 좌표가 다르게 표현될 수 있음   
따라서 실체물체의 위치를 word coorinate frame 좌표계에서 표현

### word coordinate frame->Camera coordinate
<img width="217" alt="image" src="https://user-images.githubusercontent.com/81468129/169747803-884dae3b-8c69-4a76-b39e-c62b7643229c.png">   
R:얼마나 회전됐는지 나타냄   
t:얼마나 변형됐는지 나타냄   
   
Extrinsic matrix : 회전과 변환정보에 따라World coordinate 에서 정의된 좌표 값을 camera coordinate 좌표값으로 바꾸어주는 역할을 하는 행렬   
Intrinsic matrix : camera coordinate 로 바뀐 점을 카메라의 사영하는 역할을 하는 행렬   

#### Camera Calibration
실제 3차원 좌표와 카메라 사영 좌표는 알고 있기때문에 K,R,t를 찾으면 관계를 알 수 있음





<br/><br/><br/><br/><br/><br/><br/><br/><br/><br/>







<https://bskyvision.com/643>   
<https://velog.io/@good159897/Image-classificationlect-2>   
<https://darkpgmr.tistory.com/78>   
<https://m.blog.naver.com/PostView.naverblogId=sw_maestro&logNo=222082648250&categoryNo=0&proxyReferer=>
