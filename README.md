# 토닥
> 반려인의 병원 방문 번거로움을 해결하기 위한 비대면 의료 서비스
# 🏆프로젝트 성과
공통프로젝트 웹디자인부분 우수상 수상(2등)🥈

![alt text](images/mainpage.png)

# 📜 목차
- [서비스 개요](#서비스-개요)
- [주요 기능](#주요-기능)
- [담당 역할](#담당-역할)
- [기술 스택](#기술-스택)
- [기술 선정 이유 및 문제 해결](#기술-선정-이유-및-문제-해결)
- [아키텍처 구성](#아키텍처-구성)
- [폴더 구조](#폴더-구조)
- [팀원 소개](#팀원-소개)


# 📝서비스 개요
WebRTC 기술을 이용한 반려인들을 위한 반려동물 **비대면 의료 서비스**입니다.

###  페르소나
**구름이를 키우는 반려인 '이반려'**
 - **문제점** : 
    - 약물 투여시기 결정을 위해 병원에서 주기적인 관찰 진료가 필요
    - 병원에 대한 스트레스가 높음
- **필요한 점** :
    - 병원에 방문하지 않고 관찰 진료 필요
    - 시간, 공간에 제약 없이 진료 필요

# ⚡주요 기능
> 토닥은 반려인, 수의사 , 병원 관계자 3가지의 사용자 유형이 존재
<div class=flex>
<img width="200" height="658" alt="반려인 홈" src="images/반려인 홈.png" />
<img width="200" height="658" alt="수의사 홈" src="images/수의사 홈.png" />
<img width="200" height="658" alt="병원관계자 홈" src="images/병원관계자 홈.png" />
</div>


## 1. 반려인
### 반려동물 관리
- **프로필 등록** : 반려동물의 정보를 프로필 형태로 등록하여 정보 열람 및 관리
<div class = "flex">
<img src="/images/동물등록1.gif" alt="예약 신청1" width="200" height="658">
<img src="/images/동물등록2.gif" alt="예약 신청2" width="200" height="658">
<img src="/images/동물등록3.gif" alt="예약 신청3" width="200" height="658">
</div>

  
### 진료 내역 조회
- **예약 요약 제공** : 작성했던 진료 신청서 내용을 요약해 어떤 진료 내역인지 한눈에 확인 가능
- **AI 요약 진단서** : 수의사의 검증을 거친 AI 요약 진단서 보관
<img src="/images/진료내역상세.gif" alt="예약 시간 설정 1" width="200">

### 예약 신청
- **신청서 작성** : 원하는 병원과 수의사를 검색 후 선택하고, 증상 입력
- **자동 결제 수단 선택** : 카카오페이 결제를 통해 예약을 확정하고 승인 대기 상태로 전환
<div class = "flex">
<img src="/images/예약 신청1.gif" alt="예약 신청1" width="200" height="658">
<img src="/images/예약 신청2.gif" alt="예약 신청2" width="200" height="658">
<img src="/images/예약 신청3.gif" alt="예약 신청3" width="200" height="658">
</div>

## 2. 수의사
### 비대면 진료
- **실시간 1:1진료** : Kurento 기반 WebRTC 기술을 활용하여 원격 화상 진료 지원
<div class = "flex">
<img src="/images/비대면진료1.gif" alt="비대면진료1" width="245">
<img src="/images/비대면진료2.gif" alt="비대면진료2" width="200">
</div>

### 진단서 검토
- **STT → text 변환** : Whisper-1을 이용해 비대면 진료 중 음성을 텍스트 파일로 변환
- **AI text 요약** : 의료 용어가 많은 텍스트를 ChatGPT 4.1을 통해 핵심 내용 요약
- **수의사 검증** : 수의사의 검토 절차를 통해 수정, 승인
<img src="/images/진료내역상세.gif" alt="수의사진료상세" width="200">

## 3. 병원 관계자
### 진료 일정 관리
- **예약 시간 설정** : 버튼 토클 방식으로 진료 가능/불가 시간 설정
<div class = "flex">
<img src="/images/예약 시간 설정 1.gif" alt="예약 시간 설정 1" width="200">
<img src="/images/예약 시간 설정 2.gif" alt="예약 시간 설정 2" width="200">
</div>

### 예약 관리
- **신청 목록 확인** : 전체 예약 내역을 조회하고, 내용을 검토한 뒤 승인 또는 반려 처리 가능
<div class = "flex">
<img src="/images/예약승인.gif" alt="예약 승인" width="200" height="658">
<img src="/images/예약반려.gif" alt="예약 반려" width="200" height="658">
</div>

### 결제 관리
- **수납** : 진료 종료 후 결제 금액 입력 → 자동 결제 요청
<img src="/images/원무.gif" alt="예약 시간 설정 1" width="200">

# 🙋담당 역할
- **Kurento 미디어 서버**를 이용한 비대면 진료화면 구현
- **카카오페이 API를 활용**한 결제 서비스 구현
- 백엔드 서버 RestAPI 작성
- 프론트엔드 자문 및 배포를 위한 **CI/CD 파이프라인 구축 및 운영**

# 🛠기술 스택

### Frontend
- Language: TypeScript
- Framework: React 19
- UI/스타일링: TailwindCSS
- 상태 관리: Zustand
- 라우팅: React Router Dom
- 개발 도구: Vit

### Backend

- Language: Java 17
- Framework: Spring Boot 3.3.3
- Database: MySQL, Redis, Elasticsearch
- ORM: Spring Data JPA
- 인증/보안: JWT (jjwt), Spring Security
- 메시징 서비스: RabbitMQ
- API 문서화: Swagger
- 웹소켓: Spring WebSocket
- 개발 도구: Lombok, Devtools
- AI : GMS

### Infra 
- Containerization: Docker
- CI/CD: Jenkins
- Cloud: AWS ,S3 Bucket

# 🔧기술 선정 이유 및 문제 해결
### Kurento 미디어 서버
- Web RTC기능을 P2P 방식이 아닌 미디어 서버를 거쳐서 관리하기 위해서 사용했습니다. 이렇게 미디어 서버를 통해서 관리하면 녹음, 녹화 같은 추가 기능을 적용하기 수월합니다. 보통 더 편한 OpenVidu미디어 서버를 많이 사용하지만, AI가 요약 및 분석하여 진단서를 뽑아주는 기능을 위해서 서비스에서 수의사 음성을 이용해서 STT로 뽑아내야했습니다. 이러한 특수한 미디어 파이프라인을 직접 구현하기 위해서 Kurento를 사용하였습니다.

### Redis
- 예약 내역을 입력한 이후에 카카오페이를 등록하게 Flow를 짰습니다. 이 과정에서 예약내역을 미리 Redis에 저장하고, 정상적으로 등록 된 이후에 DB에 저장하도록 만들었습니다.
또한, 자동결제 등록을 위해 카카오페이에서 임시로 전달하는 key값을 redis에 잠시 저장한 후 사용하기 위해서 redis를 적용하였습니다.

### Elasticsearch
- 서비스에서 병원들을 이름으로 검색하는 기능을 구현했습니다. 이 과정에서 한 글자 한 글자가 완성되면 자동완성하여 보여주도록 했습니다. 이 때, 단순 DB에서 LIKE로 검색할 경우 검색 시간이 오래 걸리는데, 이러한 자동검색이 매우 빈번하게 요청되고 Connection pool에도 부담이 되기 때문에 ElasticSearch를 적용하였습니다.

### RabbitMQ
- AI진단서를 위해서 수의사의 음성을 Text로 뽑은 뒤, AI에 요청을 보내게 되는데 이 때, 트래픽이 몰려서 AI 요약 및 분석이 실패할 경우 재시도를 자동으로 관리하기 위해서 적용하였습니다.

## ⚙️문제 해결 사례
### 예약 상세내역 저장방식
- 저희 서비스에서는 예약신청을 작성할 때, 증상 사진을 넣어주도록 구현했습니다. 이 과정에서 MultipartFile 타입으로 사진을 서버에서 받아서 S3에 저장하게 되는데, 이 때 작성한 정보가 카카오페이를 등록한 이후에 서버에 전달되어야 했습니다. 하지만, 외부 API인 카카오페이를 등록하게 되면 URL이 바뀌게 되어서 이러한 정보를 React에서 유지할 수 없는 이슈가 있었습니다.
이를 해결하기 위해서 File형식으로 저장했다가 다시 MultipartFile로 바꾸는 방식을 고려했는데, MultipartFile은 Http 요청으로만 전달이 되는 타입이었기 때문에 변환에 어려움이 있었습니다. 그래서 Redis에 DB에 저장되는 정보 그대로를 Redis에 저장하였습니다. 그 후, 결제등록이 완료된 이후에만 예약신청내역에 저장되도록 하는 방식을 통해서 해결하였습니다.


# 📐아키텍처 구성 
### 시스템 아키텍처
![alt text](images/시스템_아키텍처.png)

### ERD
![alt text](images/ERD.png)

# 📂폴더 구조
- Frontend
```
Todak/
├── frontend/                 # React 기반 프론트엔드
│   ├── src/                  # 소스코드
│   │   ├── component/        # 공통/페이지별 컴포넌트
│   │   │   │   ├── auth/     # 인증 관련 페이지
│   │   │   │   ├── Owner/    # 반려인 페이지
│   │   │   │   ├── Staff/    # 직원 페이지
│   │   │   │   ├── Vet/      # 수의사 페이지
│   │   ├── assets/           # 이미지, 폰트 등 정적 리소스
│   │   ├── types/            # TypeScript 타입 정의
│   │   │   ├── Owner/        # 반려동물 주인 관련 타입
│   │   │   ├── Staff/        # 직원 관련 타입
│   │   │   ├── Vet/          # 수의사 관련 타입
│   │   │   └── auth.ts       # 인증 관련 타입
│   │   ├── services/         # API 서비스 로직
│   │   │   └── api/          # API 호출 함수들
│   │   ├── router/           # 라우팅 설정
│   │   ├── layouts/          # 레이아웃 컴포넌트
│   │   ├── store/            # 상태 관리 (Zustand)
│   │   ├── RTC/              # 실시간 통신 (WebRTC)
│   │   ├── utils/            # 유틸리티 함수
│   │   ├── styles/           # CSS 스타일
│   │   ├── plugins/          # 플러그인 설정 (axios 등)
│   │   └── ...               # 기타 src 하위 파일
│   ├── public/               # 정적 파일 (이미지, favicon 등)
│   ├── dist/                 # 빌드된 파일들
│   ├── package.json          # 프론트엔드 의존성/스크립트
│   ├── vite.config.ts        # Vite 설정
│   ├── tailwind.config.js    # Tailwind CSS 설정
│   ├── Dockerfile            # 프론트엔드 도커파일
│   ├── Jenkinsfile           # CI/CD 파이프라인 설정
│   ├── nginx.conf            # Nginx 설정
│   └── ...                   # 기타 설정 파일 (tsconfig, eslint 등)
│
├── README.md                 # 프로젝트 설명서
└── ...                       # 기타 파일/폴더
 ```
- Backend
```
backend/
├── build.gradle
├── docker-compose.yml
├── Dockerfile
├── gradlew
├── gradlew.bat
├── Jenkinsfile
├── settings.gradle
├── .gitattributes
├── .gitignore
│
├── src/
│   ├── main/
│   │   ├── java/com/A409/backend/
│   │   │   ├── BackendApplication.java
│   │   │   └── domain/
│   │   │       ├── home/
│   │   │       │   └── controller/
│   │   │       │       └── HomeController.java
│   │   │       │
│   │   │       ├── hospital/
│   │   │       │   ├── entity/
│   │   │       │   └── repository/
│   │   │       │
│   │   │       ├── pet/
│   │   │       │   └── entity/
│   │   │       │       ├── OwnerPet.java
│   │   │       │       └── Pet.java
│   │   │       │
│   │   │       ├── reservation/
│   │   │       │   └── entity/
│   │   │       │       ├── FirstTreatment.java
│   │   │       │       ├── Rejection.java
│   │   │       │       ├── Reservation.java
│   │   │       │       └── Treatment.java
│   │   │       │
│   │   │       ├── user/
│   │   │       │   ├── auth/
│   │   │       │   │   ├── entity/
│   │   │       │   │   │   └── Auth.java
│   │   │       │   │   └── repository/
│   │   │       │   │       └── AuthRepository.java
│   │   │       │   │
│   │   │       │   ├── owner/
│   │   │       │   │   ├── controller/
│   │   │       │   │   ├── dto/
│   │   │       │   │   ├── entity/
│   │   │       │   │   ├── repository/
│   │   │       │   │   └── service/
│   │   │       │   │
│   │   │       │   ├── staff/
│   │   │       │   │   ├── controller/
│   │   │       │   │   ├── dto/
│   │   │       │   │   ├── entity/
│   │   │       │   │   ├── repository/
│   │   │       │   │   └── service/
│   │   │       │   │
│   │   │       │   └── vet/
│   │   │       │       ├── controller/
│   │   │       │       ├── dto/
│   │   │       │       ├── entity/
│   │   │       │       ├── repository/
│   │   │       │       └── service/
│   │   │       │
│   │   │       └── global/
│   │   │
│   │   └── resources/
│   │       ├── elasticsearch/
│   │       └── application.properties
│   │
│   └── test/
```

# 👥팀원 소개
| 이대연 | 김유성 | 송인범 | 안성수 | 전윤지 | 한진경 |
|-------------|--------|--------|--------|--------|--------|
| FE, 팀장         | BE     | BE     | BE     | FE     | FE     |




