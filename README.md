CD/CD PROJECT COMMIT 15

https://velog.io/@luckyprice1103/series/Jenkins-Kubernets-Ansible%EC%9D%84-%EC%9D%B4%EC%9A%A9%ED%95%9C-CICD-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8

![image](https://github.com/user-attachments/assets/605d7e3a-2fc2-489b-b481-fec53f57ac4e)
![image](https://github.com/user-attachments/assets/338722a9-189a-405f-b9bc-636313ea1729)

## CI 파트


   - github
   - Jenkins
   - Ansible

   &nbsp
   
깃허브에 어떤 변화가 생긴다면 깃허브 repository가 POM.XML를 통해서 trigger를 진행한다. 

젠킨스는 github repository로 부터 코드를 pull 한고 maven을 이용해서 architecture를 구성한다. 그리고 ansible서버로 아키텍처를 push한다.

ansible서버에는 도커를 설치해서 push된 아키텍처를 통해서 도커이미지를 만든다. 그리고 만들어진 docker이미지를 도커 허브에 push한다.

CI작업이 끝나면 자동적으로 CD작업이 trigger되도록 jenkins에 설정한다.


## CD 파트
   - ansible
   - kubernetes
   - dockerhub
 
  &nbsp
  
CD작업에서는 쿠버네티스를 실행할 bootstrap 서버를 만든다. 여기서 docker hub로부터 도커이미지를 pull 할것이고, 쿠베네티스 위에서 컨테이너를 빌드할 것이다. 이번 프로젝트에서는 aws eks를 사용할 것이다.
