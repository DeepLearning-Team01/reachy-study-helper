# 협업 규칙

## 1. 브랜치
- `main`: 제출용. 중간 시연, 최종 제출 때만 반영
- `develop`: 개발 통합. **main, develop에 직접 push 금지**
- 작업할 때는 develop에서 브랜치를 만들어요: `feat/기능이름`, `fix/버그이름`, `chore/설정이름`
  - 영어 소문자, 단어는 하이픈(-)으로 구분. 예: `feat/voice-chat`

## 2. 커밋 메시지
`타입: 한글로 한 일` (예: `feat: 음성 대화 기능 추가`)
- feat 기능 / fix 버그 / chore 설정·문서

## 3. PR
- 제목: `[타입] 한 일` (예: `[feat] 음성 대화 기능 추가`)
- develop으로 PR → 본인이 **Squash and merge** → **Delete branch**
  - 리뷰 없이 본인이 머지해도 PR을 거치는 이유: 다른 팀원 코드와 충돌하면 머지 전에 PR 화면에서 미리 알려 줘요. 바로 push하면 develop이 깨진 뒤에야 알게 돼요.
- develop → main은 시연/제출 때만, 팀원 1명 승인 후 **Create a merge commit** (최종 결정: 정민준)

## 4. 할 일 관리
- 회의, 일정, 할 일(누가 뭘 하는지)은 모두 노션에서 관리해요. GitHub 이슈는 안 써요.

## 5. 작업 순서
```
git checkout develop
git pull
git checkout -b feat/기능이름
(작업)
git add .
git commit -m "feat: 한 일"
git push -u origin feat/기능이름
→ GitHub에서 develop으로 PR → Squash and merge → Delete branch
```

## 6. ⚠️ 절대 금지 (레포가 public이라 누구나 볼 수 있어요)
- **API 키는 `.env` 파일에만.** 코드에 직접 쓰지 않기 (`api_key = "sk-..."` ❌)
  - `.env`는 GitHub에 안 올라가요. `.env.example`을 복사해서 만들어요.
  - 실수로 올렸으면 바로 그 사이트에서 키를 삭제하고 단톡에 알리기
- 강의자료 PDF, 모델 파일, 데이터셋, 녹음 파일 올리지 않기
