아래는 README.md 파일의 한글 번역본입니다. 

---

# Docker 101 튜토리얼

> :warning: **이 프로젝트는 보관(아카이브)되었습니다.** 공식 "시작하기" 가이드는 [docker/getting-started](https://github.com/docker/getting-started)에서 확인할 수 있습니다.

이 튜토리얼은 컨테이너를 쉽게 시작할 수 있도록 돕기 위해 작성되었습니다. 너무 깊이 들어가지 않으면서 다음 주제를 다룹니다:

- 첫 번째 컨테이너 실행하기
- 컨테이너 빌드하기
- 실행 중인 컨테이너 확인 및 제거하기
- 볼륨을 사용해 데이터 영속화하기
- 바인드 마운트를 사용해 개발 지원하기
- 컨테이너 네트워킹으로 다중 컨테이너 애플리케이션 지원하기
- Docker Compose로 애플리케이션 정의 및 공유 간소화하기
- 이미지 레이어 캐싱으로 빌드 속도 향상 및 push/pull 용량 줄이기
- 멀티 스테이지 빌드로 빌드 타임과 런타임 의존성 분리하기

## 시작하기

튜토리얼을 실행하려면 다음 명령어를 사용할 수 있습니다:

```bash
docker run -dp 80:80 dockersamples/101-tutorial
```

실행이 완료되면 브라우저에서 [http://localhost](http://localhost) 또는 Play-with-Docker에서 80번 포트로 접속할 수 있습니다.

## 개발

이 프로젝트에는 `docker-compose.yml` 파일이 있어, mkdocs 애플리케이션을 로컬에서 실행해 변경사항을 바로 확인할 수 있습니다.

```bash
docker-compose up
```

기본적으로 개발 컨테이너는 튜토리얼의 영어 버전을 사용합니다. 다른 언어로 작업하려면 `services.docs.build.args.LANGUAGE` 값을 원하는 언어로 수정하세요. 아래 단계(새 언어 추가)가 완료되지 않았다면 빌드가 실패할 수 있습니다.

## 기여하기

튜토리얼에서 오타나 다른 문제가 발견되면 PR을 생성해 수정사항을 제안해 주세요!

튜토리얼을 더 좋게 만들거나 새로운 콘텐츠 아이디어가 있다면, 먼저 issue를 열어주세요. 다양한 의견을 환영하지만, 튜토리얼의 범위는 입문자 대상으로 제한하고자 합니다. 따라서 고급 주제는 거절될 수 있으며, 작업한 내용이 무의미하게 될 수 있으니 먼저 문의해 주세요!

### 튜토리얼 번역

튜토리얼을 다른 언어로 번역하려면 다음을 수행하세요:

1. `docs_en` 디렉터리를 복사해 `docs_[언어코드]`로 이름을 변경합니다.
2. 각 디렉터리를 번역합니다.
3. 모든 *.md 파일을 번역합니다.
4. `mkdocs-config.json`에 `[언어코드]` 키를 추가하고 나머지 설정을 완료합니다.
5. 모든 설정을 테스트하려면 `build.sh` 스크립트를 실행하면 설정 파일 검증과 모든 언어 빌드를 확인할 수 있습니다.

---

필요하다면 이 내용을 예를 들어 `README.ko.md` 파일로 저장하실 수 있습니다.



# Docker 101 Tutorial

> :warning: **This project is archived.** The official "Getting Started" guide can be found at [docker/getting-started](https://github.com/docker/getting-started).

This tutorial has been written with the intent of helping folks get up and running
with containers. While not going too much into depth, it covers the following topics:

- Running your first container
- Building containers
- Learning what containers are running and removing them
- Using volumes to persist data
- Using bind mounts to support development
- Using container networking to support multi-container applications
- Using Docker Compose to simplify the definition and sharing of applications
- Using image layer caching to speed up builds and reduce push/pull size
- Using multi-stage builds to separate build-time and runtime dependencies

## Getting Started

If you wish to run the tutorial, you can use the following command:

```bash
docker run -dp 80:80 dockersamples/101-tutorial
```

Once it has started, you can open your browser to [http://localhost](http://localhost) or
port 80 if running on Play-with-Docker.


## Development

This project has a `docker-compose.yml` file, which will start the mkdocs application on your
local machine and help you see changes instantly.

```bash
docker-compose up
```

By default, the dev container will use the English version of the tutorial. If you wish to work on
a different version, modify the `services.docs.build.args.LANGUAGE` value to the language you want
to work in. Note that the build will fail if the steps below (for new languages) haven't been
completed yet.


## Contributing

If you find typos or other issues with the tutorial, feel free to create a PR and suggest fixes!

If you have ideas on how to make the tutorial better or new content, please open an issue first 
before working on your idea. While we love input, we want to keep the tutorial is scoped to new-comers.
As such, we may reject ideas for more advanced requests and don't want you to lose any work you might
have done. So, ask first and we'll gladly hear your thoughts!


### Translating the Tutorial

If you wish to translate the tutorial into another language, you need to do the following:

1. Copy the `docs_en` directory and rename it as `docs_[your-language-code]`.
1. Translate each of the directories.
1. Translate all *.md files
1. In the `mkdocs-config.json`, add a key for `your-language-code` and fill in the
   remaining pieces to configure the mkdocs build.
1. To test everything out, you can run the `build.sh` script, which will verify the config file,
   as well as build all languages.
