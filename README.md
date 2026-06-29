# 🚀 Retro Synthwave Shooter — 80s Arcade Shmup

> 80년대 레트로 신스웨이브(Synthwave) 스타일의 우주 비행 슈팅 게임. 외부 이미지 에셋 없이 자바스크립트 드로잉 함수만으로 보라색 격자무늬 지평선, 스크린 쉐이크, 파티클 폭발 이펙트까지 단일 HTML에 담은 브라우저 아케이드 슈팅 게임.

![status](https://img.shields.io/badge/status-Live-22C55E?style=flat-square)
![tech](https://img.shields.io/badge/HTML5_Canvas-Vanilla_JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![license](https://img.shields.io/badge/license-MIT-22C55E?style=flat-square)

---

## 🎬 [**라이브 데모 (Live Demo) — 지금 플레이**](https://retro-synthwave-shooter.vercel.app/)

브라우저에서 바로 플레이 가능. GitHub 푸시 시 Vercel 자동 배포.

[**➡️ 지금 플레이: https://retro-synthwave-shooter.vercel.app/**](https://retro-synthwave-shooter.vercel.app/)

| | |
|---|---|
| [![Live Demo](https://img.shields.io/badge/Live_Demo-지금_플레이-FF00FF?style=for-the-badge&logo=vercel&logoColor=white)](https://retro-synthwave-shooter.vercel.app/) | [![GitHub](https://img.shields.io/badge/GitHub-sigco3111%2Fretro--synthwave--shooter-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/sigco3111/retro-synthwave-shooter) |
| [![Status](https://img.shields.io/badge/Status-Live-22C55E?style=for-the-badge)](https://retro-synthwave-shooter.vercel.app/) | [![Stack](https://img.shields.io/badge/Stack-HTML5_Canvas-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://retro-synthwave-shooter.vercel.app/) |
| [![License](https://img.shields.io/badge/License-MIT-22C55E?style=for-the-badge)](https://retro-synthwave-shooter.vercel.app/) | [![Deps](https://img.shields.io/badge/Dependencies-0-9CA3AF?style=for-the-badge)](https://retro-synthwave-shooter.vercel.app/) |

### 🎮 조작 키

| 키 | 동작 |
|---|---|
| **← → / WASD** | 좌우 / 상하 이동 |
| **Space** | 레이저 발사 (홀드 자동 발사) |
| **P / Esc** | 일시정지 / 재개 |
| **R** | 게임 오버 후 재시작 |
| **Esc** | 게임 오버 시 → 타이틀로 (난이도 변경) |
| **1 · 2 · 3 · 4** | 타이틀 화면에서 난이도 직접 선택 |
| **← → (타이틀)** | 난이도 순환 선택 |
| **M** | 음소거 |

### 🎚️ 난이도 (Difficulty)

타이틀 화면의 4개 칩 또는 키보드 `1`–`4` / `←` `→` 으로 선택. 선택은 `localStorage` 에 저장되어 다음 접속 때 자동 복원.

| Mode | Color | Lives | Score | Enemy HP | Speed | Fire-rate | Spawn | Boss-every | BPM |
|---|---|---|---|---|---|---|---|---|---|
| **ROOKIE** | cyan #7afcff | 4 | × 0.75 | × 0.60 | × 0.78 | × 0.70 | × 0.85 | wave 6 | 80 |
| **NORMAL** | cyan #00f5ff | 3 | × 1.00 | × 1.00 | × 1.00 | × 1.00 | × 1.00 | wave 5 | 100 |
| **HARD** | orange #ff8a00 | 3 | × 1.50 | × 1.40 | × 1.22 | × 1.30 | × 1.20 | wave 4 | 120 |
| **INSANE** | pink #ff2bd1 | 2 | × 2.50 | × 2.00 | × 1.45 | × 1.65 | × 1.45 | wave 3 | 140 |

난이도가 영향을 주는 항목: 플레이어 라이프·속도·연사속도, 적 HP·속도·발사속도·총알속도, 적 스폰 밀도, 보스 HP·총알속도·산탄 폭, 점수 배율, 파워업 드랍 확률, BGM 템포.

### 🎯 게임 목표

- 적 함선을 격추하고 점수 획득
- 적 총알 회피 (히트 시 생명 감소)
- 보라색 격자무늬 지평선이 무한히 스크롤되는 80s 신스웨이브 세계관
- 적 파괴 시 화면 흔들림(스크린 쉐이크) + 파티클 폭발

---

## 🤖 생성 정보 (How this was made)

이 프로젝트는 **OpenCode** CLI의 **MiniMax-M3** 모델에 아래 프롬프트를 입력하여 진행됩니다.

### 사용된 프롬프트

> 외부 이미지 에셋 없이 오직 자바스크립트 드로잉 함수만으로 80년대 레트로 신스웨이브(Synthwave) 스타일의 우주 비행 슈팅 게임을 만들어주는데, 배경에는 보라색 격자무늬 지평선이 무한히 스크롤되는 3D 원근감 효과를 넣고, 적을 파괴할 때 화면이 흔들리는 스크린 쉐이크(Screen Shake) 효과와 화려한 파티클 폭발 이펙트가 포함된 완성도 높은 게임을 단일 파일로 코딩해줘.
>
> **Implementation Advice:** Use HTML5 Canvas. The rolling grid background can be simulated with simple 2D perspective math (no need for full 3D engine). Implement 'Screen Shake' by temporarily offsetting the canvas context (ctx.translate) during the render loop. 모든 의존관계의 코드를 하나의 HTML에 담는 형태로 코드 작성.

### 구현 예정 핵심 기술

| 항목 | 접근법 |
|---|---|
| **3D 원근 격자 지평선** | 2D 원근 수학 (`y_screen = horizon_y + (cy - horizon_y) * scale`, 시간 오프셋으로 무한 스크롤) |
| **스크린 쉐이크** | `ctx.translate(random_offset_x, random_offset_y)` 를 render loop에서 임시 적용 후 복원 |
| **파티클 폭발** | 작은 원/선을 객체 배열로 관리, 시간 경과로 크기/투명도 감소, lifespan 만료 시 제거 |
| **레이저 / 적 / 충돌** | AABB 충돌 검사 + 게임 루프 (requestAnimationFrame) |
| **난이도 스케일링** | `CFG.DIFFICULTY[rookie\|normal\|hard\|insane]` 의 13개 배율 (lives / scoreMul / enemyHp / enemySpd / spawnRate / fireRate / bossEvery / bossHp / bossBullet / spreadFan / musicBpm / dropMul) 을 모든 적·보스·플레이어·사운드 경로에서 `_diff()` 한 줄로 적용 |
| **사운드** | Web Audio API로 절차 합성 — 난이도별 BPM (80/100/120/140) 로 배경음악 템포 변화 |

### 생성 환경

| 항목 | 값 |
|------|-----|
| **AI 도구** | OpenCode CLI |
| **모델** | `MiniMax-M3` |
| **입력 방식** | 위 프롬프트 |
| **후처리** | 사람이 README 작성 및 구조 정리 |

---

## ✨ Features

- 🌌 **무한 스크롤 보라색 격자무늬 지평선** — 2D 원근 변환으로 3D 효과 모방
- 💥 **스크린 쉐이크(Screen Shake)** — 적 격추 시 화면 흔들림
- ✨ **파티클 폭발 이펙트** — 적 파괴 시 색상별 입자 비산
- 🔫 **레이저 발사 시스템** — 홀드 자동 발사
- 👾 **다양한 적 함선** — 크기/색상/이동 패턴별 분류
- 🏆 **점수 시스템** — 적 종류별 점수 + 최고점수 로컬 저장
- ⏸️ **일시정지 / 재시작** — 부드러운 게임 흐름
- 🎚️ **4단계 난이도 (Rookie / Normal / Hard / Insane)** — 적 HP·속도·보스 패턴·점수 배율·BGM 템포 모두 일괄 조정, 선택 `localStorage` 저장
- 🎨 **클래식 신스웨이브 팔레트** — 핑크 #FF00FF + 시안 #00FFFF + 보라 #8B00FF + 검정
- 🚀 **Zero-Dependency** — 외부 라이브러리 없이 단일 HTML 파일

---

## 🚀 사용법 (Usage)

### 로컬 실행

```bash
# 파일 열기:
open index.html

# 또는 로컬 서버 (권장)
python3 -m http.server 8000
# → http://localhost:8000 접속
```

### 라이브 데모 (Vercel 자동 배포)

GitHub에 푸시되면 Vercel이 자동으로 빌드하여 `https://retro-synthwave-shooter.vercel.app/` 에 배포합니다.

---

## 🛠️ 기술 스택

| 영역 | 사용 기술 |
|---|---|
| **렌더링** | HTML5 Canvas 2D Context |
| **물리 / 충돌** | 직접 구현 (AABB) |
| **입력** | KeyboardEvent (`keydown` / `keyup`) |
| **게임 루프** | `requestAnimationFrame` + 델타타임 |
| **사운드** | Web Audio API (선택) |
| **빌드** | 불필요 (단일 HTML) |
| **배포** | Vercel (GitHub 푸시 시 자동) |

---

## 📝 라이선스

MIT License — 자유롭게 사용, 수정, 배포 가능합니다.

---

## 🙏 Credits

- **신스웨이브 비주얼 컨셉** — 1980년대 아케이드 / Outrun / Miami Vice 미학
- **격자무늬 지평선 기하학** — 전통 원근 투영 수학
- **스크린 쉐이크 패턴** — 클래식 아케이드 슈팅 게임 UX 관행
- **AI 생성** — OpenCode + MiniMax-M3
- **코딩미션 참조 페이지**: [cokac.com — 코드깎는노인](https://cokac.com/list/announcement/24)

---

<p align="center">
  <sub>🌌 Built with neon glow + 80s arcade vibes · sigco3111 · MIT · AI-generated by MiniMax-M3</sub>
</p>