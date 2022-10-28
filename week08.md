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

## 


# Traking and Match-move
