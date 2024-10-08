# 퐁당 PONGDANG
웹소켓 통신을 이용한 실시간 게임
<br/><br/>

## 🚩 목차
1. [기획 배경](#기획-배경-httpsgithubcommyddoddomimini_heaven_2nd)
2. [프로젝트 소개](#프로젝트-소개)
3. [기술 스택](#기술-스택)
4. [게임 구조](#게임-구조)
5. [역할 분담](#역할-분담)
<br/><br/>

## 기획 배경 (https://github.com/myDdoDdomi/mini_heaven_2nd)

###  목적
- SW 알고리즘 학습에 대한 효율적인 학습 방안을 찾고자 실무적인 프로젝트를 진행하기 위해 기획되었습니다.
- Python의 문법 구조, 특히 객체지향 프로그래밍(Class) 등을 실제 프로젝트에서 활용하여 이해를 높이고자 했습니다.
- Pygame을 통해 시각적인 이해와 실시간 상호작용 및 이벤트 처리를 경험하며 알고리즘 학습에 도움이 되도록 했습니다.
- WebSocket을 활용하여 클라이언트와 서버 간의 실시간 양방향 통신을 경험해보고, 실시간 데이터 전송 및 비동기 프로그래밍을 학습하는 것을 목표로 했습니다. 이를 통해 네트워크 통신 구조를 이해하고, 실시간 멀티플레이 게임 개발에 필요한 기술을 습득하고자 했습니다.

### 개요
- 프로젝트 이름: PONGDANG
- 프로젝트 진행 기간: 2024.03 - 2024.04
- 개발 언어: Python
- 팀원: 강병규, 김예운, 윤채영
<br/><br/>

## 프로젝트 소개
| 시작 화면                       | 플레이 화면                    | 엔딩 화면                      |
| ------------------------------- | ------------------------------ | ------------------------------ |
| ![스타트](readme_img/start.png) | ![플레이](readme_img/main.PNG) | ![엔딩](readme_img/ending.PNG) |

- 상대의 비치볼을 밀어내라! 육지 위에 마지막까지 살아남는 플레이어가 승자가 되는 전략 알 까기 게임

### GAME TIP!
- 돌을 하나씩 조작해 상대의 돌을 밀어내는 기존 알 까기 게임과 달리, 플레이어는 플레이 턴에 자신의 비치볼 다섯 개를 한꺼번에 조작한다. 이때에 상대 플레이어 역시 비치볼을 조작한다. 턴이 끝나면 해당 비치볼들은 동시에 조작한 위치로 나아가며 충돌한다. 즉 플레이어는 상대의 돌을 밀어내는 공격적인 전략을 취할 것인지, 피하는 방어적인 전략을 취할 것인지 선택해야 한다. 60%의 운과 40%의 전략이 게임을 좌우하는 게임!

### 플레이 룰
1. 플레이어별 다섯 개의 비치볼이 보드 위 랜덤한 위치에 주어진다.
2. 플레이어는 각 비치볼들의 방향, 파워를 조작한다.
3. 플레이 턴이 끝나면, 각 플레이어의 볼들이 동시에 조작한 위치로 나아가며 서로 충돌한다.
4. 2-3번을 반복하며, 상대의 비치볼을 밀어내고 보드 위에 끝까지 비치볼이 남은 플레이어가 승리하게 된다.
<br/><br/>

## 기술 스택
### 사용 기술
Pygame
- Pygame을 활용하면 게임 개발을 통해 프로그래밍의 기본 개념과 알고리즘을 시각적으로 이해
- 이를 이용한 실시간 상호작용 및 이벤트 처리

WebSocket
- 클라이언트와 서버 간의 실시간 양방향 통신 가능, 실제 네트워크 환경에서의 데이터 전송과 비동기 처리를 경험
- 실시간 통신의 효율성과 네트워크 프로그래밍에 대한 이해도를 높임

### 주요 알고리즘
- 오브젝트 충돌 및 물리 엔진: 공이 벽이나 다른 오브젝트와 충돌할 때 각도와 속도 변화가 실제 물리 법칙에 따라 움직이도록 하는 알고리즘
- 캡 배치 알고리즘: 게임 시작 시 플레이어의 캡 위치를 랜덤으로 배치하되, 겹치지 않도록 위치를 조정하는 알고리즘
<br/><br/>

## 게임 구조

### 기본 구조
디스플레이 사이즈
- width: 650 px
- heigt: 977 px

스크린 구성
- 소켓 대기 화면
- 스타트 화면
- 메인(플레이) 화면
- 엔딩 화면

### 게임 로직
소켓 통신
- 소켓을 활용해 화면 송출과 데이터 통신으로 코드를 분리
- 그 후 소켓을 활용해 게임 진행

스타트
- 게임시작 버튼과 움직이는 바탕화면 구현

메인
- 턴제로 하늘색 공이 움직일 방향과 힘을 선택하면 빨간색 공으로 턴이 넘어감
- 선택한 방향과 힘으로 공 이동하면서 충돌
- 승패가 갈리지 않으면 게임 계속 진행
- 결정된다면 엔딩으로 넘어가기

엔딩
- 승패가 결정되었다면 함성소리
- 무승부라면 DRAW만 띄우기
<br/><br/>

## 역할 분담
### 총괄 - 윤채영
- 화면 통합 및 디자인 관리
- 게임 오류 수정 및 디버깅
- 소켓 통신 서브 시스템 구현 및 관리

### 디자인 팀장 - 김예운
- 아이디어 기획 및 정리
- 디자인 및 레이아웃 제작
- 이미지 및 사운드 자원 관리

### 백엔드 팀장 - 강병규
- 게임 메인 로직 구현
- 추가 기능 구현