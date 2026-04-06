# 🔮 타로 리더 (Tarot Reader)

OpenRouter의 AI 모델을 활용한 웹 기반 타로 리딩 사이트입니다. 타로 카드 정보를 입력하면 AI가 심층적인 해석을 제공하고, 결과를 로컬에 보관할 수 있습니다.

## 🌟 주요 기능

- **AI 기반 타로 해석** - OpenRouter API를 통해 GPT-4o Mini, Mistral Small 등의 모델 지원
- **유연한 입력 방식** - Yes/No 타로, 스프레드, 자유 형식 등 모든 형태 지원
- **해석 히스토리 저장** - 로컬 스토리지에 리딩 결과 자동 저장
- **모바일 친화적 UI** - 반응형 디자인으로 모든 기기에 최적화
- **API 키 관리** - 안전하게 API 키 저장 및 검증 기능

## 🚀 시작하기

### 1. 프로젝트 열기
브라우저에서 `index.html` 파일을 열면 됩니다.

```bash
# VS Code에서 Live Server 사용 권장
# (확장 프로그램: Live Server by Ritwick Dey)
```

### 2. API 키 설정

1. [OpenRouter](https://openrouter.ai) 가입 및 로그인
2. API 키 생성 (대시보드 > API Keys)
3. 애플리케이션의 "OpenRouter API Key" 입력란에 붙여넣기
4. **테스트** 버튼 클릭하여 키 검증

### 3. 타로 리딩 시작

1. AI 모델 선택 (GPT-4o Mini / Mistral Small)
2. 타로 내용 입력
   - Yes/No 결과
   - 카드 이름과 정/역방향
   - 질문이나 주제
3. **카드 해석하기** 버튼 클릭
4. AI의 해석 결과 확인
5. **보관함에 저장** 클릭하여 히스토리 관리

## 📋 입력 예시

### Yes/No 타로
```
질문: 내가 이번 프로젝트를 성공할 수 있을까?
1. 황제 (정방향) → YES
2. 죽음 (정방향) → NO  
3. 힘 (정방향) → YES

이 결과를 심층 해석해주세요.
```

### 4카드 스프레드
```
4카드 스프레드 (이번 달 운세)

1. The Magician - 현재 상황
2. The Hermit - 내적 변화
3. The Star - 기대감
4. The World - 결과

주제: 커리어 방향
```

### 자유 형식
```
3장의 카드가 나왔어:
The Moon, The Chariot, Queen of Swords (역방향)

연애 관계에 대해 배웠던 타로 스프레드 형식이야.
어떤 의미가 있을까?
```

## 🛠️ 개선 사항

현재 버전에 적용된 보안 및 UX 개선사항:

✅ **AbortController** - 요청 진행 중 취소 가능  
✅ **API 키 검증 버튼** - 저장 전 테스트로 오류 미리 방지  
✅ **타임아웃 설정** - 느린 연결에서 불필요한 대기 방지  
✅ **중복 코드 리팩토링** - `getApiKey()`, `getModel()` 헬퍼 함수 제공

## 🔒 보안 주의사항

- **API 키는 로컬 스토리지에 저장**됩니다. 공용 기기에서는 사용하지 마세요.
- 프로덕션 환경에서는 **백엔드 서버를 거쳐** API 호출을 하기를 권장합니다.
- API 키 노출 시 OpenRouter 대시보드에서 바로 비활성화하세요.

## 💾 데이터

### 로컬 스토리지
- `tarot_readings_v2` - 리딩 히스토리 (JSON 배열)
- `tarot_api_key` - API 키 (평문)

브라우저 개발자 도구($Application → Local Storage)에서 확인/삭제 가능합니다.

## 📱 기술 스택

- **Frontend**: HTML5, CSS3, Vanilla JavaScript (의존성 없음)
- **API**: OpenRouter (GPT-4o Mini, Mistral Small 등)
- **Storage**: Browser LocalStorage
- **Design**: Custom CSS (시스템 디자인 inspired)

## 🎨 커스터마이징

### 모델 변경
`index.html`의 `MODELS` 배열 수정:
```javascript
const MODELS = [
  { id:"gpt-모델-id", label:"모델명", desc:"설명", icon:"🔯" },
  // 추가 모델...
];
```

### 시스템 프롬프트 수정
`SYSTEM_PROMPT` 변수를 편집하여 AI의 성격/스타일 커스터마이징 가능.

### 스타일 수정
CSS `:root` 변수로 컬러, 폰트, 간격 조정 가능:
```css
:root {
  --accent: #7C6DC7; /* 주 색상 */
  --font-body: 'Noto Sans KR'; /* 기본 폰트 */
}
```

## 🐛 문제 해결

| 증상 | 해결 방법 |
|------|---------|
| API 키 테스트 실패 | 키가 올바른지, OpenRouter 계정이 활성화되어 있는지 확인 |
| "요청 시간 초과" | 인터넷 연결 확인, OpenRouter 서버 상태 확인 |
| 해석 결과가 없음 | API 할당량 확인, 모델 이름 정확성 확인 |
| 저장된 리딩이 없음 | 브라우저 개발자 도구에서 로컬 스토리지 확인 |

## 📞 지원

- [OpenRouter 문서](https://openrouter.ai/docs)
- [OpenRouter 한국 커뮤니티](https://openrouter.ai)

---

**v1.1.0** - 개선 사항 적용 버전  
마지막 업데이트: 2026년 4월
