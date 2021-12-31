# 빌드 오류 Execution failed for task ':app:kaptDebugKotlin'.
Room을 사용하는 안드로이드 어플리케이션에서의 빌드 오류.

## ERROR
```
Execution failed for task ':app:kaptDebugKotlin'.
> A failure occurred while executing org.jetbrains.kotlin.gradle.internal.KaptWithoutKotlincTask$KaptExecutionWorkAction
   > java.lang.reflect.InvocationTargetException (no error message)
```
<img src="https://user-images.githubusercontent.com/70834187/147829903-b5715f6a-9991-443b-92c8-6f2e43b87758.png"/>
위의 에러를 구글링해서 나온 여러 방법을 시도해보았지만 해결이 되지 않았다.

## 해결
assembleDebug로 찾은 오류 내역을 구글링하여 해결하였다.
```
Caused by: java.lang.IllegalAccessError: class org.jetbrains.kotlin.kapt3.base.KaptContext
(in unnamed module @0x20e2ffd3) cannot access class com.sun.tools.javac.util.Context (in module jdk.compiler)
because module jdk.compiler does not export com.sun.tools.javac.util to unnamed module @0x20e2ffd3
```
프로젝트 JDK 버전을 16에서 11로 다운시켰더니 빌드에 성공했다!

## assembleDebug
Terminal : gradlew assembleDebug --debug --stacktrace

## 참고
https://stackoverflow.com/questions/67509099/kapt-is-not-working-properly-with-openjdk-16
