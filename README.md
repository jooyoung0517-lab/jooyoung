# 🚀 개발 워크스테이션 구축 및 웹 서버 배포 프로젝트

![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=for-the-badge&logo=docker&logoColor=white)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E9433F?style=for-the-badge&logo=ubuntu&logoColor=white)
![GitHub](https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white)

이 프로젝트는 Docker, Git, 그리고 Ubuntu(WSL2) 환경을 활용하여 기본적인 개발 워크스테이션을 구축하고, 간단한 웹 서버를 컨테이너화하여 배포하는 과정을 담고 있습니다.

## 🛠 사용 기술 및 환경
- **OS**: Windows 11 (WSL2 - Ubuntu 22.04 LTS)
- **Tools**: Docker Desktop, VSCode, Git
- **Language/Server**: HTML, Nginx (Docker Image)

## 📂 프로젝트 구조
```text
.
├── index.html          # 웹 서버 메인 페이지
├── Dockerfile          # Docker 이미지 빌드 설정
├── result.png          # 실행 결과 캡처 이미지
└── README.md           # 프로젝트 문서
```

## ⚙️ 실행 방법
1. 도커 이미지 빌드
`docker build -t my-web-server .`

2. 도커 컨테이너 실행
`docker run -d -p 8081:80 my-web-server`
브라우저에서 `localhost:8081` 로 접속하여 확인합니다.

## 📸 실행 결과
![웹 서버 실행 결과](./result.png)

## 🔍 트러블슈팅 및 해결
1. Docker 권한 문제 (Permission Denied)
문제: Ubuntu 환경에서 docker ps나 빌드 시 권한 오류 발생.
원인: 기본적으로 Docker 데몬은 root 권한이 필요함.
해결: /var/run/docker.sock 파일의 권한을 변경하여 해결.
```
sudo chmod 666 /var/run/docker.sock
```

2. GitHub Push 인증 실패 문제 (Problem): git push 실행 시 GitHub 아이디와 비밀번호를 입력했으나 Authentication failed 오류가 발생하며 권한 거부됨.
원인 가설 (Hypothesis): GitHub의 보안 정책 변경으로 인해 일반 계정 비밀번호로는 터미널에서 인증할 수 없고, 별도의 토큰(PAT)이 필요할 것으로 추측함.
확인 (Verification): GitHub 공식 문서 및 에러 메시지를 확인한 결과, 2021년부터 비밀번호 인증 지원이 중단되었음을 확인.
해결/대안 (Solution): GitHub 계정 설정(Developer Settings)에서 **Personal Access Token (Classic)**을 생성하고, 권한(repo)을 부여한 뒤 비밀번호 대신 토큰 값을 입력하여 인증 성공.

## 🎓 주요 학습 내용

- **WSL2 & Ubuntu**: 윈도우 환경에서 리눅스 개발 환경을 구축하는 법을 익힘.

- **Docker**: Dockerfile을 작성하여 나만의 웹 서버 이미지를 만들고 컨테이너화함.

- **Git & GitHub**: 로컬 작업물을 원격 저장소에 관리하고 협업 환경을 이해함.

- **VSCode Remote**: WSL2와 VSCode를 연동하여 효율적인 개발 워크플로우를 구축함.

- **바인드 마운트 실습**:
    - **목적**: 호스트와 컨테이너의 디렉토리를 연결하여 소스 코드 수정 시 실시간 반영 확인
    - **명령어**: `docker run -d -p 8082:80 -v "$(pwd):/usr/share/nginx/html" --name web-mount nginx`
    - **결과**: `index.html` 수정 후 새로고침 시 즉각 반영됨 (성공)