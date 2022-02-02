---
title: "GameMode와 GameState의 차이점"
excerpt: "GameMode와 GameState의 차이점 정리"
category: unreal
---

### 서버 - 클라이언트 관계에서의 역할
기본적으로 GameMode는 서버에만 존재하는 하나의 인스턴스이며, GameState는 GameMode와 직접적으로 연결되는 복제된 확장이라 할 수 있다. 멀티 플레이어 게임에서는 GameMode에 서버만 알아야 할 정보를 배치하고, GameState는 서버의 GameMode에 엑세스하여 클라이언트에게 필요한 정보를 받아온다.

멀티 플레이 게임을 만드는 경우 UI는 GameState와 PlayerState에서 사용한다.

싱글 플레이 게임을 만드는 경우 GameState를 무시할 수 있다.




### 그렇다면 GameInstance는

GameInstance는 게임이 레벨 전환, 게임 모드 전환 시에도 유지되는 클래스로 GameMode, PlayerController와 같이 런타임 내에서 제거될 수 있는 인스턴스를 초월하여 데이터를 저장해야 할 때 이 곳에 데이터를 배치한다.


소스: https://forums.unrealengine.com/t/whats-the-deferent-between-gamestate-and-game-instance/310378
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM3MzM1MTIyMywxODUxOTQ0NTY1XX0=
-->