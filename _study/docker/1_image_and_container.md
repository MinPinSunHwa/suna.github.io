---
title: "도커 이미지와 도커 컨테이너"
permalink: /study/docker/1/
comments: true
categories: []
toc: true
---

**Reference**

- 도커/쿠버네티스를 활용한 컨테이너 개발 실전 입문 , 야마다 아키노리 지음 , 심효섭 옯김
<br><br>

---

# Docker Image is ...

- 도커 컨테이너를 만들기 위한 **템플릿**

- 우분투 같은 운영 체제로 구성된 파일 시스템은 물론, 컨테이너 위에서 실행하기 위한 애플리케이션이나 그 의존 라이브러리, 도구에 어떤 프로세스를 실행할지 등의 실행 환경의 설정 정보까지 포함하는 아카이브

- `Dockerfile`은 이미지를 구성하는 순서를 기술한 코드이므로 `Dockerfile` 자체가 이미지라고 할 수 없음

- 컨테이너의 템플릿 역할을 하는 이미지를 만드는 과정을 **도커 이미지를 빌드한다**고 함

---

# Docker Image Build ...

```
docker image build -t 이지미명[:태그명] Dockerfile_경로
```

- `Dockerfile`이 현재 작업 디렉터리에 있다면 `.`을 입력함

  ```
  $ docker image build -t example/echo:latest .
  ```

- `f` 옵션
