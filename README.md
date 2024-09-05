# Robot_Manual
## DAY -1 
Robot
<두산로보틱스 교육>
우리모델 : M0617

-- 기본
25 / 13 payload / Reach
M Series - 대중화, 모든 안전로직 적용완료. 
W가 부하가 되는 
저속에서 진동이 발생할 수 있다?왜?
TP(TEACH 팬던트) 
DART PLATFORM 
Doosan Robot LAB / 소프트웨어 버전 맞추는 방법이 있다.
3개 선이 꽃아진다.
AC/DC 선택을 해서 사용한다. 
AMR에 태운다
각축에 대한 커버에 대한 예비품 구매가능
협동로봇

-- 제어
Cockpit 
1번 버튼 - 축고정 (상/하) Z축
2번 버튼 - 행고정 (좌/우 Rotation), X,Y축 
3번 버튼 -전고정 
Hole 규격은 동일
BASE 도면은 각 제조사에 따라 다르다 

연결해 하는 제어부분
로봇케이블
TP케이블
컨트롤러케이블

TP에 대한 노이즈 필터가 존재한다
최소 곡률반경을 만들어놓고 사용

-- 작업영역 
6축에 대한 거리 확인, 6축이 회전하지 않는다는 기준으로 사용한다

특이점의 종류
BASE/축/TOOL
:3가지경우에 대해서 존재
(1/2/3)
① 3축 0
② 5축 0
③ 1,6축 동일선상에 있는 경우 

모든 축을 다뻗은 상태에서 사용하기
로봇을 15 구부러지도록 설정해야한다 
왜 안되는지 확인이 필수적이다 

특이점에 대한 자동회피가 존재한다
특이점을 반영해서 Layout을 짜야한다
리치를 조금 고려해서 제품선정이 필요하다 
-- Dart SW 사용
 
PW : admin
로봇 Ip 확인 
로봇 버전 확인 GV02110100 ( 0은 .으로 읽으면 되는지) 해당 버전은 11.1 을 맞추면 된다. 
업데이트 권장에 대한 부분 2버전내에서 Intgration update로 동일하게 맞춰야 한다. 
Idle servo off,
screen saver 를 최대한 늘려서 해야한다
Log 를 통해서 오류를 확인할 수 있다 
Update
IP경우, 100과 1

JOG로 정렬하는 부분 사양 . Parallel  Axis
Dart Studio d외력에 대한 셋팅을 사용한다
Collsion Sensitivtiy 민감도 조정
속도에 대해서 가속도가 가이드 되어있다

프로그램 이 종료되는 부분에 대해서 
시그널을 어떻게 받아야하나?
Safety IO(2점씩 사용해야한다) , Not used 변경 확인
PC가 메인연결 
외부시그널 Input에 대해서 시그널을 줘야한다(내부전원 input Output ) 
로봇on/off, pc on/off 
설정에 대해서 11개가 기본적으로 사용
Remote.
TP - Operator. 
비전으로 케이스를 나눠서 동작에 대한 부분을 줘야하는 걸로
A,B,C에 대해서 

-- 중량물에 대한 무게 입력
+ , Categories
** Robots 
Tool Weights 
Full Motion, 
*

4,5,6 D Joint Motion
Auto Measure Motion으로 자동 제어 중에서 혹시나 모를 상황에 Stop 대기 
Cofirm 진행.
Tool weight 에 Camera  
TCP (Tool Center Position) 
축좌표계 / Base좌표계 / TCP라는 카메라 좌표쪽으로 이동을 안해도 괜찮은 거네
외관을 할 때는 TCP 기준으로 해야 한다. 
**
Controll 
마스터이미지를 찍고, 해당 부분에 대한 좌표를 준다 
로봇이 틀어지는 경우에 대해서는 어떻게 해야하는지 
고정만 잘되어있다는 전제하에 무조건 . 
로봇이 전원을 껐을때. 값이 틀어지면 On/off 가 안된다. 

완전히 고장난 상태에 대해서는 보전이 필요하다. →Back Drive Mode 
보전쪽에 대해서는 틀어졌을 때는 영점잡는 거에 대해서 신경써달라 
Absolute 위치값에 대해서 비교가 되는 부분이 있다. 
소리에 대해서는 브레이크가 걸리고/안걸리는 걸 확인가능하다 
off/Back Drive Mode Click 
하면 각 축에 대해 보전을 해주면 된다.

틀어진 정도만 주게 되면, 좌표를 조정할 수 있다. 
계산하는 방법. 좌표계꼬다리기준 X,Y F
Camera TCP 1DCP

[X,Y] ','단위로 나눠서 데이터를 주면 된다. 
BASE와 TOOL 좌표에 대해서 

* Shoulder 를 사용할 때에 대해서는 TCP좌표를 잡아야 한다

## DAY 2
-- INSTALL
-- Program
-- User Manual 
Task write 
Limit를 해제해서 사용한다 recovery mode
Limit가 되면, 빨간색
Recovery가 되면, 노란색 
Unpack 
직접수정할 경우에는, 하늘색
JOG AXIS 평행
INTERLOCK RESET 
협착된 상태에 대해.무조건 Recovery 모드로 가야한다
Protective Stop (노란색) - 선택: SS1, SS2
Recovery에서 predrive
Collision Sensitivity :1로 사용하면 안된다
manual 15 SSO 로 해야하는지 확인하기 

Workshell, Safety Stop에 대한 조건을 설정할 수 있다. 
SS1, SS2
Collusion SS1,SS0 으로 하면, 빨리 멈춘다
Software recovery

## TCP
Tool Center Position 
4 point
move J, move l
Rz축으로 돌린다 

Client open 


