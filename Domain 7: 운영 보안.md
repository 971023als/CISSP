# Domain 7: 운영 보안

## 1. 통제(Control) 개념
- **통제**: 위험과 잠재적 손실을 줄이기 위해 민감한 정보 접근을 제어.
- **계정 추적성(Accountability)**: 모든 주체의 행동 기록 및 추적.
- **통제 유형**:
  1. **예방 통제(Preventive)**: 문제 발생 방지.
  2. **탐지 통제(Detective)**: 문제 발생 감지.
  3. **저지 통제(Deterrent)**: 부정행위 억제.
  4. **교정 통제(Corrective)**: 문제 해결.
  5. **복구 통제(Recovery)**: 손실 복구.

---

## 2. 행정 관리 및 보안
- **직원 보안**:
  - **내부 직원**: 보안에서 가장 취약한 연결점.
  - **조치**:
    - 배경 조사(신원 확인, 신용 조사 등).
    - 퇴직 관리: 계정 비활성화, ID 및 키 반납, 퇴직 인터뷰.
- **직무 분리(Separation of Duty)**:
  - 권한 남용 및 사기 방지.
  - 시스템 관리자: 시스템 소프트웨어 설치, 백업 및 복구.
  - 보안 관리자: 사용자 권한 설정, 감사 로그 검토.
- **상호 견제(Two-Man Control)**:
  - 두 사람이 업무를 검토/승인하여 책임 추적성 제공.
- **직무 순환(Rotation of Duty)**:
  - 공모 방지 및 부정 행위 확인.
- **최소 권한(Least Privilege)**:
  - 업무 수행에 필요한 최소한의 권한만 부여.
  - **정관 예우(Authorization Creep)**: 불필요한 권한 축적 방지.

---

## 3. 시스템 및 미디어 관리
- **특권 운영 통제(Privileged Operation Controls)**:
  - 관리자에게 특별한 접근 제한.
  - **Superzapping 프로그램**: 접근 통제를 우회하지 않도록 설계.
- **안티바이러스 관리**:
  - 감염 후 조치:
    1. 시스템 격리 (네트워크 분리).
    2. 데이터 백업.
    3. 시스템 초기화 및 재설치.
- **미디어 관리**:
  - **잔존 데이터**: 데이터 삭제 후에도 남아있는 정보.
  - **보안 방법**:
    - **디가우저**: 자기장으로 데이터 완전 삭제.
    - **폐기(Destruction)**: 광학 매체 데이터 제거의 확실한 방법.

---

## 4. Orange Book의 통제
- **Operational Assurance**:
  1. 시스템 아키텍처.
  2. 시스템 무결성.
  3. 은닉채널 분석.
  4. 신뢰된 시설 관리.
  5. 신뢰된 복구.
- **Life Cycle Assurance**:
  - 시스템 개발 및 유지보수에 필요한 보안 통제.
  - 보안 테스트, 설계 사양 검토, 형상 관리 포함.

---

## 5. 신뢰된 복구 및 형상 관리
- **신뢰된 복구(Trusted Recovery)**:
  - 시스템 장애 발생 시 보안 유지.
  - 주요 파일의 정기적인 백업.
- **형상 관리(Configuration Management)**:
  - 시스템 변경에 따른 보안 위반 방지.
  - B2: 개발 및 유지보수 기간 동안 형상 관리 절차 수행.
  - A1: 시스템 생명 주기 전체에서 형상 관리 절차 수행.
  - **변경 관리 절차**:
    1. 변경 요청 → 승인.
    2. 소스 복사(운영 → 개발).
    3. 수정 및 테스트.
    4. 사용자 승인 후 변경 적용.

---

## 6. 감사 및 침입 탐지
- **감사 증적(Audit Trails)**:
  - 로그를 통해 개인의 행동 추적, 사건 재구성, 침입 탐지 가능.
  - 포함 내용: 트랜잭션 시간, 사용자 정보, 보안 사건.
- **침입 탐지 유형**:
  1. 패턴 인식 및 기준선 비교.
  2. 이상 탐지(Anomaly Identification).
  3. 공격 서명 식별(Attack Signature Identification).
- **Data Scavenging**:
  - 신뢰 경로 정보를 로그 파일에서 추적.

---

## 7. 주요 통제 원칙
1. **직무 분리**:
   - 사기 및 권한 남용 방지.
2. **상호 견제**:
   - 중요한 작업에 두 사람 이상 배치.
3. **최소 권한 원칙**:
   - 필요 최소한의 권한만 부여.
4. **정책 준수**:
   - 변경 관리 및 형상 관리 절차 수행.
