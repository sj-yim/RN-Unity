# RN-Unity

## 1. Unity
빌드 세팅 - Export Project 체크

## 2. RN 폴더에 붙혀넣기
export된 유니티 파일들을 RN-Unity/EmptyRN/unity/builds/android로 복사하기

## 3. Unity 파일 복사
RN-Unity/EmptyRN/unity/builds/android/unityLibrary/libs/ 하위 파일들을 RN-Unity/EmptyRN/android/app/libs로 복사

## 4. Unity 파일 수정
### RN-Unity/EmptyRN/unity/builds/android/unityLibrary/src/main/AndroidManifest.xml

< intent-filter> ... </ intent-filter> 태그 삭제

android:icon="@mipmap/app_icon" 

android:theme="@style/UnityThemeSelector" 삭제 (없을 수도 있음)

## 5. RN-Unity/EmptyRN/unity/builds/android/unityLibrary/build.gradle

//    implementation(name: 'native-toolkit', ext:'aar')

//    implementation(name: 'support-compat-27.1.1', ext:'aar')

//    implementation(name: 'support-v4-27.1.1', ext:'aar')

주석처리 / 삭제 (유니티 버전에따라 없을 수도 있음)

## 6. RN-Unity/EmptyRN/android/app/src/main/ 디렉토리에 "assets" 폴더 생성

## 7. RN-Unity/EmptyRN/android/app/src/res/ 디렉토리에 "drawables" 폴더 삭제

## 8. 터미널에서 다음 실행
react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res/

## 9. 빌드 실행
npm run android 혹은 npx react-native run-android



## 오류

1. 라이선스 에러

안드로이드 스튜디오에서 Google Play Licensing Library 설치 후 license 폴더를
/Applications/Unity/Hub/Editor/2021.1.16f1/PlaybackEngines/AndroidPlayer/SDK 로 복사

2. NDK 버전 불일치 에러 (하나씩 적용)

- RN-Unity/EmptyRN/android/build.gradle 에서 ndk 버전 21.3.6528147로 수정
- local.properties 에서 ndk.dir=/Applications/Unity/Hub/Editor/2022.1.0b16/PlaybackEngines/AndroidPlayer/NDK  Unity/Hub/Editor/ 안에있는 폴더 이름 확인 후 다를 시 변경
- local.properties 에서 ndk.dir=/Applications/Unity/Hub/Editor/2022.1.0b16/PlaybackEngines/AndroidPlayer/NDK 21.3.6528147버전 ndk 다운로드 받아서 붙혀넣기
- Android Studio 프로젝트 설정 확인
