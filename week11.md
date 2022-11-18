# Tracking and How to use 3D node
## Assignment Feedback
* 트래킹을 하고 새로운 소스를 합성할때는 움직이는 영상에 멈춰있는 소스를 붙이는 것이므로 모션블러를 넣으면 현실감 있는 표현 가능. 
* Node: Motion Blur
* transform node를 사용하면 소스의 복제가 쉽다. 노드를 다 처리한 후 끝에 transform을 붙여주면 복붙 역할함
* Node가 비슷한 색인 것은 비슷한 연산을 하기때문에 정해져있는 색. 같은 색의 노드끼리 정렬하면 원본의 손실이 적다. 특히 필터가 들어가는 transform은 같이 정렬하면 좋다.
  * 필터가 한번만 가해지는 것으로 인해 손실이 적어짐.
* 트래커의 위치를 잡을 때는 최대한 확대해서 픽셀을 집어내면 정확도의 차이가 달라짐. 최대한 정확한 곳에 찍어주는 것이 좋다.
* 로토는 가능하면 많이 확대해서 본 후 곡선으로 만들기. Z와 페더(E키)면 더 부드럽게 가능...
* merge에서 바운딩 박스가 늘어날 때 union이 아니라 Bbox를 b로 설정해주면 넘어가는 픽셀없이 잘라낼 수 있다. 쓸데없는 연산 과정 줄이기 가능. 
* shuffle node는 웬만하면 input 바로 앞에 붙이는 것이 좋다. rgb채널의 조작을 하는 노드이므로 다른 노드보다 우선시해서 앞에 붙여주자.
* Alt+2?e? 를 누르면 Tracker-Transform 연결을 끊을 수 있다. 만약 실수로 끊었을 때의 상황을 방지하여 node의 node란에 표시를 해두거나 뭔가 기입해두면 좋다.
* Roto도 웬만하면 Input 바로 앞에 두기. 알파라는 채널을 두는 것이므로 변형이 적은 위치일수록 좋다.
* 4-point Tracking을 하고서 다른 사각형을 삽입할 때 Edge blur를 넣어주면 보다 자연스럽게 보일 수 있다.
* Frame hold를 써서 한 프레임을 고정하는 것도 좋지만, 더 좋은 것은 알파 채널이 따져있는 png나 jpg가 있는 것..(노드가 붙을수록 원본은 손실)
* 영상이 너무 흔들려서 모션 블러로 영상이 심하게 번지면 손트래킹을 잡는 수 밖에..웬만하면 흔들림이 없거나 덜한 좋은 플레이트를 구하자
* 3d는 나중에 붙여주는 것이므로 노드들의 밑으로 정리해서 보내면 좋다. 
* 똑같은 플레이트를 불러올때 씬이 쌓이면 렌더링 할때 시간이 많이 걸리므로 포스테지 스탬프도 많이 사용한다. read node와 비슷하게 생김.
  * **Postage Stamp:** https://learn.foundry.com/nuke/content/reference_guide/other_nodes/postagestamp.html
* A B 구역 구분을 확실히 해줄 것! 
* 연산에 있어서 영상의 크기가 다른 파일들을 불러올 땐 bounding box 꼭 조절할 것!!
  * **Bounding Box (B Box)**: https://learn.foundry.com/nuke/content/comp_environment/reformatting_elements/adjusting_bbox.html

* **How to use Tracking Mark**
* Coner Pin Node 두개 사용하기. 먼저 트래킹 마크에 맞추고, 그 밖의 영역까지 확장한다.
1. Coner Pin 의 From head로 와서 set to input을 누르면 해상도가 늘어나며 원본과 해상도 크기를 맞춰준다. copy from을 누르면 원본의 코너로 자동으로 포인트를 맞춰준다.
2. 그 이후 from은 건드릴 필요 없고 확장해서 to를 삽입하려는 스크린에 맞춘다. 
3. 애니메이션을 넣은 coner pin node는 그대로 두고 그 위의 해상도를 맞춘 Node의 to를 스크린 크기에 맞춰 변경한다.
* *from은 input의 해상도를 말한다.*
  * Coner Pin : https://learn.foundry.com/nuke/content/reference_guide/transform_nodes/cornerpin2d.html
* 트래킹한 4트랙을 잡고서 tracking to stabilize node를 만들면 거의 피사체가 움직이지 않는다. 이 노드를 복붙하고 합성하려는 소스의 match move node 사이에 연결해준다. 그리고 invert를 켜주면 다시 원본 영상처럼 바뀐다.
* 3D mesh를 불러올땐 <u> Read Geo node </u> 사용.
* Read Geo: https://learn.foundry.com/nuke/11.1/content/reference_guide/3d_nodes/readgeo.html


