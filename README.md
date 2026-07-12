# 👋 Hi there, I'm Lee Je-hoon (이제훈)
### ☁️ Cloud & DevOps Engineer | Kubernetes & GitOps Specialist

<p align="left">
  <a href="https://github.com/UniqueOnion">
    <img src="https://img.shields.io/badge/GitHub-181717?style=flat-square&logo=github&logoColor=white"/>
  </a>
  <img src="https://img.shields.io/badge/Email-dlwodns5841@naver.com-blue?style=flat-square&logo=naver&logoColor=white"/>
</p>

---

## 👨‍💻 About Me
비즈니스의 **중단 없는 가치**를 지탱하는 안정적인 인프라를 지향하는 **클라우드 & 데브옵스 엔지니어** 이제훈입니다.  
온프레미스 AI CCTV 솔루션 설치 및 장애 대응(SOP 구축) 경험을 바탕으로 시스템 밑바닥부터 다져진 트러블슈팅 역량을 보유하고 있으며, 클라우드(AWS) 이중화 설계, Kubernetes(EKS) 및 GitOps(ArgoCD) 파이프라인 자동화에 특화되어 있습니다.

---

## 🛠️ Tech Stacks

### ☁️ Cloud & DevOps
<p align="left">
  <img src="https://img.shields.io/badge/Amazon_AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white"/>
  <img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat-square&logo=kubernetes&logoColor=white"/>
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white"/>
  <img src="https://img.shields.io/badge/Terraform-7B42BC?style=flat-square&logo=terraform&logoColor=white"/>
  <img src="https://img.shields.io/badge/Argo_CD-FF7E00?style=flat-square&logo=argo&logoColor=white"/>
  <img src="https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat-square&logo=github-actions&logoColor=white"/>
  <img src="https://img.shields.io/badge/Prometheus-E6522C?style=flat-square&logo=prometheus&logoColor=white"/>
  <img src="https://img.shields.io/badge/Grafana-F46800?style=flat-square&logo=grafana&logoColor=white"/>
</p>

### 💻 OS & Languages & Frameworks
<p align="left">
  <img src="https://img.shields.io/badge/Linux_Ubuntu-E95420?style=flat-square&logo=ubuntu&logoColor=white"/>
  <img src="https://img.shields.io/badge/Shell_Script-4EAA25?style=flat-square&logo=gnu-bash&logoColor=white"/>
  <img src="https://img.shields.io/badge/PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white"/>
  <img src="https://img.shields.io/badge/Java_17-ED8B00?style=flat-square&logo=openjdk&logoColor=white"/>
  <img src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=spring-boot&logoColor=white"/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/C++-00599C?style=flat-square&logo=c%2B%2B&logoColor=white"/>
</p>

### 💾 Databases & Cache
<p align="left">
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/>
  <img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white"/>
  <img src="https://img.shields.io/badge/Amazon_DynamoDB-4053D6?style=flat-square&logo=amazondynamodb&logoColor=white"/>
</p>

---

## 💻 Projects

### 🎫 [대규모 트래픽 처리 공연 예매 시스템](https://github.com/UniqueOnion)
* **설명:** 대량의 실시간 티켓 예매 트래픽을 격리 제어 및 수용하기 위한 무중단 EKS 인프라 및 GitOps 배포 자동화 파이프라인
* **역할:** 인프라 및 GitOps 구성 관리 엔지니어 (VPC 설계, EKS 인프라, LBC 컨트롤러 및 Gateway API 연동, ArgoCD 운영)
* **핵심 해결 과제:**
  * **GatewayClass `Accepted=False` 장애 복구:** AWS LBC v3.1.0과 Gateway API CRD 버전 간 호환 충돌 문제를 분석하여 CRD v1.5.0 패치를 적용, 게이트웨이 클래스를 정상화하고 AWS ALB 생성을 자동화함.
  * **Readiness Probe 타임아웃 해결:** Spring Boot 파드가 기동 중 계속해서 재시작되는 문제를 확인, 애플리케이션의 실제 구동 시간(42s)에 맞춰 readinessProbe의 `initialDelaySeconds`를 60초로 변경하여 파드 배포를 정상화함.
  * **공유 계정 내 Grafana ALB 이름 명명 충돌 해소:** 타 팀들과 동일한 namespace에 Prometheus 모니터링 스택을 배포하면서 ALB 네임 명명 길이(32자) 제한으로 인한 ALB 충돌을 겪음. `kube-prometheus-stack-app.yaml`에 커스텀 Ingress ALB 명칭 명시 어노테이션(`t5-prod-grafana-alb`)을 적용하여 리소스를 정상 격리함.
  * **비용 방어용 인프라 전원 일괄 제어 자동화:** EKS NodeGroup, Bastion, RDS 인스턴스를 일괄 정지/기동시키는 PowerShell 스크립트(`aws-power.ps1`) 개발. RDS Multi-AZ 및 Read-Replica 추가에 맞춰 `InvalidParameterCombination` 등의 전원 차단 오류 예외 처리를 정밀 보완하여 자동화에 성공함.

### 📅 [TodoDiary 서비스 인프라 구축 및 EKS 배포](https://github.com/UniqueOnion)
* **설명:** 일기 및 할 일 관리 Spring Boot 서비스의 가상화 컨테이너 배포 및 인프라 설계 프로젝트
* **역할:** 인프라 및 DevOps 엔지니어 (Dockerfile 최적화, AWS ECR 이미지 빌드/배포, EKS 및 RDS 인프라 관리)
* **핵심 해결 과제:**
  * **Liveness Probe 실패 및 Actuator Security 충돌 해결:** 파드 기동 후 `CrashLoopBackOff` 무한 반복 문제 직면. Spring Security 보안 정책에서 `/actuator/health` 경로를 차단(403)하던 점을 발견하고, `SecurityConfig`에 `permitAll()` 허용 및 `application.yml` Actuator 노출 옵션을 설정하여 헬스체크 정상 통신 확인.
  * **멀티 서버 환경 로컬 저장 유실 리스크 극복:** 프로필 이미지는 S3에 저장되지만 다이어리 이미지는 `user.dir` 기반 로컬 디렉토리에 저장되는 구조적 한계 분석. 컨테이너가 무작위로 재배포되는 EKS 환경에서 로컬 파일 소실 위험을 사전에 규명하고, `S3Service` 기반 S3 업로드 구조로 통합하는 마이그레이션 및 리팩토링 방안을 도출해 제안함.
  * **Dockerfile 멀티스테이지 빌드 구성:** Maven 빌드와 Slim 기반 런타임 레이어를 구분하여 최종 도커 이미지 경량화 및 취약점 최소화 달성.

### 🏥 [DocRate - 병원 및 의사 리뷰 조회 서비스](https://github.com/CLD-05/team6-DocRate)
* **설명:** 병원/의사 정보 조회 및 사용자 평점 리뷰 공유 웹 애플리케이션
* **역할:** 백엔드 개발자 (병원 도메인 CRUD API 개발, 페이징 및 연관 쿼리 최적화)
* **핵심 해결 과제:**
  * 병원 도메인 DB 모델링 및 Hospital Entity/Repository 개발.
  * 목록 조회 트래픽 완화를 위한 Pagination 처리 및 병원-의사 연관 관계 조회 성능 튜닝.

---

## 📈 Github Stats

<p align="left">
  <img src="https://github-readme-stats.vercel.app/api?username=UniqueOnion&show_icons=true&theme=nord&align=left" alt="UniqueOnion's github stats" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=UniqueOnion&layout=compact&theme=nord" alt="UniqueOnion's top languages" />
</p>

---

## 📬 Contact Me
* **이메일:** dlwodns5841@naver.com
* **깃허브:** [github.com/UniqueOnion](https://github.com/UniqueOnion)
