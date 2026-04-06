# 🚀 빠른 시작 가이드

## 1단계: OpenRouter API 키 준비 (5분)

### 1.1 OpenRouter 가입
- [openrouter.ai](https://openrouter.ai) 방문
- "Sign Up" 클릭 후 계정 생성
- 이메일 인증

### 1.2 API 키 생성
1. 로그인 후 우측 상단 **"Settings"** → **"API Keys"**
2. **"New Key"** 버튼 클릭
3. 키 이름 입력 (예: "tarot-reader")
4. 생성된 키 복사 (`sk-or-...`)

### 1.3 크레딧 확인
- 왼쪽 사이드바 **"Billing"** 확인
- 초기 무료 크레딧이 있는지 확인
- 필요시 결제 정보 추가

## 2단계: 애플리케이션 실행 (2분)

### 방법 A: 브라우저에서 직접 열기 (가장 간단)
```
폴더를 탐색기에서 열기
→ index.html 파일 더블클릭
```

### 방법 B: VS Code Live Server 사용 (권장)
1. VS Code에서 폴더 열기
2. VS Code 확장 설치: "Live Server"
3. `index.html` 우클릭 → "Open with Live Server"

### 방법 C: 로컬 서버 실행
```bash
# Node.js 필요
npm install
npm run dev
# http://localhost:8080 에서 실행
```

## 3단계: 애플리케이션 사용

### 첫 사용
1. **API 키 입력**
   - 상단의 "OpenRouter API Key" 입력 필드에 키 붙여넣기
   
2. **테스트 버튼 클릭**
   - "테스트" 버튼으로 키 검증
   - ✓ 표시 나타나면 성공

3. **모델 선택**
   - "GPT-4o Mini" (빠르고 저렴) 또는
   - "Mistral Small" (균형잡힘)

4. **타로 내용 입력**
   ```
   예: Yes/No 질문 + 3장의 카드 + 결과
   ```

5. **카드 해석하기 버튼 클릭**

### 결과 저장
1. 해석 결과 확인 후 **"보관함에 저장"** 클릭
2. 왼쪽 위 **"보관함"** 배지에서 저장된 리딩 확인 가능

## 💡 팁

### 효과적인 입력
✨ **구체적일수록 좋습니다**
- 카드 이름 + 정/역방향 명시
- 질문이나 맥락 포함
- 스프레드 형식 명확하게

### API 비용 절감
- GPT-4o Mini: 가장 저렴하고 빠름
- 짧은 입력: 요금 감소
- 4000 max_tokens 이내 자동 설정

### 데이터 관리
- 브라우저 로컬 스토리지에 자동 저장
- 브라우저 캐시 삭제 → 모든 데이터 삭제
- 백업 원하면 **보관함** 스크린샷 저장

## 🆘 자주 묻는 질문

**Q: API 키 테스트에서 "유효하지 않습니다"**  
A: 키 복사 시 공백이 없는지 확인. OpenRouter 계정 활성화 여부 확인.

**Q: "요청 시간 초과" 오류**  
A: 인터넷 연결 확인. OpenRouter 서버 상태 확인. 다시 시도.

**Q: 해석이 너무 짧아요**  
A: 시스템 프롬프트에서 max_tokens을 더 높이면 더 길어집니다. (index.html 수정 필요)

**Q: API 키가 노출됐어요**  
A: OpenRouter 대시보드에서 해당 키를 "Disable" 클릭 후 새 키 생성.

**Q: 저장된 데이터를 내보낼 수 있나요?**  
A: 브라우저 개발자 도구(F12) → Application → Local Storage → 복사

---

**더 궁금하신 점?**  
- README.md 확인
- OpenRouter 문서: https://openrouter.ai/docs
