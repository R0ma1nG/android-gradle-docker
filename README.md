# android-gradle
[![android-gradle](http://dockeri.co/image/r0ma1n/android-gradle-docker)](https://hub.docker.com/r/r0ma1n/android-gradle-docker/)

## Included
* OpenJDK 8
* Git
* Gradle 4.10.2
* Android NDK r16b
* Android SDK (android-28)
* Android Build-tools (28.0.3)
* Android System Image(sys-img-x86-android-28)
* Android Support Libraries
* Google Play Services

## Build image

```bash
docker build -t r0ma1n/android-gradle-docker
```

## Usage

### GitLab CI

```yaml
image: r0ma1n/android-gradle-docker
stages:
  - build

build:
  stage: build
  script:
    - gradlew build
  only:
    - master

```

### Without GitLab

```bash
docker pull r0ma1n/android-gradle-docker
```
