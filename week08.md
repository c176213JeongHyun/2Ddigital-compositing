# ChromaKey Feedback and Tips
* Ibk gizmo는 keylight보다 키가 잘빠지는 장점이 있다.
* IBK= Image based keyer
* 이미지와 그린스크린의 차이를 이용해서 컬러를 추출한다. 이후 Grade로 알파채널의 수치만 조절하면 보다 깔끔하게 딸수 있다. 헤어의 디테일을 굉장히 잘 살리는 노드.
* 추출하고서 알파채널에서 루미너스를 올려서 보면 완벽하게 빠지지 않은 부분을 볼 수 있다. (회색으로 나타남) 
* keylight의 단점 인물에 묻은 초록색을 다른색으로 대체하는데, 이 색이 합성할 또 다른 소스와 톤이 맞지 않을수도 있다. 때문에 바로 키라이트를 쓰기보다 카피에 연결시켜 알파채널만 만들고, 나머지 묻은 색은 huecorrect나 despill 해준다. huecorrct쓸때는 RGB보다는 sup 쓰기. 컨트롤 알트하면 베지어 찍을 수 있다. despilmadness도 간편하게 적용 가능.
* copy 잘 활용할 것. 원본을 최대한 손상없이 고유하게 가지고 있어야 나중에 변형이 편리하다. 
*  soft matte를 사용할 경우 연한 회색이 되면 반투명 상태이므로 clip Black으로 외곽선을 좀 더 파준다.
*  Erode는 hade matte가 soft matte와 합쳤을때 외곽선이 너무 튀지 않도록 깎아주는 역할을 한다. 
* keylight node 여러개 쓰는 이유: control shift로 영역을 조절해가는 keylight, 색상피커로 따주는 keylight, 등등 화면의 위 아래 보며 피사체 각각의 외곽을 잡아간다. 그리고 마지막에 channel merge 사용.
* 알파 채널에 구멍이 나 있을때 무조건 채우지말고 원본을 보며 원래 투명한 곳인지 아닌지 재차 확인하기. 
* GITHUB에서 LUMA Pictures 페이지에 방문하면 gizmo 많이 있다 다운 후 써보기. 마찬가지로 nuke survival tool kit. 
  - https://github.com/CreativeLyons/NukeSurvivalToolkit_publicRelease
  - https://github.com/LumaPictures/LumaNukeGizmos
* Light Wrap 꼭 찾아보기
* shift s, prep 에서 새로운 노드를 띄울 때 자동으로 b인풋에 연결 되도록 설정 바꾸면 좀 더 편하다. (세로 연결)
* *Localization* 외장하드에서 파일을 불러올때 완전히 파일과 자료를 복제해서 불러온다. 훨씬 속도가 빨라짐. limit to (GB) on해서 끄고 킬 수 있다. 

## Grade
* black point (가장 어두운 색) white point (가장 밝다고 생각되는 색) 를 색상 픽해서 ISO를 맞출 수 있다. 
* lift gain gamma 순으로 사용. 
  * lift: 어두운 색 주변을 끌어올리는 역할. 다른 것과 함께 쓰기위해 어두운 정도를 맞춘다.
 
 * Gain: 밝은 영역을 끌어올린다. 

* offset: 전체적으로 밝혀주는 노드.

* Gamma: 밝음과 어두움의 중간 정도= 블랙과 화이트가 아니 중간색이 밝아지거나 어두워짐. 

* black clamp :픽셀의 수치들 조정. (0이 되지 않도록)
* rgb에서 gb가 1이상이라면 그것에 집중하고, 1이상으로 clamps
  
*  constant node가 있으면 빈 백그라운드의 역할 한다. 
*  원래 소스의 크기에 따라 화면 비율을 맞춰준다. 안쓰는 소스의 여분은 과감히 버리자.
*  reformat: center, width 크기를 강제로 맞춤. (resize)
*  transform: filter:cubic 
*  노드의 필터의 종류를 를 맞춰주는 것이 원본이 최대한 덜 손상되는 방법. 
*  :node kon concatenation 
*  ex) transform, reformat의 filter를 cubic으로 맞추면 두번 손상이 아닌 한번 손상으로 맞출 수 있다.
*  *Filtering algorithm*
  * https://learn.foundry.com/nuke/content/comp_environment/transforming_elements/filtering_algorithm_2d.html
* 크기 안맞을때의 방법: reformat, crop, tranxform. 주변에 black outside하면 필요하지 않은 부분 검게 보이도록 할 수 있다.

* gain, gamma말고 lift를 가장 먼저 작업을 해야한다. 채널을 분리해서 작업. r,g,b, 번갈아가며 확인한다. 어둠의 정도 맞춰줄 것.
* 채널에서 1.0이 된 부분은 노출이 심해서 날아간 것. 맞출 수 없으니 대강 작업한다.


## Color Correct






# Traking and Match-move
