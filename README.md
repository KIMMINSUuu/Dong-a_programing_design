# Software Project - Code Sharing Platform

A Site better than git

## 프로젝트 소개

이 프로젝트는 GitHub와 유사한 코드 저장소 공유 플랫폼입니다. 사용자들이 자신의 레포지토리를 생성하고, 파일을 업로드하며, 다른 사용자들과 코드를 공유할 수 있는 웹 애플리케이션입니다.

## 주요 기능

### 사용자 관리
- 회원가입 및 로그인
- 세션 기반 인증
- 사용자 프로필 관리

### 레포지토리 관리
- 레포지토리 생성 및 삭제
- 레포지토리 설명 추가
- 파일 업로드 및 관리
- README.md 자동 생성

### 공유 및 검색
- 인기 레포지토리 조회 (조회수 기반)
- 레포지토리 상세 정보 보기
- 최근 조회한 레포지토리 추적
- 파일 업로드 및 다운로드

### 게시판 기능
- 게시글 작성, 수정, 삭제
- 게시글 목록 조회

## 기술 스택

### Backend
- **Node.js** - 서버 런타임 환경
- **Express.js** - 웹 프레임워크
- **MySQL** - 데이터베이스

### Frontend
- **EJS** - 템플릿 엔진
- **CSS** - 스타일링
- **JavaScript** - 클라이언트 사이드 로직

### 주요 라이브러리
- `express-session` - 세션 관리
- `mysql2` - MySQL 데이터베이스 연결
- `multer` - 파일 업로드 처리
- `body-parser` - 요청 본문 파싱
- `dotenv` - 환경 변수 관리

## 프로젝트 구조

```
Dong-a_programing_design/
├── app.js                 # 메인 애플리케이션 파일
├── package.json           # 프로젝트 의존성 및 스크립트
├── .env                   # 환경 변수 (DB 연결 정보 등)
├── routes/                # 라우트 핸들러
│   ├── share.js          # 공유 페이지 라우트
│   ├── home.js           # 홈/내 레포지토리 라우트
│   ├── login.js          # 로그인 라우트
│   ├── register.js       # 회원가입 라우트
│   ├── logout.js         # 로그아웃 라우트
│   ├── post.js           # 게시글 라우트
│   ├── repo.js           # 레포지토리 목록 라우트
│   ├── repoDetail.js     # 레포지토리 상세 라우트
│   ├── index.js          # 인덱스 라우트
│   └── guide.js          # 가이드 라우트
├── views/                 # EJS 템플릿 파일
│   ├── share.ejs         # 공유 페이지
│   ├── home.ejs          # 홈 페이지
│   ├── login.ejs         # 로그인 페이지
│   ├── register.ejs      # 회원가입 페이지
│   ├── repo.ejs          # 레포지토리 목록
│   ├── repoDetail.ejs    # 레포지토리 상세
│   ├── post.ejs          # 게시글 페이지
│   ├── postList.ejs      # 게시글 목록
│   ├── postNew.ejs       # 새 게시글 작성
│   ├── postEdit.ejs      # 게시글 수정
│   └── guide.ejs         # 가이드 페이지
└── public/                # 정적 파일
    ├── css/              # 스타일시트
    ├── js/               # 클라이언트 JavaScript
    ├── images/           # 이미지 파일
    └── fonts/            # 폰트 파일
```

## 설치 및 실행 방법

### 1. 필수 요구사항
- Node.js (v14 이상)
- MySQL (v5.7 이상)

### 2. 프로젝트 클론
```bash
git clone <repository-url>
cd Dong-a_programing_design
```

### 3. 의존성 설치
```bash
npm install
```

### 4. 환경 변수 설정
`.env` 파일을 생성하고 다음 내용을 추가하세요:
```env
PORT=3000
DB_HOST=localhost
DB_USER=your_mysql_username
DB_PASSWORD=your_mysql_password
DB_DATABASE=your_database_name
```

### 5. 데이터베이스 설정
MySQL에서 필요한 테이블을 생성해야 합니다:
- `users` - 사용자 정보
- `repo` - 레포지토리 정보
- `file` - 파일 정보
- `recent_view` - 최근 조회 기록
- 게시판 관련 테이블

### 6. 서버 실행
```bash
npm start
```

서버가 시작되면 `http://localhost:3000`에서 애플리케이션에 접근할 수 있습니다.

## 주요 라우트

| 경로 | 설명 |
|------|------|
| `/` | 메인 페이지 (인기 레포지토리) |
| `/login` | 로그인 페이지 |
| `/register` | 회원가입 페이지 |
| `/logout` | 로그아웃 |
| `/myrepo` | 내 레포지토리 관리 |
| `/repo` | 레포지토리 목록 |
| `/repoDetail` | 레포지토리 상세 정보 |
| `/post` | 게시판 |
| `/guide` | 사용 가이드 |

## 개발 정보

- **Version**: 1.0.0
- **Main File**: app.js
- **Start Script**: `npm start`

## 데이터베이스 구조

### repo 테이블
- `Id` - 레포지토리 고유 ID
- `Name` - 레포지토리 이름
- `Owner_id` - 소유자 ID
- `Description` - 레포지토리 설명
- `Views` - 조회수
- `Updated` - 최종 수정일

### recent_view 테이블
- `user_id` - 사용자 ID
- `post_id` - 레포지토리 ID
- `viewed_at` - 조회 시간

## 기여하기

이 프로젝트는 동아대학교 프로그래밍 설계 과목의 일환으로 개발되었습니다.

## 라이선스

이 프로젝트의 라이선스 정보는 별도로 명시되어 있지 않습니다.
