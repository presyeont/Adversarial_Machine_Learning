
## V. 한계점 및 구현상의 도전 과제 (Limitations and Implementation Challenges)

---

### 복잡성 (Complexity)

* 전체 보안 제어를 구현하려면:
  - 보안 전문성 요구
  - 새로운 도구 도입 투자
  - 운영 자원 지속적 투입 필요

---

### 성능 저하 (Performance Overhead)

* 다음 보안 기능은 지연 및 성능 저하 유발 가능:
  - 심층 패킷 검사 (Deep Packet Inspection)
  - 복잡한 암호 연산 (예: DPoP)
  - 실시간 모니터링
* 특히 저지연 애플리케이션에서는 성능 관리 중요

---

### 도구 생태계 성숙도 및 검증 부담

* MCP에 연동되는 서드파티 도구의 보안 상태가 전체 보안에 영향을 줌
* 외부 도구의 철저한 검증은 어렵고 리소스 많이 소모됨
* 도구 간 보안 품질 차이가 큼

---

### 위협 환경의 변화 속도 (Dynamic Threat Landscape)

* AI 모델, 도구, 공격 기법의 빠른 진화
* 보안 제어는 지속적인 검토 및 업데이트 필요

---

### 실증 검증의 한계 (Empirical Validation Gap)

* MCP는 비교적 새로운 프로토콜
* 실제 공격 사례 및 보안 조치 효과에 대한 데이터 부족
* 본 논문은 주로 개념적, 시나리오 기반 검증에 머무름

---

### 사용성과 개발자 경험 (Usability and Developer Experience)

* 보안 제어가 너무 엄격하면:
  - 개발자 생산성 저하
  - AI 애플리케이션의 사용성 악화 가능
* 적절한 균형이 중요

---

### 정책 적용 일관성 (Policy Enforcement Consistency)

* 다양한 MCP 인스턴스 및 도구에 걸쳐
  - 세분화된 정책을 일관되게 적용하는 것은 운영상 복잡

---

### 결론

* 이러한 도전 과제를 인정하는 것은
  - 현실적인 계획 수립과 MCP 보안의 성공적 구현에 필수

---

## 📋 MCP 보안 위협 및 대응 통제 전략 (Table I)

| Threat Category | Description | Key Controls |
|----------------|-------------|--------------|
| Tool Poisoning | Manipulation of tool descriptions or parameters to induce harmful AI behavior | - Content Security Policy<br>- Tool behavior monitoring<br>- Semantic analysis<br>- Sandboxed execution |
| Data Exfiltration | Unauthorized extraction of sensitive data | - Output filtering with DLP<br>- Response size monitoring<br>- Pattern-based redaction<br>- Anomaly detection |
| Command & Control / Update Mechanism Compromise | Covert channels or persistent backdoors through compromised tools/servers | - Network segmentation / egress filtering<br>- Behavioral analysis<br>- Tool isolation<br>- Cryptographic verification<br>- Supply chain security<br>- File integrity monitoring |
| Identity / Access Control Subversion | Exploitation of auth flaws to gain access | - Enhanced OAuth<br>- JIT access<br>- MFA<br>- Continuous validation |
| Denial of Service (DoS) | Overloading MCP with requests | - Rate limiting<br>- Resource quotas<br>- Anti-automation<br>- Redundancy |
| Insecure Configuration | Misconfiguration in MCP/network | - Secure defaults<br>- Drift detection<br>- Regular audits |

