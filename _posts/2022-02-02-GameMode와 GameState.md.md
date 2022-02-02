---
title: "GameMode와 GameState의 차이점"
excerpt: "GameMode와 GameState의 차이점 정리"
category: unreal
---

### 서버 - 클라이언트 관계에서의 역할
기본적으로 GameMode는 서버에만 존재하는 하나의 인스턴스이며, GameState는 GameMode와 직접적으로 연결되는 복제된 확장이라 할 수 있다. 멀티 플레이어 게임에서는 GameMode에 서버만 알아야 할 정보를 배치하고, GameState는 서버의 GameMode에 엑세스하여 클라이언트에게 필요한 정보를 받아온다.

멀티 플레이 게임을 만드는 경우 UI는 GameState와 PlayerState에서 사용한다.

싱글 플레이 게임을 만드는 경우 GameState를 무시할 수 있다.

예를 들어 포트나이트에서 위젯 간 전환, 마스터 서버 쿼리 등은 GameInstance를 통해 이루어지지만 PVP방에 참가하여 게임을 진행하면 그 모드에 맞는 GameMode와 GameState가 새로 생성된다.


### 그렇다면 GameInstance는

GameInstance는 게임이 레벨 전환, 게임 모드 전환 시에도 유지되는 클래스로 GameMode, PlayerController와 같이 런타임 내에서 제거될 수 있는 인스턴스를 초월하여 데이터를 저장해야 할 때 이 곳에 데이터를 배치한다.


### 공식 문서
**GameMode**

"게임" 이라는 것의 개념은 두 개의 클래스로 나뉩니다.  게임 모드와 게임 스테이트는 게임의 규칙이나 승리 조건같은 것이 포함된 게임의 정의로, 서버에만 존재합니다. 보통은 플레이 도중 바뀌는 데이터는 많이 없어야 하며, 클라이언트에서 알아야 하는 트랜션트(휘발성) 데이터는 반드시 없어야 할 것입니다.

**GameState**

GameState 에는 접속된 플레이어 목록, 점수, 체크 게임에서 말들의 위치, 오픈 월드 게임에서 완료한 퀘스트 목록 등과 같은 것이 포함될 수 있는 게임 상태가 포함됩니다. GameState 는 서버와 모든 클라이언트에 존재하며, 최신 상태 유지를 위해 자유롭게 리플리케이트 가능합니다.

**PlayerState**

인간 플레이어 또는 플레이어인 척 하는 봇과 같은 게임 참여자의 상태를 말합니다. 게임의 일부로써 존재하는 플레이어가 아닌 AI 에는 PlayerState 가 없습니다. PlayerState 에 적합한 예제 데이터라면, 플레이어 이름, 점수, MOBA 게임류에서의 대전상대 레벨, CTF 게임에서 플레이어가 현재 깃발을 운반중인지 여부 등입니다. 모든 플레이어에 대한 PlayerState 는 (PlayerController 와는 달리) 모든 머신에 존재하며, 동기화 상태 유지를 위해 자유로이 리플리케이트 가능합니다.


소스: https://forums.unrealengine.com/t/whats-the-deferent-between-gamestate-and-game-instance/310378

문서: https://docs.unrealengine.com/4.27/en-US/InteractiveExperiences/Framework/
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNjQ0NjUxMjUsLTEzODE2MzU4NzksMT
g1MTk0NDU2NV19
-->