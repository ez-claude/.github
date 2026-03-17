# EZ Claude

Claude Code를 쓰다 보면 반복되는 실패 패턴이 있습니다.
파일을 읽지 않고 기억으로 설명하다 틀리거나, 증상만 고치고 근본 원인은 그대로 두거나.
이 저장소들은 그 패턴들을 구조적으로 차단합니다.

---

## 저장소

### [ez-harness](https://github.com/ez-claude/ez-harness) &middot; [소개](https://ez-claude.github.io/ez-harness/ez-harness.html)

AI 실패 패턴 차단 시스템. Claude Code + Antigravity 양쪽 지원.

**핵심: 발생하지 않은 버그를 배포 전에 잡습니다.**

- 역추적: 증상 -> 경로 -> 수정 위치 확정
- DMAD 토론: 코드 작성 전 설계자 vs 사용자 관점 문답
- sim: 3개월 + 10배 규모 장기 실패 시뮬레이션
- smartLoop: 실패 유형별 최소 지점 재시작 (최대 3회)

### [ez-plans](https://github.com/ez-claude/ez-plans)

Claude Code Plan Mode 결과를 파일로 영속화하는 시스템.

- 멀티세션 작업을 플랜 파일로 보존
- research.md 선행 조사 필수
- [보고] 마커로 단계별 체크포인트 제어

---

## 함께 쓰는 흐름

```
ez-plans:   플랜 수립 -> research.md -> overview.md -> GATE -1 검증
ez-harness: GATE -> DMAD 토론 -> 코드 -> sim -> Check
```
