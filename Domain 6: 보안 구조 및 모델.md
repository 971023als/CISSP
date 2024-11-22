# Domain 6: 보안 구조 및 모델

## 1. 보안정책 및 모델
- **보안정책**:
  - 민감한 정보/자원의 관리, 보호, 배포 규칙
  - 보안 메커니즘으로 달성할 보안 수준 설정
  - 시스템 설계의 중요한 요소 및 평가 기준
- **보안 모델**:
  - 보안을 구현하기 위한 청사진 및 방법론
  - 특징: 예측 가능성, 문제 해결 능력, 로드맵 제공

---

## 2. 시스템 구성 요소
- **CPU 구성**:
  - **Registers**:
    - General Register: 연산 결과나 변수 저장
    - Dedicated Register: 특정 목적의 레지스터
    - IR: 현재 명령어 저장
    - PC: 다음 실행할 명령어 주소 저장
    - MAR/MBR: 메모리 주소 및 데이터 저장
    - PSWR: 시스템 상태 표시
  - **BUS**:
    - Address Bus: 단방향 버스
    - Data Bus: 양방향 버스
    - Control Bus: 단방향 버스
- **RAM 종류**:
  - SRAM: 빠른 속도, 캐시 메모리로 사용
  - DRAM: 주기적 충전 필요, RAM 칩에 사용
  - DDR SDRAM: 클럭당 두 번 명령 수행
- **ROM 종류**:
  - PROM: 단 한 번 쓰기 가능
  - EPROM: 자외선으로 수정 가능
  - EEPROM: 전기적으로 수정 가능

---

## 3. 프로세스 및 메모리 관리
- **프로세스 관련 개념**:
  - Multi-Programming: CPU를 번갈아 사용하는 방식
  - Multi-Tasking: 여러 작업 동시 실행
  - Process Isolation: 무결성 보장
  - Virtual Address Mapping: 메모리 공간 격리
- **메모리 관리자 책임**:
  1. Relocation
  2. Protection
  3. Sharing
  4. Logical Organization
  5. Physical Organization
- **Base Register, Limit Register**:
  - Base: 초기 주소 저장
  - Limit: 마지막 주소 저장
- **Virtual Memory**:
  - 1차 저장장치 + Swap Space
  - 보안 문제: 암호화 부족, 객체 재사용

---

## 4. 운영 체제 구조
- **Monolithic**: 데이터 숨김 제공하지 않음
- **Layered**:
  - 모듈화, 각 레이어는 자체 보안 및 접근통제 제공
  - **Data Hiding**: 다른 보안 등급으로부터 읽기 방지
- **보안 도메인과 보호 링**:
  - R0: OS Kernel
  - R3: Applications
  - 낮은 번호의 링이 더 많은 권한 보유

---

## 5. 신뢰 기반 컴퓨팅
- **Trusted Computing Base (TCB)**:
  - 보안 메커니즘 포함, 커널에 해당
- **참조 모니터**:
  - 주체와 객체 간의 모든 접근 통제
  - 격리성, 검증 가능성, 완전성 보장
- **보안 커널**:
  - TCB의 핵심, HW, SW, 펌웨어로 구성

---

## 6. 접근 통제 모델
- **Mandatory Access Control (MAC)**:
  - Clearance, Classification, Need-to-Know
  - Rule-based, 강제적 접근 통제
- **Discretionary Access Control (DAC)**:
  - 신분 기반, ACL 사용
  - Trojan 공격, 은닉채널에 취약
- **Role-Based Access Control (RBAC)**:
  - 역할 기반, 관리 용이
- **Content/Context-Dependent AC**:
  - 데이터 내용 또는 조건에 따른 접근 통제

---

## 7. 보안 모델
- **Bell-LaPadula (BLP)**:
  - 기밀성 강조, NRU, NWD 규칙
  - 약점: 은닉채널 다루지 않음
- **Biba 모델**:
  - 무결성 강조, NRD, NWU 규칙
  - BLP의 단점을 보완
- **Clark-Wilson 모델**:
  - 무결성의 3가지 목표 (인가자 변형 방지, 내부/외부 일관성)
- **Brew-Nash 모델 (만리장성)**:
  - 직무 분리, 이해 상충 방지

---

## 8. 운영 보안 모드
| 모드               | 허가 | 승인 | 알 필요성 | 비고                     |
|--------------------|------|------|----------|--------------------------|
| 전용 보안 모드       | O    | O    | O        | 단일 등급 정보 취급       |
| 시스템 최고 보안 모드 | O    | O    | X        | 알 필요성 없는 경우 접근 제한 |
| 구획화된 보안 모드   | O    | X    | X        | 알 필요성에 따라 세그먼트 접근 |
| 다중 등급 보안 모드  | X    | X    | X        | 다양한 등급의 정보 취급    |

---

## 9. 컴퓨터 보안 평가 기준
### TCSEC (Orange Book)
- **등급**:
  - A1: 검증된 설계
  - B1-B3: 강제적 보호
  - C1-C2: 임의적 보호
  - D: 최소 보호
- **특징**:
  - 기밀성만 강조, 무결성/가용성 고려하지 않음

### ITSEC
- 기밀성, 무결성, 가용성 포함
- 기능성과 보증 분리

### CC (Common Criteria)
- **필요성**:
  - 국제적 평가 기준
  - 평가 결과의 상호 인증
  - 비용 절감으로 제품 가격 인하
- **TCSEC과 CC의 등급 매칭**:
  - TCSEC B1 = CC EAL4
  - TCSEC C2 = CC EAL3
