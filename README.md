# 🚀 개발 워크스테이션 구축 및 웹 서버 배포 프로젝트

이 프로젝트는 Docker, Git, 그리고 Ubuntu(WSL2) 환경을 활용하여 기본적인 개발 워크스테이션을 구축하고, 간단한 웹 서버를 컨테이너화하여 배포하는 과정을 담고 있습니다.

## 🛠 사용 기술 및 환경
- **OS**: Windows 11 (WSL2 - Ubuntu 22.04 LTS)
- **Tools**: Docker Desktop, VSCode, Git
- **Language/Server**: HTML, Nginx (Docker Image)

## 📂 프로젝트 구조
- `index.html`: 사용자에게 보여지는 메인 웹 페이지
- `Dockerfile`: Nginx 이미지를 기반으로 한 웹 서버 설정 파일

## ⚙️ 실행 방법

### 1. 도커 이미지 빌드
```bash
docker build -t my-web-server .

