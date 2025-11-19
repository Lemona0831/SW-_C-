# SW-_C-
## TicketBot — C 기반 고속 우선순위 티켓 관리 Discord Bot

디스코드에서 고객 문의·티켓을 관리하기 위한 C 기반 고속 Queue + Priority Queue 를 사용하는 Discord Bot입니다.
기본적인 일반 티켓 + 우선순위 티켓을 모두 처리하며, JSON 지속 저장 및 CSV 로그 기록이 가능합니다.


## 핵심 기능
### ✔ 일반 티켓 Queue

/ticket_create 로 생성

/ticket_next 로 처리 (우선순위 없는 티켓 대상)

### ✔ 우선순위 티켓 Priority Queue

/ticket_priority <id> <1~5> 로 지정

/ticket_next 호출 시 우선순위 티켓 먼저 처리

/ticket_priority_list 로 목록 열람 (버튼 페이지네이션)

### ✔ DM 기반 티켓 목록 UI

/ticket_list 사용 시 개인 DM으로 페이지네이션 UI 제공

버튼으로 페이지 이동 가능

### ✔ JSON + C 이중 저장

JSON 파일로 영구 저장

C Queue/Priority Queue 로 실행 중 빠른 작업

봇 실행 시 JSON → C 구조 자동 복원

## 🔧 설치 방법
### 1️⃣ Python 설치 (3.11 ~ 3.13 지원)

필요 패키지 설치:

pip install discord.py

## 🔧 2️⃣ 환경 변수 설정 (봇 토큰)

Windows (PowerShell):

setx DISCORD_TOKEN "여기에_봇_토큰"


Mac/Linux (bash):

export DISCORD_TOKEN="여기에_봇_토큰"

## 🔧 3️⃣ DLL 빌드 방법 (ticketlib.dll)

Windows (MinGW-w64 설치 필요):

gcc -shared -o ticketlib.dll queue.c priority_queue.c error.c -O2

DLL은 Python 실행 폴더 or bot 폴더에 반드시 넣어야 합니다.

### ✨ 사용 가능한 Slash Commands
명령어	설명

/ticket_create <내용>	새 티켓 생성

/ticket_list	DM으로 목록 전송

/ticket_status	현재 큐 크기 표시

/ticket_priority <id> <1~5>	우선순위 지정

/ticket_priority_list	우선순위 티켓 리스트 UI

/ticket_next	다음 티켓 처리 (우선순위 → 일반 순서)

/shutdown	관리자만 봇 종료


## 🗂 로그 CSV 저장 형식 예시
ticket_id	user	message	created_at	processed_by	processed_at

## 🛠 개발자 노트 [1.0ver]
C 성능 최적화

Queue: 배열 기반 FIFO


JSON 저장으로 재시작해도 데이터 유지

DLL 오류 발생 시 c_get_last_error() 반환 지원

## 라이선스
MIT License
