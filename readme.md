## 알아두기
- gradle 버전은 6.8
  - 그러므로 jdk 최소 버전은 8
  - jdk 버전 변경 혹은 설치 대신 docker로 jdk 8 버전 이용하는게 편리
- gradle 빌드도 `gradlew` 사용하여 gradle 버전에 종속적이지 않게 처리한다.
- multi-stage 빌드를 이용하여 어플리케이션 실행은 jre 8 버전 환경에서 한다.
- gradle 빌드 할 때 less를 compile 하지 못한다. 그냥 maven 산출물을 갖다 넣었다.

## 컨테이너 이미지
- `docker build -t <name>:<version> .`명령으로 빌드한다.
  - `<name>`, `<version>`은 사용자의 환경에 맞게 구성한다.
  - `<name>` 기본값으로 `euffk/petclinic`, `<version>` 기본값으로 `0.0.1` 사용
- ENTRYPOINT는 `/usr/bin/java` CMD로 jar파일 넘겨 준다.
