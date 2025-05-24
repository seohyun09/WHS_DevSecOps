# LoadBalancing

<img width="800" alt="loadbalnce" src="https://github.com/user-attachments/assets/28f1a162-3252-44f4-9909-e6cbcd7cf56a" />

1. `8080번`으로 요청이 들어온다.
2. 로드 밸런싱 역할을 하는 `ALB`는 해당 요청을 `ECS`에 요청을 보낸다.
3. ALB는 `Blue 컨테이너(8080 포트)`로 요청을 전달한다.
4. 새로운 버전의 애플리케이션을 배포하기 위해 Green 서비스가 생성된다.
5. Green 서비스는 ALB의 `테스트용 포트(8081 포트)`와 연결되어 있고, 헬스체크를 통해 `Green 컨테이너` 상태를 확인한다.
6. Green 컨테이너가 헬스체크에 통과하면, 8080 포트 대상 그룹을 Blue에서 Green으로 전환한다.
