# Tracking and Match-move
## 2D Tracker
 * 2d트래커는 데이터 쫓아가는 것, 3d트래커는 촬영을 추출해내는 것 카메라의 움직임을 추출해내는 것. (3차원 정보)
 * 안쪽에 있는 조절자, 바깥에 있는 조절자. 십자는 물체의 가운데를 잡아주면 같은 패턴의 이미지를 찾도록 하는 중심. 
 * 바깥의 있는 조절자는 카메라의 움직임에 따라 내가 정한 범위까지에서도 움직일 수 있다고 지정하는 기준. 위아래 보다 좌우를 넉넉하게 잡는 것이 도움된다. 
 * 바깥 조절자의 영역이 너무 작거나 너무 크면 트래킹 할때 카메라의 움직임 여부에 따라 못 따라갈 수 있다. 적당한 수준으로 잡아주는 게 중요.
 * 좌측 상단에 있는 레퍼런스 영역을 통해 트래커가 잘 따라가는지 아닌지 알수있다. 뷰어 이미지는 잘 따라가는지 보여주지 않음.
 * 신호등 아이콘을 누르면 트래커가 잘 작동했는지 알수있다 빨간색이면 에러수치가 좀 있는 편이라고 표시하는 것.
 * 점을 따라가는 트래킹- One Point Tracking 삼각형으로 트래킹을 하면 Depth도 표현 가능하다. 점이 두개면 회전하는 물체도 추적가능.
 * 트래커에 넣은 transform으로 위치 정보를 불러와서 트래커랑 동일하게 움직일 수 있다. roto paint를 만들어서 깨끗한 이미지를 만든다던지..
 * export를 이용해서 transform으로 바꿔서 트래커를 내보낼 수 있다. Match move 옵션을 이용해서 따라가게 하면 트래커와 같은 위치를 따라간다.
 * stabilize는 카메라가 덜덜 떨릴다던가 할때 안정시키기 위해 사용.
 * error on track 으로 에러수치가 있는 점들을 판단하고, 맘에 안드는 부분이 있으면 지우고 다시 트래킹을 한다. 뒷부분이 에러 수치가 적으면 역방향 트래킹으로 트래커의 안정도 높일 수 있다.
 * 트래킹 하고자 할때 이미지가 불분명한 곳을 트래킹하면 (픽셀 평균값이 거의 비슷한 경우) 잘 따라가지 못한다. 대비가 확실한 곳을 추적하는게 좋음.
 * T R S - T는 transform, R은 Rotate, S는 Scale을 트래킹한다는 체크박스.
 * 카메라 각도가 많이 변하지 않을때는 One Point Tracking도 유용하게 사용가능하다..
 * frame hold를 써서 레퍼런스 이미지 설정한 후 로토를 따서 덮어씌울 만한 것을 만들고, 트래커를 달아주면 트래킹한 물체를 지울 수 있다.
 * frame hold를 풀면 이동하는 이미지가 되기때문에 다시 그 이미지에 트래킹을 해야함. 그래서 보다 간편하게 한 프레임의 이미지만 따와서 가리는 용도로 사용했다...
 * stabilize: 카메라의 좌우상하 움직임을 막아주는 것으로 카메라 안정성을 주는 역할. 카메라가 위로 치솟으면 다시 아래로 끌어내린다.
 * baked가 안된 노드를 초록색 선으로 연결하면 트래커가 변하는 것에 따라 다른 연결한 노드도 같이 변화한다. bake하면 연결이 끊기고 키가 박힌 노드가 만들어짐.
 * 트래커에서 위치정보를 control으로 잡고 드래그 앤 드롭하면 정보값 그대로 옮길 수 있다.
 * four point tracking을 하면 coner pin node 생성 가능. 직사각형의 끝과 끝 맞추기 가능하다.
 * Two point Tracker 점을 두 개 사용해서 트래킹. 
 * stabilzie 움직이는 물체를 가져다 붙이기보다 안 흔들리도록 왜곡 시켜서 따로 딴 후 회전시키며 가져다 붙이는게 더 자연스럽다.
 * three point Tracking (삼각형)면을 만들어서 트래킹하는 것도 가능하다.
 * 조절자는 control누르고 조절하면 각 점으로 조절해서 크기변경 가능.
 * four point tracking을 하면 coner pin node 생성. 사방에 있는 네 개의 포인트를 조절해서 어떤 방향으로 들어갈지 묘사한다. 
 * 네개의 트랙을 생성해야 사각형에 맞추기, 다른 이미지로 대체 가능해진다. 네개의 점대로 위치를 바꿔준다.
 * coner pin- set to input 트래커 정보로 input들어감 기능 활용해보기!
 * 카메라는 nuke x,nuke studio에서 사용가능. 3차원 공간의 생성이 가능하다.
 * 로토를 만들고 그 부분이 트래킹에 포함되지 않도록 하려면 mask를 달아주면 된다.
 * locate (feature 표시 트래킹 할만한 것의 개수 조절가능. (십자표시의 개수 조절) feature 주황색인 경우 탈락한 것. 
 * Focal range 카메라 렌즈 몇 mm인지 알고있을때 왜곡을 위해 입력.35mm,50mm
 * solve error가 1.~이면 쓸만하게 조정된 것..
  ## 3D Tracker 
   * create 누르면 카메라가 생성되고, 트래커의 위치값 따라간다. 
   * 카메라 트래커 선택한 상태에서 바닥으로 지정할 십자들을 잡아주고 ground play set to selected로 하면 바닥으로 정한 영역을 아래로 카메라가 위로 뜬다.
   * point clould 는 3d상의 공간에서 어디에 feature가 있는지 띄워 위치를 보여준다.
   * scan line render가 없다면 망에서 만드는 씬이나 다름없다. 
   * four point로 하기 어려운 경우 trans form geo로 연결후 이동, 회전해서 맞춰주면 2d이미지를 3d 노드와 연결 가능.
   * 가장 좋은 건 dslr로 줌 렌즈말고 일반 렌즈로 찍는 것
   * 과제: one point Tracking 부터 four point Tracking까지..피사체 교체해오기.
 * **자료링크**
   * https://learn.foundry.com/course/4685/view/practical-compositing-in-nuke-4-merging
 * **Free Effect**
 * 알파 처리 되어있는 무료 효과 소스!
   * https://vfx.productioncrate.com/search/#!/free
  * **How to make 3D Traking and show it**
    * https://learn.foundry.com/course/6714/play/place-objects-in-a-scene-with-cameratracker
