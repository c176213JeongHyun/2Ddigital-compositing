다음 주 정상 수업, 12월 9일 휴강.
12월 5-9일 특강 

# 3D mesh compositing
* 3d 렌더링 할때는 배경과 합쳐서 렌더링 하는것보다 알파채널이 없는 물체를 따로 렌더링하고 배경과 합치는 것이 더 빠르다
* 퀄리티를 높이려고 하면 합성에서 하는것이 더 편리하다
* **Crpyto matte**: 자동으로 개체마다 다른 색을 배정해서 id채널을 부여하는 node.
  * https://learn.foundry.com/nuke/content/reference_guide/keyer_nodes/cryptomatte.html 
* Maya의 Redering setting에서 AOVs (Render Path)보면 Crypto export 찾을 수 있다. 추가한 후 내보내면 지정한 채널을 가지게 됨.
* 투명물체가 없다면 투명도 계산을 0으로두면 렌더가 더 빨라진다. 무조건 Camera 수치 높여서 좋은 것x
* color correct, grade를 쓰기전 unpremult넣어야.. 그 후에 pemult넣어야 dark edge 안 생긴다. 컬러 조정후 premult 넣으면 조금 깎아지만 손상이 많지는 않다.
* S log에다 lut적용으로 색상 변환하면 중간톤의 컬러가 많아지기 때문에 합성하기에 여유가 생인다.
* 누크 작업 파일은  전부 Linear, Linear 를 lut?으로 바꾸거나 그 반대로 바꿔서 활용가능.
* sharpness 적용 후 lut적용하여 linear로 주면 더 원본의 손상이 적고 안전하게 이미지를 만들 수 있다.
* shuffle로 색별로 채널이 다르게해서 인지가능하게 한다. 쪼갠 shuffle은 merge로 다시 합친다.
* 컬러 Grade 로 밑색이나 새로운 색의 합성이 가능하다.
* direct_specular 으로 빛 (물체가 받는 조명) 만 추출 가능하다.
* maya anold로 뽑아보기..
* 물체의 xzt 축을 따라 채널 추출
* 행렬을 계산하면 이미지가 왜곡된다. 수치를 바꿀때마다 rgb채널의 값이 변함.
* maya rocater=nuke axis
* 값이 회전하면 조명이 바뀌는 것 같은 효과를 줄 수 있다. 영역에 해당하는 부분에 빛 비치게 할수있다. Nomal pass node. 쓰는 이유
* **zedefocus**: focal point로 카메라 초점 조절 가능하다. 
  * https://learn.foundry.com/ko/nuke/content/reference_guide/filter_nodes/zdefocus.html
* **position to point** : 2d이미지를 뒤가 트인 3d 오브젝트로 구현가능
  * https://learn.foundry.com/nuke/content/reference_guide/3d_nodes/positiontopoints.html
* 3d공간에서 유용하게 쓰일 수 있다. 3d데이터가 오면 카메라가 거리를 인식못할 수 있으나 마야에서 카메라 정보를 가져올 수 있다.
* export selection - fbx로 뽑을 수 있으나 좋지는 않다.. 다른 포맷으로 하기
* animation data 또한 들어간상태로 export된다.
* nuke normal map 자료 방대하니까 검색해보기
