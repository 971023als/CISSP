# Domain 2: 네트워크 통신

## OSI 7 Layer
Mnemonic: **"Please Do Not Throw Sausage Pizza Away"**
1. **Application Layer**: 사용자 인터페이스(UI) 설계
   - **기능**:
     - User-to-Process Interface
     - Database Access, E-mail, File Transfer, Remote Connection
   - **프로토콜**:
     - DNS: UDP 53 (Query), TCP 53 (Zone Transfer)
     - FTP: TCP 21 (접속 및 인증), TCP 20 (데이터 전송)
   - **보안 위협**:
     - DNS Cache Poisoning → Redirect 공격

2. **Presentation Layer**: 데이터 표준화, 암호/복호화, 인코딩/디코딩
   - **기능**:
     - Character 표준(ASCII, EBCDIC), 그림 표준(GIF, JPEG)
     - 암호/복호화, 프로토콜 변환, 데이터 변환
   - **관련 작업**:
     - Redirectors: File System, Printers, Networks

3. **Session Layer**: 어플리케이션 간 대화 방식 결정
   - **기능**:
     - 대화 설정: Full-Duplex(전화), Half-Duplex(무전기), Simplex(라디오)
     - Synchronization: 긴 메시지 추적
   - **프로토콜**:
     - NFS, SQL, RPC
   - **SSL 위치**: Transport Layer 위, Application 사이

4. **Transport Layer**: 데이터 전송 신뢰성 보장
   - **프로토콜**:
     - TCP: Connection-Oriented, Reliable, Flow Control
     - UDP: Connection-less, Best-effort
   - **기능**:
     - Acknowledgement 전송
     - Flow Control (TCP Window Size 사용)

5. **Network Layer**: 라우팅 및 패킷 전송
   - **기능**:
     - 패킷 전송, Intermediate Routing Decisions
   - **프로토콜**:
     - ICMP: 오류 보고 (해결 불가)
     - IGMP: 멀티캐스트
   - **사설 IP 범위**:
     - 10.0.0.0 – 10.255.255.255
     - 172.16.0.0 – 172.31.255.255
     - 192.168.0.0 – 192.168.255.255

6. **Data Link Layer**: 프레임 생성, 오류 감지/수정
   - **기능**:
     - Frame Sequence, Error Detection/Correction
   - **포맷**:
     - Ethernet, Token-Ring, ATM, FDDI, ISDN
   - **프로토콜**:
     - SLIP, PPP, L2F, L2TP, WEP

7. **Physical Layer**: 데이터 비트 전송
   - **기능**:
     - 전기 신호로 변환, 케이블 연결
   - **포맷**:
     - RS-232, Cat-5/6, Coaxial, Fiber
   - **문제 및 해결**:
     - Noise, Attenuation(감쇄), Crosstalk(혼선)

---

## 네트워크 보안
### 패시브 공격 (Passive Attack)
- **유형**:
  - Interception: Sniffer 사용
  - Traffic Analysis, Eavesdropping
- **방지 방법**:
  - 암호화, 스위치 사용, Sniffer 제거(Promiscuous Mode)

### 액티브 공격 (Active Attack)
- **유형**:
  - Spoofing, Replay Attack, Social Engineering
- **DoS 공격**:
  - Ping, SYN Flooding, UDP Flooding
  - 방지: Backlog Queue 늘림, Connection Timeout 줄임
- **DDoS**:
  - 구성요소: Client-Handler-Agent-Target
  - 공격 도구: Trinoo, TFN2K

---

## 방화벽
- **아키텍처**:
  - Screening Router, Screened Host, Screened Subnet, Dual-Home Host
- **방화벽 종류**:
  1. 1세대: Packet Filtering
  2. 2세대: Application Firewall
  3. 3세대: Stateful Firewall
- **가장 안전한 방화벽**: Application-Level Proxy

---

## IDS (침입탐지시스템)
- **탐지 방식**:
  - Misuse Detection: Knowledge Base, Expert System
  - Anomaly Detection: Profile, Statistical, Neural Network
- **Honeypot**:
  - Zero-Day 공격 탐지
  - Corrective Control: IDS와 연계하여 패킷 전달

---

## VPN (Virtual Private Network)
- **VPN 프로토콜**:
  - Application Layer: SSL/SSH
  - Network Layer: IPSEC
  - Data Link Layer: L2TP, PPTP
- **IPSEC**:
  - Header: ESP(암호+인증), AH(인증)
  - Modes: Tunnel Mode(전체 암호화), Transport Mode(End-to-End)
  - 관련 프로토콜: IKE, ISAKMP, OAKLEY

---

## 무선 네트워크 (Wireless Network)
- **802.11 표준**:
  - 802.11b: 2.4GHz, 802.11a: 5GHz, 802.11g: 2.4GHz
- **보안 프로토콜**:
  - WEP: 40bit 키, Replay 공격 취약
  - WPA: WEP+MIC+SEQ
- **위협**:
  - Eavesdropping, Jamming, MITM
- **방지 방법**:
  - WEP 강화, Access Point 설정 변경
