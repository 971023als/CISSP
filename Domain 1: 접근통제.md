# Domain 1: 접근통제

## 접근통제란?
보안정책(Security Policy)에 의거하여 자원에 대한 비인가 접근을 감시하고, 접근 사용자 식별 및 접근 요구의 정당성을 확인하는 것.

- **주체**: 사용자, 프로그램, 프로세스 등
- **객체**: ERP, DATA, 프로그램 등
- **접근통제 시스템 (Reference Monitor)**:
  - **정의**:
    1. 접근통제 결정을 중재하는 OS의 요소
    2. 모든 접근 요청이 통과되어야 하는 단일 지점(Single Point)
    3. 주체와 객체 간의 모든 접근을 중재
    4. 객체로의 접근이 요청될 때만 작동
    5. 방화벽은 Reference Monitor의 한 형태
  - **우회 방법**: 객체가 주체로 직접 접근

### Reference Monitor의 3가지 요소
1. **Completeness**: 안전성, 우회 불가능
2. **Isolation**: 격리성, 부정조작 불가(무결성 보장)
3. **Verifiability**: 검증 가능성 (분석/테스트 가능하도록 충분히 단순해야 함)

---

## 접근통제의 원칙
1. **Need-to-know 원칙**: 꼭 필요한 권한만 부여
2. **최소 권한의 원칙 (Least Privilege Policy)**:
    - 금지되지 않은 접근을 허용하는 최대 권한 정책과 대조
    - 보안 강화에 사용
3. **직무 분리 원칙 (Separation of Duty)**:
    - 한 사람이 업무 전체를 처리하지 못하도록 제한
    - **예시**: 보안/감사, 개발/생산, 암호키 관리/변경

---

## 접근 단계
1. **식별 (Identification)**: "내가 누구다"를 시스템에 알림 (ex: ID)
2. **인증 (Authentication)**: 본인 여부 확인 (ex: 패스워드, 스마트카드, 생체 인증)
3. **승인 (Authorization)**: 접근 권한 유무 확인
4. **인가 (Authorization)**: 접근 권한 부여
5. **감사 (Audit)**: 권한 내 작업 여부 감시

---

## 접근통제 레이어
1. **물리적 통제**: CCTV, 경비원, 카드키
2. **관리적 통제**: 정책, 직무 분리
3. **기술적 통제**: 암호화, Callback System, IDS

---

## 인증 방식에 따른 분류
| **인증 구분** | **설명**                  | **기반** | **종류**              |
|---------------|--------------------------|----------|-----------------------|
| Type I        | Something you know       | 지식     | 패스워드, PIN, Passphrase |
| Type II       | Something you have       | 소유     | 스마트카드, 토큰      |
| Type III      | Something you are        | 존재     | 홍채, 지문, 정맥      |
| Type IV       | Something you do         | 행동     | 음성, 서명            |

- **보안 강도**: Type I < Type II < Type III
- Type I + Type II > Type III

---

## 패스워드 관리
- **장점**: 저비용
- **단점**: 낮은 안전성, 부인 가능성
- **정책**: 8~12자 조합, 공유 금지, 감사 기록 유지
- **사전 공격 방지**: PW Salting 사용

---

## 접근통제 기술 유형
1. **MAC (Mandatory Access Control)**: Rule-based
    - 데이터 소유자가 아닌 관리자만 자원 변경 가능
    - Orange Book B-level 요구사항
    - 기밀성 중심 (ex: 군사정보)
    - **장점**: 보안성 강함
    - **단점**: 구현 어려움
2. **DAC (Discretionary Access Control)**: Identity-based
    - 데이터 소유자가 임의로 접근 제어
    - Orange Book C-level 요구사항
    - 상용 OS에 적합
    - **장점**: 유연성, 구현 용이
3. **RBAC (Role-Based Access Control)**:
    - 사용자의 역할에 따라 접근 제어
    - **장점**: 보안 관리 간소화

---

## 접근통제 보안 모델
1. **Bell-LaPadula (BLP)**:
    - **기밀성** 중심
    - No read-up (NRU), No write-down (NWD)
2. **BIBA**:
    - **무결성** 중심
    - No read-down (NRD), No write-up (NWU)
3. **Clark and Wilson**:
    - **무결성** 및 직무 분리 강조
    - 데이터는 지정된 프로그램만 조작 가능
4. **만리장성 모델 (Brewer-Nash)**:
    - 이익 충돌 방지를 위한 접근통제 모델

---

## 침입탐지시스템 (IDS)
- **종류**:
  - HIDS: 내부자 공격 탐지
  - NIDS: 외부 DOS 공격 탐지
- **탐지 방식**:
  - 오용 탐지: False(+) 낮음
  - 이상 탐지: False(+) 높음

---

## Single Sign-On (SSO)
- **장점**: 보안성 증가, 계정 관리 단일화
- **단점**: Single point failure

---

## Kerberos
- **정의**: 대칭키 기반 티켓 인증 프로토콜
- **구성요소**:
  - KDC: 키 분배 서버
  - AS: 인증 서비스
  - TGS: 티켓 생성
  - Ticket: 인증 토큰
- **장점**: 재생 공격 예방, 네트워크 인증 지원
- **단점**: PW 추측 공격에 약함, 시간 동기화 필요

---

## 침투 테스트
- **단계**: Planning -> Discovery -> Attack -> Reporting
- **유형**: Black Box Test, Open Box Test
- **목적**:
  1. 취약성 발견
  2. DOS 공격에 대한 내성 확인
