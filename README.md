<div align="center">

# 🌱 꿈틀

### 만다라트 기반 목표 관리 웹 서비스

> 나만의 만다라트를 작성하고, 목표 달성 과정을 한눈에 관리하세요

<br>

[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.2-6DB33F?style=flat-square&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Java](https://img.shields.io/badge/Java-21-ED8B00?style=flat-square&logo=openjdk&logoColor=white)](https://www.java.com/)
[![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Thymeleaf](https://img.shields.io/badge/Thymeleaf-005F0F?style=flat-square&logo=thymeleaf&logoColor=white)](https://www.thymeleaf.org/)
[![Google OAuth2](https://img.shields.io/badge/Google%20OAuth2-4285F4?style=flat-square&logo=google&logoColor=white)](https://developers.google.com/identity)
![Team](https://img.shields.io/badge/팀%20프로젝트-3인-FF6B6B?style=flat-square)

<br>

</div>

---

## 📖 프로젝트 소개

**꿈틀**은 만다라트(Mandalart) 기법을 활용한 목표 관리 웹 서비스입니다.

핵심 목표를 중심으로 9×9 구조의 만다라트를 작성하고, 세부 목표의 달성 여부를 체크하며 진행률을 시각적으로 확인할 수 있습니다. 구글 소셜 로그인으로 간편하게 시작할 수 있습니다.

> 💡 **만다라트(Mandalart)** 란? 핵심 목표를 중심에 두고, 이를 달성하기 위한 8가지 세부 목표를 주변에 배치하는 일본식 목표 설정 기법

<br>

## ✨ 주요 기능

| 기능 | 설명 |
|------|------|
| 🔐 **구글 소셜 로그인** | Google OAuth2 기반 간편 로그인 |
| 📝 **만다라트 작성** | 9×9 구조의 81칸 목표 입력 폼 |
| ✅ **목표 달성 체크** | 세부 목표(Cell) 완료 여부 토글 |
| 📊 **달성률 시각화** | 전체 목표 대비 완료 비율 퍼센트 표시 |
| 📅 **D-Day 카운트** | 목표 마감일(2026년 12월 31일)까지 남은 날짜 표시 |
| 🕐 **최근 활동 조회** | 최근 완료한 목표 최신 3개 표시 |
| ✏️ **만다라트 수정** | 기존 작성한 만다라트 편집 가능 |
| 📂 **카테고리 상세** | 카테고리별 세부 목표 상세 페이지 |

<br>

## 🛠️ 기술 스택

### Backend
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.2-6DB33F?style=flat-square&logo=springboot)
![Spring Security](https://img.shields.io/badge/Spring%20Security-6DB33F?style=flat-square&logo=springsecurity&logoColor=white)
![Spring Data JPA](https://img.shields.io/badge/Spring%20Data%20JPA-6DB33F?style=flat-square)
![Java](https://img.shields.io/badge/Java-21-ED8B00?style=flat-square&logo=openjdk)

### Frontend
![Thymeleaf](https://img.shields.io/badge/Thymeleaf-005F0F?style=flat-square&logo=thymeleaf)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)

### Database
![MySQL](https://img.shields.io/badge/MySQL-8-4479A1?style=flat-square&logo=mysql&logoColor=white)
![H2](https://img.shields.io/badge/H2-개발용-009DB1?style=flat-square)

### Auth
![Google OAuth2](https://img.shields.io/badge/Google%20OAuth2-4285F4?style=flat-square&logo=google&logoColor=white)

<br>

## 🗄️ 데이터베이스 구조

```
users           # 사용자 (구글 ID, 이메일, 이름)
└── mandalarts  # 만다라트 (제목, 생성일)
    └── categories  # 카테고리 블록 8개 (위치, 이름)
        └── cells   # 세부 목표 (내용, 완료 여부, 생성일)
```

<br>

## 📁 프로젝트 구조

```
src/main/java/com/kkumteul/
├── KkumTeulApplication.java
├── config/
│   └── SecurityConfig.java         # Spring Security 설정
├── controller/
│   ├── HomeController.java         # 랜딩 페이지
│   ├── MandalartController.java    # 만다라트 CRUD
│   └── MandalartApiController.java # REST API
├── domain/
│   ├── User.java
│   ├── Mandalart.java
│   ├── Category.java
│   └── Cell.java
├── repository/
│   ├── UserRepository.java
│   ├── MandalartRepository.java
│   ├── CategoryRepository.java
│   └── CellRepository.java
└── service/
    ├── MandalartService.java
    └── CustomOAuth2UserService.java
```

<br>

## 🚀 로컬 실행 방법

### 1. MySQL 데이터베이스 생성
```sql
CREATE DATABASE kkumteuldb;
```

### 2. application.yml 설정
```yaml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/kkumteuldb
    username: {your_username}
    password: {your_password}
  security:
    oauth2:
      client:
        registration:
          google:
            client-id: {your_google_client_id}
            client-secret: {your_google_client_secret}
```

### 3. 실행
```bash
./gradlew bootRun
```

<br>

## 👥 팀 구성

| 역할 | 담당 |
|------|------|
| 팀장 | 이세연 |
| 팀원 | 이나연 |
| 팀원 | 조혜인 |

> 2025 IDEA-L 동아리 프로젝트 · 3인 팀

<br>

---

<div align="center">

🌱 *꿈틀꿈틀, 목표를 향해 조금씩 나아가요*

</div>
