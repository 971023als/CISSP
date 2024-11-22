# 보안 개념 및 정책

## 1. 경영진의 지원
- 보안 성공을 위해 필수적인 요소: **경영진의 지원** (Top-Down 방식)
- 지원이 필요한 주요 보안 활동:
  - 보안정책
  - 보안의식 교육
  - 침투테스트 (Pen Test)
  - BCP/DRP (업무 연속성 계획/재해복구 계획)
  - 위험관리
  - CERT 운영

---

## 2. ISO 7498-2:1989 보안정책 목적
- **보안 3요소**:
  - **가용성 (Availability)**
  - **기밀성 (Confidentiality)**
  - **무결성 (Integrity)**
- **책임추적성 (Accountability)**:
  - 패스워드 공유 금지, 로그 기록 필요성
  - 식별, 인증, 권한 부여, 접근통제, 감사의 기반

---

## 3. NIST 800-33 보안목적
- 보안 목표:
  1. 가용성 (Availability)
  2. 기밀성 (Confidentiality)
  3. 무결성 (Integrity)
  4. 책임추적성 (Accountability)
  5. 보증 (Assurance)
- **가용성**이 최우선 보안 목적

---

## 4. 보안목적의 상호 의존성
- **기밀성(C)**은 무결성(I)에 의존:
  - 예) 트로이목마 감염 → 무결성 손상 → 기밀성 손상
- **무결성(I)**은 기밀성(C)에 의존:
  - 예) 어깨너머로 패스워드 유출 → 기밀성 손상 → 무결성 손상

---

## 5. 위험 관리 (Risk Management)
- **위험**:
  - 정의: 위협이 취약점을 이용하여 조직에 악영향을 미치는 가능성
  - 공식: `Risk (R) = Vulnerability (V) x Asset Value (A) x Threats (T)`
- **위험 관리 과정**:
  1. 위험 평가
  2. 위험 완화 (Risk Mitigation)
  3. 잔여 위험 수용 (Acceptable Risk)

### 위험 완화 수단 (Countermeasure)
- 예방적 조치 (Safeguard, Control)
- 잔여 위험: 보안 대책 후에도 남는 위험

---

## 6. Defense in Depth (D.I.D)
- **중첩 보안**: 여러 장비(F/W, IDS, IPS 등)를 결합해 다중 방어
- 동일 장비로는 효과 없음
- 목적: 상용제품(COTS)의 불완전성을 보완

---

## 7. 데이터 분류
- **목적**: 데이터 중요도(Criticality) 및 민감도(Sensitivity)에 따라 적절히 보호
- **분류 과정**:
  - 보안 관리자가 기준 제시
  - 데이터 소유자(Data Owner)가 데이터 분류 및 등급 할당
- **데이터 가치를 결정하는 이유**:
  1. CBA (Cost Benefit Analysis)
  2. 적절한 Safeguard 선택
  3. 보험 가입
  4. Due Care 만족

---

## 8. 보안정책
- **정의**: 특정 요구사항 또는 규칙에 대한 윤곽을 명시한 문서
- **특징**:
  - 경영진에 의해 생성
  - 포괄적, 일반적, 개괄적
  - 기술, 세부 내역, 방법론 언급 없음

### 보안정책의 종류
1. 허가된 사용 정책 (Acceptable Use Policy)
   - 예: 회사 컴퓨팅 자원의 개인적 사용 금지
2. 계정 정책: 시스템이 사용자를 식별하기 위함
3. 인증 정책
4. 원격접속 정책 (Remote Access Policy)
5. 엑스트라넷 연결 정책: VPN

---

## 9. NIST 보안정책 분류 (NIST 800-12)
1. **Organizational/Program Security Policy**
   - 최고 경영진의 성명서
   - 개괄적이며 수정 빈도 낮음
2. **Issue-Specific Security Policies**
   - 상황에 맞춘 정책, 자주 개정 필요
3. **System-Specific Policy**
   - 개별 시스템 보안정책 (예: Router-ACL, F/W-rule)

---

## 10. 표준, 가이드라인, 절차
1. **정책 (Policy)**:
   - "모든 데이터는 안전해야 한다."
2. **표준 (Standards)**:
   - 강제적, 특정 기술 및 절차 규정
   - 예: "모든 데이터는 24시간마다 백업해야 한다."
3. **가이드라인 (Guidelines)**:
   - 권장 사항, 융통성 제공
4. **절차 (Procedures)**:
   - 세부 단계 기술

---

## 11. 위험 분석
- **목적**: 잔여위험을 수용 가능한 수준으로 감소
- **분석 방법**:
  1. **정성적 분석**: 주관적, 순위결정법, 계산 간단
  2. **정량적 분석**: 객관적, 신뢰성 있는 데이터 제공

### 위험 관리 용어
- **EF (Exposure Factor)**: 손실율 (%)
- **SLE (Single Loss Expectancy)**: 단일 손실 예상액 = `자산 가치 x EF`
- **ARO (Annualized Rate of Occurrence)**: 연간 발생율
- **ALE (Annualized Loss Expectancy)**: 연간 손실 예상액 = `SLE x ARO`

---

## 12. 보안인식 교육
- **목적**:
  - 정보보호 목표, 정책, 필요성, 역할을 설명
  - 직원, 파트너, 공급자의 보안 태도 개선
- **교육 효과**:
  - 직원의 태도 변화, 부정 감소, 책임 의식 증가
- **효과적인 교육 방법**:
  - Role Play, 은유(Analogies) 사용
  - Web-based Training (WBT)

---

## 13. 직무 분리 및 강제휴가
- **직무 분리**:
  - 절대적 권한 방지, Split Knowledge, 부정 예방
  - 예: 개발 vs 생산, 보안 vs 감사
- **강제휴가**:
  - 횡령 예방, 부정 탐지 목적
- **직무 순환**:
  - 부정 탐지, 공모 예방

---

## 14. 사회공학 (Social Engineering)
- **정의**: 사람을 속여 민감 정보를 유출하도록 하는 기술
- **공격 방법**:
  - 동정심 유발, 협박, 공감, 설득
- **예방책**:
  - 보안인식 교육
