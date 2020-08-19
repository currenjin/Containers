# 컨테이너란 무엇일까요?

### [Docker&Kubernetes 포스팅](https://simpleisit.tistory.com/category/Simple%20is%20IT/Cloud%20%26%20Container)

### [Certified Kubernetes Administrator](./certified_kubernetes_administrator)

### [시작하세요! 도커&쿠버네티스](./start-docker-kubernetes)

<br>

## [자주쓰고 유용한 명령어]

### POD, Deployment

Create a POD<br>
`kubectl run --generator=run-pod/v1 nginx --image=nginx`
<br><br>

Generate POD Manifast YAML file(-o yaml). Don't create it(--dry-run)<br>
`kubectl run --generator=run-pod/v1 nginx --image=nginx --dry-run -o yaml`
<br><br>

Create a Deployment<br>
`kubectl create deployment --image=nginx nginx`
<br><br>

Generate Deployment YAML file(-o yaml). Don't create it(--dry-run)<br>
`kubectl create deployment --image=nginx nginx --dry-run -o yaml`
<br><br>

Generate Deployment YAML file(-o yaml). Don't create it(--dry-run) with 4 Replicas (--replicas=4)<br>
`kubectl create deployment --image=nginx nginx --dry-run -o yaml > nginx-deployment.yaml`
<br><br>

### Services

Create a Service named redis-service of type ClusterIP to expose pod redis on port 6379<br>
`kubectl expose pod redis --port=6379 --name redis-service --dry-run=client -o yaml`
<br>or<br>
`kubectl create service clusterip redis --tcp=6379:6379 --dry-run=client -o yaml`
<br><br>

Create a Service named nginx of type NodePort to expose pod nginx's port 80 on port 30080 on the nodes<br>
`kubectl expose pod nginx --port=80 --name nginx-service --type=NodePort --dry-run=client -o yaml`
<br>or<br>
`kubectl create service nodeport nginx --tcp=80:80 --node-port=30080 --dry-run=client -o yaml`
<br><br>

위 명령에서 발생하는 이슈 중 하나는 Selector를 받아들일 수 없고, 다른 하나는 Node Port를 받아들일 수 없습니다. 혹시 필요하다면 미리 지정하는 것이 좋아요!
<br><br>


## [유용한 설명 링크]

### [kubectl Usage Converntions](https://kubernetes.io/docs/reference/kubectl/conventions/)
<br>


1. [AWS에서 kubeadm로 클라우드 프로바이더를 설정해 쿠버네티스 설치하기](https://blog.naver.com/alice_k106/221696987140)
2. [kops 설치 시, IAM 역할 및 사용자 생성하기](https://blog.naver.com/alice_k106/221342005691)
3. [쿠버네티스 컴포넌트의 실행 옵션 변경하기](https://blog.naver.com/alice_k106/221737477464)
4. [쿠버네티스 버전이 너무 낮을 때 Nginx Ingress 포드가 Pending으로 뜨는 현상](./lecture4-nginx-ingress.md)
5. [GKE에서 Google Persistent Disk를 사용해 퍼시스턴트 볼륨 사용하기](https://blog.naver.com/alice_k106/221737984779)
6. [Dex와 Guard를 이용한 쿠버네티스 사용자 인증 방법](https://blog.naver.com/alice_k106/221598325656)
7. [CPU Affinity를 위해 CPU Manager 사용하기](https://blog.naver.com/alice_k106/221633530545)
8. [애드미션 컨트롤러를 직접 구현해보기](https://blog.naver.com/alice_k106/221546328906)
9. [커스텀 리소스의 제어를 위한 Operator 직접 구현해보기](https://blog.naver.com/alice_k106/221586279079)

<br>
