# copy cat
  * https://learn.foundry.com/nuke/content/reference_guide/air_nodes/copycat.html
 * input: before images, ground-.. : after images
 *  디블러링과 같은 시퀀스별 효과를 복사한 다음 전체 시퀀스에서 이 효과를 복제하도록 네트워크를 훈련시키는 node. 인공지능 네트워크
 *  반복적으로 학습시켜야 더 좋은 결과 나옴
 *  로토스코핑할떄 참고이미지로 키프레임을 6개 정도 정해두고 이 이미지를 훈련시키면 프레임 사이사이에 인공지능이 학습한 결과를 통해 사이 프레임을 채워넣는다. 
 *  처리결과가 나온 후 어색하게 테두리가 남아서 덜 사라진 것들은 로토로 직접 따주면 된다.
 *  좀더 수월하게 매트 추출 가능.
