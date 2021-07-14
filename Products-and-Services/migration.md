# Migration
마이그레이션 관련 AWS 서비스는 아래와 같다.

![Application Discovery Service](https://user-images.githubusercontent.com/48475824/125532063-73e63f4b-1c1c-423f-a2a1-906b6af63d99.png)
![AWS Snow Family](https://user-images.githubusercontent.com/48475824/125532061-85238cf4-2abb-480a-af15-0b6b9c9174ba.png)
![Database Migration Service](https://user-images.githubusercontent.com/48475824/125532056-a03cdc54-50f7-4908-a3e6-e5189cd4aa0f.png)
![Server Migration Service](https://user-images.githubusercontent.com/48475824/125532064-09c1b839-47d1-4c57-bc2c-f96e80e206b5.png)

## Application Discovery Service


## AWS Snow Family
![AWS Snow Family](https://user-images.githubusercontent.com/48475824/125553572-2477e7d5-ea8f-48fd-a395-8f911b032916.png)

- **[Youtube]**
  - About Snowball:  [AWS Snowball | Introducing a new 80TB appliance and four new regions (3:19)](https://youtu.be/yl25W7LZAMU)
  - About Snowball Edge: [AWS Snowball Edge Overview (1:44)](https://youtu.be/bxSD1Nha2k8)
  - About Snowcone: [AWS Snowcone – A Small, Portable, Rugged, and Secure Edge Computing and Data Transfer Device (3:03)](https://youtu.be/X_8LM7E_hiE)

대량 데이터를 전송하기 위해 사용된다
- 10TB 이상의 데이터를 전송하는데 적합.  
  (이보다 낮은 용량의 데이터를 전송한다면 다른 서비스를 통해 하자.)
- 1세대 80TB Snowball 장치는 더는 사용 불가.
  - Snowball Edge 를 사용할 것

하드웨어를 직접 구매 또는 관리할 필요가 없다.
- AWS Snow Family Management Console을 통해 또는 작업 관리 API를 사용하여 프로그래밍 방식으로 작업을 관리

Snowball은 자체 운송 컨테이너를 갖고 있다.

### 장점
- 용이한 데이터 이동  
  테라바이트 규모의 데이터 이동 → 1주 소요

- 로컬에서 데이터 처리 및 분석  
  네트워크에 연결하지 않아도 AWS 환경을 통해 직접 애플리케이션을 실행 가능  
  - EC2 AMI를 실행하고 AWS Lambda 코드를 Snowball Edge 디바이스에 배포하여 Machine Learning 또는 다른 애플리케이션을 통한 로컬 처리나 분석을 실행

- 독립형 스토리지  
  Snowball Edge 디바이스는 NFS(파일 공유 프로토콜) 또는 객체 스토리지 인터페이스(S3 API)를 사용한다.

- 보안
  - 암호화 키는 디바이스에 저장되지 않으며 AWS KMS에서 관리한다.
  - Trusted Platform Module(TPM)를 사용
    - 변조 방지 엔클로저
    - 256-비트 암호화
    - etc...
- 확장성
  - 테라바이트 규모의 데이터를 전송
  - 여러 대의 디바이스를 병렬로 사용하거나 함께 클러스터링하여 AWS에서 페타바이트 규모의 데이터를 송수신 가능

### [Region 기반 배송 제한](https://docs.aws.amazon.com/ko_kr/snowball/latest/ug/shipping.html#shipwithinregion) (Region-Based Shipping Restrictions)
일부 리전에서만 사용 가능 하다.  
Region 별 사용 가능한 Snowball 모델 (국제 배송을 지원하지 않음)
- 80TB
  - 모든 미국 리전
- 50TB
  - 기타 AWS 리전

지역별 배송 원칙  
- 미국: 미국 리전에서 데이터를 전송할 경우 외부로 snowball을 배송하지 않는다.
- 한국: 한국에서 데이터를 전송할 경우 한국 내에서만 Snowball을 배송.
- 일본: 일본에서 데이터를 전송할 경우 일본 내에서만 Snowball을 배송.
- 아시아 태평양: 아시아 태평양 (싱가포르) 리전에서 데이터를 전송할 경우 싱가포르로만 Snowball을 배송.


## Database Migration Service


## Server Migration Service
