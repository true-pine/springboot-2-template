## clone 후 해야할 것

1. `.git` 폴더 삭제
2. 프로젝트 명 수정
3. 패키지 명 수정

## Lombok 의존성 추가

### 1. build.gradle 수정

```groovy
...

java {
    sourceCompatibility = '11'
}

configurations {    // 추가 
    compileOnly {
        extendsFrom annotationProcessor
    }
}

...

dependencies {
    ...
    compileOnly 'org.projectlombok:lombok'  // 추가
    annotationProcessor 'org.projectlombok:lombok'
    
    testCompileOnly 'org.projectlombok:lombok'  // 테스트에서 lombok 사용
    testAnnotationProcessor 'org.projectlombok:lombok'
    ...
}
```

### 2. Preferences 설정

1. Build, Execution, Deployment > Compiler > Annotation Processors > Enable annotation processing 활성화
2. Plugins > Lombok 설치 및 활성화 > IDE 재시작

## 의존성 추가 목록

```groovy
// 타임리프
implementation 'org.springframework.boot:spring-boot-starter-thymeleaf'

// web
implementation 'org.springframework.boot:spring-boot-starter-web'
```