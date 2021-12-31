## java.lang.NoClassDefFoundError: Could not initialize class org.codehaus.groovy.vmplugin.v7.Java7
안드로이드 스튜디오에서 옛날에 만든 프로젝트를 오픈 하였더니 위의 에러가 발생하였다.

## 해결
gradle버전이 낮을때 발생하는 에러이다. jdk 14 이상에서는 6.3 이상의 gradle 버전을 사용해야한다.<br>
프로젝트의 gradle버전을 6.3 이상으로 올려서 해결하였다.

#### 1. gradle-wrapper.properties 파일의 distributionUrl을 수정한다.
```
distributionUrl=https\://services.gradle.org/distributions/gradle-6.3-bin.zip 
```
#### 2. clean project 후 rebulid

## 참고
https://velog.io/@dskim-code/NoClassFound
