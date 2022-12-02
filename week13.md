# Copy cat
    * https://learn.foundry.com/nuke/content/reference_guide/air_nodes/copycat.html
 * input: before images, ground-.. : after images
 *  디블러링과 같은 시퀀스별 효과를 복사한 다음 전체 시퀀스에서 이 효과를 복제하도록 네트워크를 훈련시키는 node. 인공지능 네트워크
 *  반복적으로 학습시켜야 더 좋은 결과 나옴
 *  로토스코핑할떄 참고이미지로 키가 될 동작이 담신 레이어 6개 정도 정해두고 이 이미지를 훈련시키면 프레임 사이사이에 인공지능이 학습한 결과를 통해 사이 프레임을 채워넣는다. 
 *  처리결과가 나온 후 어색하게 테두리가 남아서 덜 사라진 것들은 로토로 직접 따주면 된다.
 *  좀 더 수월하게 매트 추출 가능.

* Inference
   * https://learn.foundry.com/nuke/content/reference_guide/air_nodes/inference.html
 * copyCat 노드에서 제공 하는 .cat 파일을 적용하여 입력 이미지 전체에서 네트워크에 의해 모델링된 효과를 생성한다.
 * 모델링 효과 불러오기
 
 * Deblur
 * : https://learn.foundry.com/nuke/content/reference_guide/air_nodes/deblur.html
 * **nuke community- cattery** 에서 위와 특정 효과들을 다운 받는게 가능하다!
 * Teco Gan 
    * https://github.com/thunil/TecoGAN
 
 * Copy node: A->B로 복사해준다.
   * missing channal 뜰 때는 from과 to 확인해보기.
   * 채널을 변경, trnasfer랑 비슷한 역할
   * shuffle과도 비슷하지만 내용이 직관적으로 보임. (RGBa->Alpha)
   
   
 * expression
  * https://www.gatimedia.co.uk/expressions
  * translate-rotate (아님 위치등 원하는 값) *100 (숫자)
  * 사칙연산이 가능하다.
  
  * node의 밖에 변경 내용이 바로 보이게 하고 싶다면 노드헤드에 들어가서 [value in]을 써놓으면 된다.
  * Blur: 화질 안좋아보이게 픽셀 딱딱하게 만들수 있음.
  * no op node
  * control rendering point...하나의 노드로 여러개의 노드 조절 가능.
  
  * unreal engine
  * 3D라고 해서 무조건 마야 쓰는 것은 아님.
  * 2D plate도 활용
