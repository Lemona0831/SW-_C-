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
