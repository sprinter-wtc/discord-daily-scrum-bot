# 🤖 Discord Daily Scrum Bot

GitHub Actions와 Discord Webhook을 활용하여, 매일 혹은 일정 주기로 **데일리 스크럼 알림**을 자동으로 발송하는 봇입니다.  
팀의 커뮤니케이션 효율을 높이고, 진행 상황을 손쉽게 공유할 수 있습니다.

---

## 🚀 기능 (Features)
- 자동 스케줄링 (GitHub Actions 기반)
- Discord Webhook을 통한 팀 알림
- 메시지 및 실행 주기 변수화 지원
- 격일, 매일, 커스텀 스케줄 설정 가능
- 환경 변수만 수정해 유지보수 용이

---

## 🛠️ 설정 (Setup)
1. **Discord Webhook 생성**
   - 디스코드 채널 → `설정 ⚙️ → Integrations → Webhooks → New Webhook`
   - Webhook URL 복사

2. **GitHub Secrets 등록**
   - Repository → `Settings → Secrets and variables → Actions`
   - `DISCORD_WEBHOOK_URL` 추가

3. **워크플로 파일 구성**
   - `.github/workflows/daily-scrum.yml`에 스케줄 정의
   - 환경 변수 수정으로 알림 주기 조정 가능

---

## 🧩 환경 변수 (Environment Variables)

| 변수명 | 설명 | 예시 |
|--------|------|------|
| `DISCORD_MESSAGE` | 전송할 메시지 내용 | "@everyone 💬 데일리 스크럼 시간입니다!" |
| `CRON_MINUTE` | 분 | `'0'` |
| `CRON_HOUR` | 시 (UTC 기준) | `'4'` |
| `CRON_DAY_INTERVAL` | 일 단위 주기 | `'*/2'` |
| `CRON_MONTH` | 월 | `'*'` |
| `CRON_WEEKDAY` | 요일 | `'*'` |

---

## 🕓 스케줄 예시

| 한국 시간 | UTC 기준 | cron 예시 |
|------------|-----------|------------|
| 매일 21시 | 12시 | `0 12 * * *` |
| 매일 09시 | 0시 | `0 0 * * *` |
| 격일 21시 | 12시 */2 | `0 12 */2 * *` |

---

## 📜 예시 메시지

```
@everyone 💬 데일리 스크럼 시간입니다!
1️⃣ 어제 한 일  
2️⃣ 오늘 할 일  
3️⃣ 막힌 점
```

---

## 👨‍💻 기여 (Contributing)
- 새로운 기능이나 개선 아이디어를 환영합니다!
- PR 전 `feature/` 브랜치에서 작업해주세요.

---

## 🪪 라이선스 (License)
MIT License © 2025 DevOps Team