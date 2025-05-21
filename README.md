# youtube-search-webapp
YouTube API 기반 동영상 검색 웹 애플리케이션
# YouTube API 기반 동영상 검색 웹 애플리케이션

이 프로젝트는 YouTube Data API v3와 FastAPI, HTML을 활용하여 키워드 기반 유튜브 영상 검색 기능을 제공하는 웹 애플리케이션입니다.  
사용자가 검색어를 입력하면 관련된 유튜브 동영상 정보를 실시간으로 받아와 출력합니다.

---

## 주요 기능

- 키워드 입력 기반 유튜브 동영상 검색
- 검색 결과에 제목, 썸네일, 설명, 채널명, 게시일, 링크 포함
- FastAPI 서버에서 YouTube API 호출 후 결과 렌더링
- HTML(Jinja2 템플릿) 기반 프론트엔드
- API 오류 및 검색 실패 시 예외 처리 포함

---

## 기술 스택

- **백엔드**: Python, FastAPI, requests
- **프론트엔드**: HTML, CSS, Jinja2
- **API**: YouTube Data API v3
- **실행환경**: 로컬 또는 Google Colab + ngrok

---

## 프로젝트 폴더 구조
├── main.py              # FastAPI 서버 파일

├── templates/

│   └── index.html       # HTML 템플릿

├── static/              # 정적 파일 (필요시)

└── requirements.txt     # 패키지 목록

---

## 실행 방법

### 1. 패키지 설치
pip install fastapi uvicorn jinja2 requests

### 2. YouTube API 키 발급 및 설정

- Google Cloud Console에서 API 키 발급
- main.py 파일 내 `YOUTUBE_API_KEY = "YOUR_API_KEY"` 부분 수정

### 3. 서버 실행
uvicorn main:app –reload

### 4. ngrok (Colab 환경일 경우)

```python
from pyngrok import ngrok
ngrok.set_auth_token("YOUR_NGROK_TOKEN")
ngrok.connect(8000)
