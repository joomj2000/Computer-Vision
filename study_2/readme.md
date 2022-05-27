
## Thin Lens Formula   
pinhole camara에서 pinhole을 통과하는 모든 ray들을 film에 사영.   
   
pinhole 크기가 클수로 많은 rays가 들어와 밝지만 흐리게 보임/ pinhole 크기가 작으면 선명하지만 어둡게 보임.   
pinhole의 크기가 너무 작으면 회절이 발생함    
<img width="358" alt="image" src="https://user-images.githubusercontent.com/81468129/170657889-7335d28a-c17e-4606-a79e-74295c0aadd5.png">   
<img width="363" alt="image" src="https://user-images.githubusercontent.com/81468129/170657942-9fd9adb2-148b-427d-b278-747b1f2055c3.png">   
   
<br/><br/>   
   
## Lens
lens는 빛을 film에 모아주는 역할을 함   
##### 가정
1. lens 의 중심을 지나는 ray 는 휘어지지 않음. 이를 optical axis라고 함.
2. optical axis와 평행한 ray 는 focal point 를 지남.    
<br/>   
   
lens를 통과한 rays는 film 사영됨-> focal point가 film에 정확히 있어야 물체의 상이 잘 맺힘!
* 물체가 가까울 때: 원래 상이 맺히는 거리보다 짧아 뭉쳐보임.   
<img width="349" alt="image" src="https://user-images.githubusercontent.com/81468129/170658657-d737187d-868b-4088-a9bf-bf93afa7d8d4.png">   
* 물체가 멀 때: focal point를 지나고나서 상이 맺혀 뭉쳐보임   
<img width="347" alt="image" src="https://user-images.githubusercontent.com/81468129/170658815-eaa8a988-3e13-41d6-9e72-d30213bb4bee.png">   
* 물체가 적당한 거리일 때: focal point가 film에 딱 맞을때로 선명한 상을 얻을 수 있음.    
<img width="330" alt="image" src="https://user-images.githubusercontent.com/81468129/170658954-8ee56865-0bf6-4431-b9a7-84d842039f76.png">    

## image plane에 상을 잘 맺히게 하기 위한 물체,lens,focal point사이의 관계   
<img width="231" alt="image" src="https://user-images.githubusercontent.com/81468129/170659300-e71c82bc-f14a-4257-ae5c-c6184495c55f.png">   
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
<img width="238" alt="image" src="https://user-images.githubusercontent.com/81468129/170660507-45d56afd-a8e8-41dd-b823-0d23732113f1.png">    
FOV를 크게하려면 f를 증가시킴.(d조절은 힘듦.)      
<br/><br/>   

## Color image   
컬러영상은 R,G,B 3 개의 channel 로 되어있음.   
+) Color filter 1 개로 3가지 색을 표현하는 방법 : 픽셀마다 특정 색만 통과할 수 있는 filter 를 적용해서 색이 없는 부분은 주변 색들의 평균값으로 보간하여 채워줌. image sensor에 R,G,B성분만 담아서 컬러 영상 표현. 


