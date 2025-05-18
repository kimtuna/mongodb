# MongoDB Docker 설정

이 프로젝트는 Docker를 사용하여 MongoDB를 설정하는 방법을 제공합니다.

## 사전 요구사항

- Docker
- Docker Compose

## 설정 방법

1. `.env` 파일 생성
   ```bash
   cp .env.example .env
   ```

2. `.env` 파일에서 다음 환경 변수들을 설정:
   - `MONGO_ROOT_USERNAME`: MongoDB 루트 사용자 이름
   - `MONGO_ROOT_PASSWORD`: MongoDB 루트 비밀번호
   - `MONGO_PORT`: MongoDB 포트 (기본값: 27018)

3. Docker 컨테이너 실행
   ```bash
   docker-compose up -d
   ```

## 연결 정보

- 호스트: localhost
- 포트: .env 파일에 설정된 MONGO_PORT (기본값: 27018)
- 사용자 이름: .env 파일에 설정된 MONGO_ROOT_USERNAME
- 비밀번호: .env 파일에 설정된 MONGO_ROOT_PASSWORD

## 데이터 영속성

MongoDB 데이터는 Docker 볼륨 `mongodb_data`에 저장되어 컨테이너가 재시작되어도 유지됩니다.

## 컨테이너 관리

- 컨테이너 중지:
  ```bash
  docker-compose down
  ```

- 로그 확인:
  ```bash
  docker-compose logs -f
  ```

- 컨테이너 재시작:
  ```bash
  docker-compose restart
  ``` 