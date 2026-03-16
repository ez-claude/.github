# EZ Claude

Claude Code가 문제를 잘못 고치거나, 고쳤다가 다른 곳을 망가뜨리는 걸 막는 도구 모음입니다.

코드를 잘 모르는 상태에서 AI에게 맡기는 경우에도 유효합니다.

---

## 도구

### [ez-claude-harness](https://github.com/ez-claude/ez-claude-harness)

코드 작성 전후 검증 규칙. Claude Code가 표면만 고치고 끝내는 패턴을 구조적으로 차단합니다.

**핵심 가치: 버그가 발생하기 전에 잡습니다.**
코드 완성 후 배포 전, "3개월 후 + 규모 10배" 상황을 시뮬레이션해서 잠재적 문제를 근본 원인까지 찾고 수정합니다.

- 역추적: 증상이 아닌 근본 원인 위치에서 수정
- DMAD 토론: 코드 작성 전 설계자 vs 사용자 관점 문답
- sim: 장기 실패 시뮬레이션 (배포 전 미발생 버그 탐지)
- smartLoop: 문제 해결될 때까지 최대 3회 자동 반복

### [ez-plans](https://github.com/ez-claude/ez-plans)

Claude Code Plan Mode 결과를 파일로 영속화하는 시스템. 세션이 끊겨도 플랜이 사라지지 않습니다.

- 멀티세션 작업에서 플랜 유지
- research.md 선행 리서치 강제 (outdated 정보로 플랜 수립 방지)
- [보고] 마커로 단계별 체크포인트 설정
- git 기반 팀 공유

---

## 함께 쓰는 흐름

```
ez-plans:          플랜 수립 → research.md → overview.md → GATE -1 검증
ez-claude-harness: GATE → DMAD 토론 → 코드 → sim → Check
```

플랜 단계에서 방향을 잡고, 코드 단계에서 검증까지 자동으로 이어집니다.
