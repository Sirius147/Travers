# TravelMate 🌍

**TravelMate**는 여행 계획 수립, 여행 추천, 그리고 여행 기록을 관리할 수 있는 올인원 여행 어플리케이션입니다.  
사용자는 로그인하여 동행 유형, 분위기, 계절에 맞는 추천 여행지를 확인하고, 여행 계획을 세우거나 여행 중의 추억을 기록할 수 있습니다.

---

## 🛠️ 기술 스택

- **Backend**: Java, Spring Boot, JPA (Hibernate), H2 Database
- **Frontend**: Thymeleaf, Bootstrap
- **Build Tool**: Gradle
- **Deployment**: Localhost (개발 중)

---

## 📋 주요 기능

### 1. 사용자 관리
- 회원가입 및 로그인
- 로그인된 사용자별 개인화된 여행 정보 제공
- 

https://github.com/user-attachments/assets/cd82be81-fe56-469b-9749-2f596550eacf




### 2. 여행 추천
- 동행 유형 (연인, 친구, 가족)
- 여행 분위기 (활동적인, 여유로운, 특별한 경험)
- 계절별 추천 여행지와 이미지 제공



https://github.com/user-attachments/assets/a916410c-bdd2-40c9-baea-ee598ddb69ef



### 3. 여행 계획
- 여행 기간 설정
- 여행 일정 세부 입력 및 수정 가능



https://github.com/user-attachments/assets/20c15f3e-b22a-4a21-af12-39f56133a20e


### 4. 여행 기록
- 여행 중 사진 및 텍스트 기록
- 여행 기록 조회 및 삭제



https://github.com/user-attachments/assets/ab03b2ad-f4ec-4036-a8f7-2b939ac8f6d0


---

## 🚀 설치 및 실행

### 1. 저장소 클론
```bash
git clone https://github.com/Sirius147/Travers.git
cd Travers
```
### 2. 환경 설정

H2 Database는 기본적으로 설정되어 있으며, src/main/resources/application.properties에서 확인 가능합니다.


### 3. 실행
IntelliJ에서 프로젝트를 열고, jdk 및 java version 설정을 완료한 후, TraversApplication을 실행합니다.
브라우저에서 http://localhost:8080으로 접속합니다.

## 📂 디렉토리 구조

``` src/
├── main/
│   ├── java/webApp/travers/
│   │   ├── controller/   # 컨트롤러 계층
│   │   ├── domain/       # 엔티티 클래스
│   │   ├── repository/   # JPA 리포지토리
│   │   ├── service/      # 서비스 계층
│   │   └── TraversApplication.java  # 메인 실행 파일
│   ├── resources/
│   │   ├── static/       # 정적 리소스 (CSS, JS, 이미지)
│   │   ├── templates/    # Thymeleaf 템플릿
│   │   └── application.properties  # 환경 설정 파일
│   └── build.gradle       # 빌드 파일
└── test/
    └── java/webApp/travers/  # 테스트 코드
```
