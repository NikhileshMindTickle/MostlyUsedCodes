To trigger build
```
git commit -m "something"
git tag dev-build-1.1.3
git push origin your-branch
```
Add this as travis file(.travis.yml) to root folder of project to build android project.
```
language: android
sudo: required
#os: [linux]
dist: trusty

env:
  global:
    - ANDROID_API=29
    - ANDROID_BUILD_TOOLS_VERSION=29.0.3
    - EMULATOR_API=29
    - EMULATOR_ABI=armeabi-v7a

branches:
  only:
    - master

android:
  components:
    - platform-tools
    - tools
    - build-tools-$ANDROID_BUILD_TOOLS_VERSION
    - android-$ANDROID_API
    - extra-google-google_play_services
    - extra-google-m2repository
    - extra-android-m2repository
    - addon-google_apis-google-$ANDROID_API
    - extra-android-support
    - sys-img-x86-android-$ANDROID_API


before_install:
  - yes | sdkmanager "platforms;android-$ANDROID_API"

script:
    - ./gradlew assembleDebug

deploy:
  provider: releases
  api-key: $GITHUB_API_KEY
  file: $TRAVIS_BUILD_DIR/app/build/outputs/apk/debug/app-1.0-debug.apk
  skip_cleanup: true
  name: dev-build-$USER-$TRAVIS_TAG
  body: Automatic build of $TRAVIS_BRANCH ($TRAVIS_COMMIT) built by Travis CI on $(date +'%F %T %Z').
  prerelease: true
  overwrite: true
  target_commitish: $TRAVIS_COMMIT
#  on:
#    tags: true

after_deploy:
  - rm -rf $TRAVIS_BUILD_DIR/app/build/outputs
```




Deploy travis apk to github releases
```
Go to Github -> Settings -> Developer Settings -> Personal access tokens -> Generate New Token
Token Name - travis(You can keep any)
Select - repo it will tick all repo:status,repo_deployment,public_repo,repo:invite,security_events

Now go to travis -> Go to Project Settings -> In Environment Variables -> 
Name - GITHUB_API_KEY
Value - your key
Branches - All branches(Its your choice)


Now add this to your travis file
deploy:
  provider: releases
  api-key: $GITHUB_API_KEY
  file: $TRAVIS_BUILD_DIR/app/build/outputs/apk/debug/app-1.0-debug.apk
  skip_cleanup: true
  name: dev-build-$USER-$TRAVIS_TAG
  body: Automatic build of $TRAVIS_BRANCH ($TRAVIS_COMMIT) built by Travis CI on $(date +'%F %T %Z').
  prerelease: true
  overwrite: true
  target_commitish: $TRAVIS_COMMIT
  on:
    tags: true

after_deploy:
  - rm -rf $TRAVIS_BUILD_DIR/app/build/outputs
```
