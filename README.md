# 정적분석 도구 CodeQL

<img width="1000" alt="sast_codql" src="https://github.com/user-attachments/assets/d8b46ea1-fb23-434d-8701-e04367bada7f" />

### IAM 역할별 권한 설명
**1. Jenkins EC2에 필요한 권한**
  - `s3:PutObject` : 분석 대상 zip 파일을 S3에 업로드
  - `s3:GetObject` : 분석 결과 다운로드(sarif)
  - `lambda:InvokeFunction` : Lambda 트리거로 CodeQL 분석 시작

**2. Lambda에 필요한 권한**
  - `ssm:SendCommand` : EC2에 쉘 명령어 전달
  - `iam:PassRole` : `ssm`명령 실행 시 EC2가 사용할 Role을 위임할 수 있어야 함

**3. CodeQL EC2에 필요한 권한**
  - `ssm` : SSM 명령 수신 및 실행 로그 조회
  - `s3:GetObject, s3:PutObject` : zip 다운로드, 분석 결과 업로드
  - `ec2:DescribeInstances` : EC2 상태 조회, 보통 SSM 기본 권한에 포함
  
