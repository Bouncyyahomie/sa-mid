### Adding Microservice

#### Deploy to Docker

```bash
docker login -u "[username]" -p "[password]"
```

- สร้าง repo ใน [docker hub](https://hub.docker.com/)

build Dockerfile with tag
```bash
docker build -t <username>/<image name> --file Dockerfile .

```

```bash
docker tag [ชื่อ image] [ชื่อ repo ใน docker hub]:latest 
docker push [ชื่อ repo ใน docker hub]:latest
```

#### สร้าง yaml

- สร้างไฟล์ [ชื่อ].yaml

```bash
touch [filename].yaml
```

- สร้าง [deployment](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)
- สร้าง [service](https://kubernetes.io/docs/concepts/services-networking/service/)

- สร้างไฟล์ [ชื่อ-config].yaml

##### start Minikube and check status

```bash
minikube start --vm-driver=hyperkit
minikube status
```

##### get minikube node's ip address

```bash
minikube ip
```

####

```bash
kubectl apply -f . //apply ทุกไฟล์ใน dir ปัจจุบัน
```

##### get basic info about k8s components

```bash
kubectl get node
kubectl get pod
kubectl get svc
kubectl get all
```

##### get extended info about components

```bash
kubectl get pod -o wide
kubectl get node -o wide
```

##### get detailed info about a specific component

```bash
kubectl describe svc {svc-name}
kubectl describe pod {pod-name}
```

##### get application logs

```bash
kubectl logs {pod-name}
```

#####

```bash
minikube service [service name]
```

##### stop your Minikube cluster
```
minikube stop
```
<br />

> :warning: **Known issue - Minikube IP not accessible**

If you can't access the NodePort service webapp with `MinikubeIP:NodePort`, execute the following command:
```bash
minikube service webapp-service
```
<br />

#### Links

- mongodb image on Docker Hub: https://hub.docker.com/_/mongo
- webapp image on Docker Hub: https://hub.docker.com/repository/docker/nanajanashia/k8s-demo-app
- k8s official documentation: https://kubernetes.io/docs/home/
- webapp code repo: https://gitlab.com/nanuchi/developing-with-docker/-/tree/feature/k8s-in-hour
