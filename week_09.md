# Midterm feedback
* **소스 탐색할때 유의사항**
 * 3d는 크로마키 색이 잘 안빠져 테두리가 검게 나올수 있으니 렌더할때 알파 채널을 뒤에 두고 렌더링 할 것 고려해보기.
 * 이미 알파가 따져있고 그곳에 다른 초록색을 덮어 씌워져있는 소스는 활용하기에 별로 좋지 못하다. 다른 plate찾아보기. 방법은 로토스코핑 뿐...
 * **Node- time offset**
   * 프레임의 시작을 지정하여 설정 가능하다.
 * 좋은 소스 사이트
 * **Action VFX**
   * https://www.actionvfx.com/?gclid=EAIaIQobChMIi7XUy7ST-wIVhzMqCh2lFgPaEAAYASAAEgJdhfD_BwE
* 알파를 빼는 방법
  * 흑백채널은 알파로 바꿀 수 있다. rgb 채널을 번갈아 보며 가장 배경과 대비가 강한 채널을 찾은 후 red,green,blue의 채널을 차단하면 된다.
  * rgb 데이터를 바꾸는 것으로 크로마키가 아니더라도 알파추출이 가능하다!!
  * 그다음에는 despill로 묻은 색을 빼주면 완성~
* **리얼리즘을 위한 텍스쳐링 소스**
  * https://surfaceimperfections.com/
