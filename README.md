# android-gradle
[![android-gradle](http://dockeri.co/image/r0ma1n/android-gradle-docker)](https://hub.docker.com/r/r0ma1n/android-gradle-docker/)

## Included
* OpenJDK 8
* Git
* Gradle 4.10.2
* Android NDK r16b
* Android SDK (android-28)
* Android Build-tools (28.0.3)
* Android System Images(sys-img-armeabi-v7a-android-28,sys-img-armeabi-v7a-android-28)
* Android Support Libraries
* Google Play Services

## Build image

```bash
docker build -t r0ma1n/android-gradle-docker
```

## Usage

### GitLab CI

This is what my .gitlab-ci.yml looks like:

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

Change directory to your project directory, then run:

```bash
docker run --tty --interactive --volume=$(pwd):/opt/workspace --workdir=/opt/workspace --rm r0ma1n/android-gradle-docker  /bin/sh -c "./gradlew build"
```
