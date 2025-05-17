# Jenkins, CodeDeploy를 이용한 CI/CD 파이프라인

<img width="800" alt="cicd_pipeline" src="https://github.com/user-attachments/assets/f64f68ab-bd48-4d27-b484-8ad5688fb852" />

1. 개발자가 `Jenkins` 와  `WebHook` 으로 연동된 `GitHub` 에 `push` 한다.
2. `WebHook` 으로 인하여 `Jenkins` 가 호출된다.
3. `Jenkins` 가 파일을 `Docker Image` 형태로 `Build` 한다.
4. 저장된 이미지는 `ECR` 에 저장된다.
5. `Jenkins` 가 `CodeDeploy` 에 배포를 요청한다.
6. `CodeDeploy` 가 `ECS` 에 배포를 진행한다.
7. `CodeDeploy` 는 `ECR` 에 저장된 이미지를 가져온다.
8. `CloudWatch` 를 통해 모니터링한다.
