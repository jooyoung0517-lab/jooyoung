# 개발 워크스테이션 구축 및 웹 서버 배포 프로젝트

## 1. 프로젝트 구조 (#10 관련)
- 현재 작업 디렉토리의 구조입니다.
```text
practice/
├── Dockerfile        # 커스텀 웹 서버 이미지를 빌드하기 위한 설정 파일
├── index.html        # 웹 서버에 표시될 메인 페이지
└── README.md         # 프로젝트 문서 및 실습 기록

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/

 ## 🐳 Docker 실습 완료
- Nginx를 이용한 웹 서버 구축 성공
- Dockerfile 작성 및 이미지 빌드 완료
- 컨테이너 실행 및 브라우저 확인 완료 (localhost:8080)