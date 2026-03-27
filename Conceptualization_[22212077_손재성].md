<img width="1835" height="1764" alt="로고." src="https://github.com/user-attachments/assets/72a904ab-0ea3-4f66-a909-05c84136328d" />
영품타(영남대를 품은 타이머)
https://github.com/skfek0916/YeungPoomTa

컴퓨터공학전공 22212077 손재성 nehalem0916@yu.ac.kr

# 1. Business purpose


<img alt="[그림 1] 열정 품은 타이머" src = "https://www.yeolpumta.com/static/img/ypt_screen_02.png" width="1000">
[그림 1] 열정 품은 타이머

## 1.1. Project Background
  이 프로젝트는 집중력 분산 문제를 피하고 학생의 순수 공부 시간 관리를 돕기 위해, PC 웹 브라우저 환경에서 접근 가능한 가벼운 타이머 및 스톱워치 서비스를 기획한 데서 출발했습니다. 유사 서비스 중 하나인 '열정 품은 타이머', 일명 '열품타'는 수험생들에게 큰 인기를 누리고 있습니다. 하지만 열품타는 안드로이드, iOS 등 현재 모바일에서만 서비스되고 있기에 컴퓨터공학도와 같이 PC를 위주로 공부하는 데스크 환경에서 공부하는 잠재적 이용자층에 적합한 서비스가 필요하다고 판단했습니다.



## 1.2. Target Market
 데스크 환경에서 장시간 학습하는 고시 준비생과 체계적인 학습 관리가 필요한 학생입니다. 본인의 기록뿐만 아니라 타 이용자의 공부 스톱워치 기록을 열람할 수 있도록 할 것입니다. 이를 통해 경쟁의식을 고취하고 자기주도학습을 촉진할 수 있는 환경이 조성될 수 있도록 하는 것입니다.



## 1.3. Goals
 직관적인 누적 데이터 시각화를 통해 사용자의 지속적인 동기를 유발하여 서비스 리텐션을 확보하고, 시스템적으로는 SPA(Single Page Application) 환경에서 상태 관리를 활용해 타임 스톱워치 및 CRUD를 안정적으로 구현하는 것입니다.



# 2. System context diagram

<img width="1386" height="429" alt="image" src="https://github.com/user-attachments/assets/9e64f440-9ee6-496e-8226-e9855eb011bd" />
[그림 2] System context diagram  

Register – 사용자 회원가입  
Log in / Log out – 로그인 / 로그아웃  
Timer, Stopwatch start / pause / stop – 타이머 또는 스톱워치 기록 시작/일시중지/중지  
View other user's statement – 타 사용자 상태 열람  
Create and join groups – 그룹 생성 및 참가  
Send notifications – 다른 사용자에 알림 전송  
Alarm ends – 사용자가 알람 종료   
User info – 사용자 정보  
Group info – 그룹 정보  
Send notifications – 알림 전송  
User account – 사용자 계정  
User info – 사용자 정보  
 




# 3. Use case list

| No. | Use Case | Actor | Description |
| :---: | :--- | :---: | :--- |
| 1 | Register | User | 사용자가 회원가입 한다. |
| 2 | Login | User | 사용자가 기존 계정에 로그인한다. |
| 3 | Timer, Stopwatch start / pause / stop | User | 사용자가 타이머 또는 스톱워치를 시작, 일시중지, 중지한다. |
| 4 | View other user's statement | User | 사용자가 타 사용자의 정보를 조회한다. |
| 5 | Create and join groups | User | 사용자가 그룹을 만들거나 그룹에 참가한다. |
| 6 | Send notifications | User | 사용자가 타 사용자에게 알림을 전송한다. |
| 7 | Alarm ends | User | 사용자가 타이머 알람을 종료한다. |


# 4. Concept of operation

| No. | Use Case | Purpose | Approach | Dynamics | Goals |
| :---: | :--- | :--- | :--- | :--- | :--- |
| 1 | Register | 사용자 관리 위한 새 계정 회원가입 | 사용자가 새 계정 ID, PW를 입력하여 회원가입 요청 시 서버에서 ID 중복 여부 확인 후 가입 절차를 진행한다. | 사이트 접속 후 회원가입을 실행할 경우 | 회원가입 기능을 구현한다. |
| 2 | Log in / Log out | 사용자 관리 위한 로그인 및 로그아웃 | 사용자가 기존 계정 ID, PW를 입력하여 로그인 요청 시 서버 내 ID, PW 정보 조회하여 계정 정보 일치 여부를 결정한다. 로그아웃 요청 시 로그아웃 절차 수행한다. | 사이트 접속 후 로그인 또는 로그아웃 실행할 경우 | 로그인 및 로그아웃 기능을 구현한다. |
| 3 | Timer, Stopwatch start / pause / stop | 사용자 기록 관리 위한 타이머 또는 스톱워치 시작, 일시중지, 종료 | 사용자가 타이머 또는 스톱워치를 시작, 일시중지, 종료 등 변동 시 서버에 전송해 이를 업데이트하여 누적 시간을 기록한다. | 사용자가 타이머 또는 스톱워치 등 시간 기록 변동 할 경우 | 누적 시간을 기록한다. |
| 4 | View other user's statement | 사용자가 타 사용자 상태 정보를 열람 | 사용자가 타 사용자의 프로필 및 누적 시간 등 상태 정보를 확인한다. | 타 사용자의 프로필을 클릭한 경우 | 타 사용자의 상태 정보를 열람할 수 있도록 한다. |
| 5 | Create and join groups | 사용자가 그룹 개설 및 참가 | 사용자가 그룹을 개설하거나 그룹에 참가할 경우 서버에서 그룹명 및 그룹 참가 중복 여부 판단 후 개설 또는 참가한다. | 사용자가 그룹 개설 및 그룹에 참가할 경우 | 그룹 개설 및 참가 기능을 구현한다. |
| 6 | Send notifications | 사용자가 타 사용자에 알림(깨우기 기능)을 전송 | 사용자가 타 사용자에게 알림을 전송할 경우 서버에서 타 사용자에게 알림을 전달한다. | 사용자가 타 사용자 프로필을 눌러 깨우기 기능을 실행한 경우 | 타 사용자에게 알림을 전송한다. |
| 7 | Alarm ends | 사용자가 설정한 타이머 설정 시간 도래해 울리는 알람을 종료 | 사용자가 설정한 타이머 시간이 도래해 울리는 알람을 종료한다. | 타이머가 알람이 울릴 경우 | 알람 종료 기능을 수행한다. |






# 5. Problem statement

Problem #1 – 보안 정책 관련 지식 수준 얕음.  
계정 로그인 체계를 포함한 프로젝트 경험이 부족해 보안 정책 관련 지식 수준이 얕음.  
계정 정책, 사용자 관리 등 관련 유심히 살펴야 할 필요성 있음, 학습을 통해 문제점 보완 예정.  

Problem #2 – API를 이용한 로그인 정책 검토 필요하나 관련 지식 전무   
소셜 ID 기반 로그인 도입할 의사 있으나 관련 지식 전무함,   
향후 공부를 통해 지식 보완할 예정.  

Problem #3 – 단일 사용자의 다중 계정 생성 방지 대책 필요  
단일 사용자의 다중 계정 생성 방지 필요하나 IP주소 등 사용자 정보만으로는 역부족,  
이메일 등 2차 인증 등의 정책 필요함.  

Problem #4 – 리얼타임 서비스로 인한 서버 부하 대책 필요성  
다수가 동시다발적으로 이용하는 서비스, 부하 최소화 정책 필요함.

NFR
- 1. 응답성: 시간 오차 1초 이하로 동기화
- 2. 무결성: 누적 시간 등 데이터 위변조 방지
- 3. 보안성: 단일 사용자의 다중 계정 생성 방지




# 6. Glossary
SPA(Single Page Application)
- 단일 페이지 모던 웹 애플리케이션, 다양한 페이지를 한 페이지에 담아내는 정책.

타 사용자
- 사용자 외 서비스 이용 중인 타 사용자

CRUD
- Create, Read, Update, Delete






# 7. References

[그림 1] 열품타
https://www.yeolpumta.com/
