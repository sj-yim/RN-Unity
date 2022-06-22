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

### RN-Unity/EmptyRN/unity/builds/android/unityLibrary/build.gradle

//    implementation(name: 'native-toolkit', ext:'aar')

//    implementation(name: 'support-compat-27.1.1', ext:'aar')

//    implementation(name: 'support-v4-27.1.1', ext:'aar')

주석처리 / 삭제

