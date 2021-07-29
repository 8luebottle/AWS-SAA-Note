# Storage
스토리지 관련 AWS 서비스는 아래와 같다.

![S3](https://user-images.githubusercontent.com/48475824/126885520-ea682be3-9388-45c8-a76e-679e5af094e3.png)
![S3 Glacier](https://user-images.githubusercontent.com/48475824/126885519-e311c6b4-cc1f-465e-8494-db475f18e88d.png)
![EFS](https://user-images.githubusercontent.com/48475824/126885517-4e92f7a8-b856-4b23-8daa-b177890578d6.png)
![FSx](https://user-images.githubusercontent.com/48475824/126885516-c887ac0a-10ff-42aa-b159-025ad412ee7b.png)
![AWS Backup](https://user-images.githubusercontent.com/48475824/126885513-9e1af3c6-d8db-4773-a7f7-dd1dc8f405f4.png)
![Storage Gateway](https://user-images.githubusercontent.com/48475824/126885514-10d22a54-a669-431c-aa9d-e4f70cbd94f2.png)

Amazon에서 제공하는 스토리지 카테고리는 아래와 같이 나뉜다.  

<img width="600" alt="AWS Storage Maturity" src="https://user-images.githubusercontent.com/48475824/126888660-ac2b8b7c-0277-4bd9-a095-caf19d6c2de6.png">

1. Block
    - `EBS`
    - `EC2 Instance Store`
1. File
    - `EFS`
1. Hybrid Integrated Storage
    - `AWS Storage Gateway`
1. Object
    - `S3`: 키 기반의 객체 스토리지
    - `S3 Glacier`


## S3
| [S3 FAQ][S3-FAQ] | [S3 Glacier FAQ][S3-Glacier-FAQ]

- **S3 Standard:** 자주 액세스 하는 데이터에 적합
- **S3 Intelligent-Tiering:** 패턴을 알 수 없거나 변화무쌍한 데이터에 적합  
- **S3 Standard-IA, S3 One Zone-IA:** 자주 액세스 하지는 않지만 오래 보존해놓아야 할 필요가 있는 데이터에 적합
- **S3 Glacier, S3 Glacier Deep Archive:** 저렴한 비용으로 오랫동안 저장해 놓아야 하는 데이터 또는 백업해야 할 데이터에 적합


#### ✅ Suitable
S3는 보통 네가지의 용도로 자주 사용된다.  

1. **정적 Web Content/Media 배포**  
   S3는 고유한 HTTP URL을 지니고 있기에 CDN(Content Delivery Network)의 오리진 스토리지로도 사용 가능하다.

1. **[정적 웹사이트 호스팅][Hosting-Static-Website]**  
   HTML파일, 이미지, 비디오 등 과 같은 정적 리소스들을 호스팅하는 용도  
   - [S3를 통해 호스팅하기][Walkthroughs-Hosting-websites-on-Amazon-S3]

1. **방대한 양의 분석용 데이터 저장**  
   금융 거래, 클릭 스트림(Clickstream), 미디어 트랜스코딩(Media transcoding)과 같은 데이터의 저장 용도  
   - [Youtube: Clickstream Analytics with AWS (45:48)][Clickstream-Analytics-with-AWS]

1. **확장성 있는 중요한 데이터의 안전한 저장/백업**  
   중요한 데이터를 우선 S3 bucket에 저장해 놓은 뒤 그 중 액세스 횟수가 적은 cold data를 Glacier로 옮기도록 작업할 수 있다.  
   - 이를 달성하기 위해서 S3의 Lifecycle을 설정.  

   백업용도로 안전하게 데이터를 저장: S3의 객체들을 여러 Region에 분산하여 복제 저장(비동기 방식)해 놓을 수 있다.

Glacier를 통해 오랜 기간(~n달, ~n년)동안 저장해야 하는 데이터를 저렴하게 보관할 수 있다. Glacier에 저장되는 데이터는 아카이브로 저장된다.

- 액세스가 자주 발생하는 데이터를 저장하는 용도에는 적합 X
- Glacier에 있는 데이터를 가져올 때는 지연시간이 오래 걸린다.
- 최소 3개의 분산된 AZs에 복제된 채 저장된다.

#### ❎ Unsuitable
- **File System**  
  - recommended: `EFS`
- **Structure Data w/ Query**  
  - recommended: `DynamoDB`, `RDS`, `CloudSearch`
- **Archival Data**  
  - recommended: `Glacier`
- **Dynamic Website Hosting**  
  - recommended: `EC2`, `EFS`
- **Rapidly Changing Data**  
  - recommended: `EBS`, `EFS`, `DynamoDB`, `RDS`

### S3 Glacier Deep Archive
S3에서 제일 저렴한 저장소이다.  
데이터가 액세스 되는 횟수가 연 1~2 회 정도로 아주 적은 경우 Deep Archive를 사용한다.

- 저렴한 데이터 저장 비용: $0.00099 GB per Month

## EFS  
| EFS: Ealstic File System
멀티쓰레드 앱

## FSx
## AWS Backup
## Storage Gateway

## Application Discovery Service

[S3-FAQ]: https://aws.amazon.com/ko/s3/faqs/
[S3-Glacier-FAQ]: https://aws.amazon.com/ko/s3/glacier/faqs/?nc1=h_ls
[Hosting-Static-Website]: https://docs.aws.amazon.com/AmazonS3/latest/userguide/WebsiteHosting.html
[Walkthroughs-Hosting-websites-on-Amazon-S3]: https://docs.aws.amazon.com/AmazonS3/latest/userguide/hosting-websites-on-s3-examples.html
[Clickstream-Analytics-with-AWS]: https://youtu.be/6cwbbqi36k8