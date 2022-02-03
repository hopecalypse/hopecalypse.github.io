---
title: "PlayerCharacter와 PlayerController 용법"
excerpt: "PlayerCharacter와 PlayerController 용법 정리"
category: unreal
---

언리얼에 입문하며 가장 힘든 점은 자체적으로 정의된 클래스가 너무 많아서 이미 구조가 잡혀있는 상태로 프로젝트를 시작하게 되기 때문에 어떤 상황에 어떤 클래스를 써야 하는지가 햇갈리기 때문이다. 언리얼과 달리 유니티에서는 아주 처음부터 내가 구조를 잡아나가야 했었다.

<br/>

그 중 언리얼의 가장 기초가 되는 PlayerCharacter, PlayerController가 어떤 기능을 담당하는지, 어떻게 구현해야 좋을지 막막했는데 검색 중 좋은 글을 찾아 정리한다.

<br/>

플레이어 컨트롤러는 직접적으로 플레이어 캐릭터와 연결되지 않는다. 두 클래스는 독립적으로 존재하며, 플레이어 컨트롤러는 알아서 캐릭터의 위에서 동작한다. 폰이나 캐릭터는 지금 어떤 컨트롤러에게 입력을 전달받는지 알 필요가 없다. 단지 입력값대로 움직이기만 하는 Pawn일 뿐이다.

따라서 플레이어 컨트롤러를 사용할 때 입력을 받는 함수나 폰을 따로 지정해줄 필요가 없으며, Raw하게 입력을 꺼버리거나 다른 플레이어와 구별되는 데이터를 저장해야 할 때 사용하면 좋을 것 같다.


<br/><br/><br/>
참고: https://forums.unrealengine.com/t/how-to-use-the-player-controller-class-in-c/370128
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3OTE1OTE2NTMsMTgzODg2Nzk2MF19
-->