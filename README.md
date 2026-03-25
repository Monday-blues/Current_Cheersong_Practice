# 🎤 응원곡 진행도 트래커

팀 응원곡 연습 진행도를 공유하는 웹사이트입니다.

---
이 아래를 너네가 읽을 이유는 없단다.
---

## 📁 파일 구조

```
(레포지토리)/
├── index.html        ← 웹사이트 메인 파일
├── config.json       ← 팀원 이름 & 응원곡 목록 설정
├── progress.json     ← 진행도 데이터 (자동 저장)
└── README.md
```

---

## ⚙️ 최초 설정 (관리자 1회만)

### 1단계 — GitHub 레포 생성
1. GitHub에서 새 레포지토리 생성 (Public으로 설정)
2. 위 파일들을 모두 업로드

### 2단계 — config.json 수정
팀원 이름과 응원곡 목록을 수정하세요:
```json
{
  "members": ["이름1", "이름2", "이름3", "이름4", "이름5"],
  "songs": ["응원곡1", "응원곡2", ...],
  "statuses": ["미완성", "연습중", "완성"]
}
```

### 3단계 — index.html 수정
파일 상단의 두 줄을 수정하세요:
```javascript
const OWNER = 'YOUR_GITHUB_USERNAME';  // ← GitHub 아이디
const REPO  = 'YOUR_REPO_NAME';        // ← 레포 이름
```

### 4단계 — GitHub Pages 활성화
1. 레포 → Settings → Pages
2. Branch: `main` / Folder: `/ (root)` 선택
3. Save 클릭
4. 약 1분 후 `https://아이디.github.io/레포이름` 접속 확인

### 5단계 — Personal Access Token 발급
진행도 저장을 위해 필요합니다 (팀원 중 1명만 있어도 됨):
1. GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Generate new token → `repo` 권한 체크
3. 생성된 토큰 복사 (한 번만 보여줌!)
4. 웹사이트에서 처음 저장 시 입력하면 자동 기억

---

## 🖥️ 사용법

### 진행도 입력하기
1. 웹사이트 접속
2. 자신의 이름 카드 클릭
3. 각 응원곡 옆 버튼으로 상태 선택 (미완성 / 연습중 / 완성)
4. 변경 즉시 자동 저장

### 전체 진행도 보기
1. 웹사이트 접속
2. **📊 전체 진행도 확인** 버튼 클릭
3. 표에서 전체 현황 확인
4. 검색창에 곡 이름 입력 시 필터링

---

## ❓ 자주 묻는 질문

**Q. 남의 진행도를 실수로 바꿀 수 있나요?**  
A. 네, 신뢰 기반으로 운영됩니다. 반드시 자신의 이름을 선택해 주세요.

**Q. 저장이 안 돼요**  
A. Personal Access Token이 만료되었을 수 있습니다. 새로 발급 후 브라우저 localStorage를 초기화하고 재입력하세요.

**Q. 응원곡/팀원을 추가하고 싶어요**  
A. `config.json`의 `members` 또는 `songs` 배열에 항목을 추가하고 GitHub에 커밋하면 됩니다.
