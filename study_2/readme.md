
## Thin Lens Formula   
pinhole camara에서 pinhole을 통과하는 모든 ray들을 film에 사영.   
   
pinhole 크기가 클수로 많은 rays가 들어와 밝지만 흐리게 보임/ pinhole 크기가 작으면 선명하지만 어둡게 보임.   
pinhole의 크기가 너무 작으면 회절이 발생함    
<img width="500" alt="image" src="https://user-images.githubusercontent.com/81468129/170657889-7335d28a-c17e-4606-a79e-74295c0aadd5.png">   
<img width="500" alt="image" src="https://user-images.githubusercontent.com/81468129/170657942-9fd9adb2-148b-427d-b278-747b1f2055c3.png">   
   
<br/><br/>   
   
## Lens
lens는 빛을 film에 모아주는 역할을 함   
##### 가정
1. lens 의 중심을 지나는 ray 는 휘어지지 않음. 이를 optical axis라고 함.
2. optical axis와 평행한 ray 는 focal point 를 지남.    
<br/>   
   
lens를 통과한 rays는 film 사영됨-> focal point가 film에 정확히 있어야 물체의 상이 잘 맺힘!
* 물체가 가까울 때: 원래 상이 맺히는 거리보다 짧아 뭉쳐보임.   
<img width="400" alt="image" src="https://user-images.githubusercontent.com/81468129/170658657-d737187d-868b-4088-a9bf-bf93afa7d8d4.png">   
* 물체가 멀 때: focal point를 지나고나서 상이 맺혀 뭉쳐보임   
<img width="400" alt="image" src="https://user-images.githubusercontent.com/81468129/170658815-eaa8a988-3e13-41d6-9e72-d30213bb4bee.png">   
* 물체가 적당한 거리일 때: focal point가 film에 딱 맞을때로 선명한 상을 얻을 수 있음.    
<img width="400" alt="image" src="https://user-images.githubusercontent.com/81468129/170658954-8ee56865-0bf6-4431-b9a7-84d842039f76.png">    

## image plane에 상을 잘 맺히게 하기 위한 물체,lens,focal point사이의 관계   
<img width="400" alt="image" src="https://user-images.githubusercontent.com/81468129/170659300-e71c82bc-f14a-4257-ae5c-c6184495c55f.png">   
y'/(D'-f)=y/f -> y'/y=(D'-f)/f   
y'/D'=y/D -> y'/y=D'/D   
위 두 식을 통해 D'/D=(D'-f)/f -> 1/D+1/D'=1/f 를 얻을 수 있음   
이는 물체와 lens까지의 거리, lens와 image plane까지의 거리, lens와 image plane까지의 거리를 통해 image plane에 상이 잘 맺히게 조절할 수 있다는 의미. D,f를 조절하는 것은 쉽지 않기때문에 D'(lens와 image plane사이의 거리)를 조정하여 in-focus인 상태로 맞추게됨.   
<br/><br/>   

## DOF(Depth of Field)    
초점심도는 조리개의 크기를 조절하여 조정.   
조리개 크기가 작으면 ray를 확실하게 나누어 DOF가 증가하지만, 들어오는 빛이 적어저 어두운 이미지가됨.   
조리개 크기가 크면 DOF는 감소하고 밝은 이미지를 얻을 수 있음.   
<br/><br/>   

## FOV(Field of View)   
카메라가 담을 수 있는 각도(화각)을 의미.   
<img width="400" alt="image" src="https://user-images.githubusercontent.com/81468129/170660507-45d56afd-a8e8-41dd-b823-0d23732113f1.png">    
FOV를 크게하려면 f를 증가시킴.(d조절은 힘듦.)      
<br/><br/>   

## Color image   
컬러영상은 R,G,B 3 개의 channel 로 되어있음.   
+) Color filter 1 개로 3가지 색을 표현하는 방법 : 픽셀마다 특정 색만 통과할 수 있는 filter 를 적용해서 색이 없는 부분은 주변 색들의 평균값으로 보간하여 채워줌. image sensor에 R,G,B성분만 담아서 컬러 영상 표현. 
<br/><br/>   

## image filtering   
##### noise   
원본영상보다 흐릿하게 보이거나, 점들이 있는 부분   
* salt and pepper noise : 검은점과 흰점   
* impulse noise : 갑자기 튀는 흰색 점   
* gaussian noise : 정규분호츷 따르는 값이 random하게 더해진 것      
<img width="400" alt="image" src="https://user-images.githubusercontent.com/81468129/170737244-a40444c5-ab9e-45e6-b996-6d44d34ef33f.png">    
<br/>   

noise 영상을 weight average를 이용해 제거함.   
(weight들을 filter(kernel)라고 함.)   
input영상에 대해 Filter를 한칸씩 이동하면서 계산된 값을 해당 filter의 가운데 위치의 값으로 저장.   
<img width="400" alt="image" src="https://user-images.githubusercontent.com/81468129/170737797-2fbe2ffa-029a-4fbf-8b6e-81e5e509a1d5.png">   
이렇게 입력영상에 Filter의 값을 곱해서 더해주는 것을 convolution이라고함.   
   
##### convolution 연산 성질
* commutative: f*g=g*f   
* associative: (f*g)*h=f*(g*h)   
* scalars factor out: kf*g=f*kg=k(f*g)   
* distributes over+: f*(g+h)=f*g+f*h   
<br/><br/>    

## Edge case
edge조건에 따라 convolution을 하는 경우를 지정해 줄 수 있음(-> 출력영상의 크기조절)   
* full : filter의 한 부분이라도 입력영상의 값이 있으면 convolution 연산수행/ 출력영상이 원래 영상보다 커짐.   
* same : filter의 중앙 위치에 입력영상이 잆으면 convolution 연산수행/ 출력영상은 입력영상과 같은 크기 가짐.   
* vaild : filter의 모든 위치에 입력영상의 값이 있을때 convolution 연산 수행/ 출력영상의 크기가 작아짐.   
<br/>    
   
##### 출력영상이 입력영상보다 크거나 같을때 비워져 있는 부분 처리 
* Symm : 바로아래의 값 복사하여 채우기   
* Circular/wrap : 맨아래와 위에 값 복사하여 채우기   
* pad/fill : 0으로 모든 값 채우기(zero padding)   
<br/><br/>   

## Linear filter   
<img width="400" alt="image" src="https://user-images.githubusercontent.com/81468129/170740067-44ffc551-7ec3-4b98-9d84-e0bb1e9c5492.png"><img width="400" alt="image" src="https://user-images.githubusercontent.com/81468129/170740165-ff37b04c-fec2-4a42-86ef-5f80c7b58217.png">    
   
<https://www.youtube.com/watch?v=WeNpd_YEF6I>    
<br/>   
영상을 더 또렷하게 하는 원리는 입력영상에서 부드러운 부분을 뺴주는 방식!(detail한 부분의 가중치를 부여해서 더해주면 더 또렷한 영상을 얻을 수 있음/ 가중치를 더 많이 부여할수록 더욱 뚜렷.)   
<img width="369" alt="image" src="https://user-images.githubusercontent.com/81468129/170740604-cb0196df-fcf2-48c3-9e45-8d068e3b6a6a.png">     
<br/><br/>   

## Box smoothing   
영상이 모자이크된 것처럼 보일떄 해결방법   
<img width="400" alt="image" src="https://user-images.githubusercontent.com/81468129/170744391-312645f9-dfca-40b8-934d-885e43bb3d1e.png">     
per-pixel weights(중앙으로부터 거리에 따라 값이 다른 filter=gaussian filter)을 적용하여 해결    
필터의 시그마(분산)을 조정하여 필터의 크기 조절 가능(보통 필터크기의 1/6정도로 시그마 설정)   
<img width="400" alt="image" src="https://user-images.githubusercontent.com/81468129/170744686-9f5e908d-f79a-47d9-a146-4f15954ff620.png">   
<br/><br/>   

## Median filter   
흰색점이 있는 noise를 해결하기 위해 사용   
중간값을 사용하는 filter. output값들을 정렬하여 그 중 중간값을 선택   
<img width="400" alt="image" src="https://user-images.githubusercontent.com/81468129/170745307-80eded3b-def6-4c7b-b6b6-fcfadde6b11d.png">    












