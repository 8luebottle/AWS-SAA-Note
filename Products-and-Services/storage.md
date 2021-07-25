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


## S3 Glacier  
Glacier는 의료, 공공 부문과 같이 오랜기간 고객의 데이터를 보존해야하는 경우를 위해 설계 되었다.    
Glacier를 통해 오랜 기간(~n달, ~n년)동안 저장해야 하는 데이터를 저렴하게 보관할 수 있다. Glacier에 저장되는 데이터는 아카이브로 저장된다.

- 액세스가 자주 발생하는 데이터를 저장하는 용도에는 적합 X
- Glacier에 있는 데이터를 가져올 때는 지연시간이 오래 걸린다. 
- 최소 3개의 분산된 AZs에 복제된 채 저장된다.  

### S3 Glacier Deep Archive
S3에서 제일 저렴한 저장소이다.  
데이터가 액세스 되는 횟수가 연 1~2 회 정도로 아주 적은 경우 Deep Archive를 사용한다. 

- 저렴한 데이터 저장 비용: $0.00099 GB per Month

## EFS
## FSx
## AWS Backup
## Storage Gateway

## Application Discovery Service

[S3-FAQ]: https://aws.amazon.com/ko/s3/faqs/
[S3-Glacier-FAQ]: https://aws.amazon.com/ko/s3/glacier/faqs/?nc1=h_ls