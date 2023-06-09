# Installation

## Front-end
Require Node.js, React
should run the following command
```bash
cd smart-farm-web
npm start
```

## Back-end
Require .NET web api
should run the following command
```bash
cd smart-fram-api
dotnet run
```

## Docker Command
docker build -t smart-farm-api -f Dockerfile . <br />
docker run  -p 8000:80 -d smart-farm-api <br />
http://localhost:8000/api/sample/

## Run Docker Compose
In case using local build
```bash
docker-compose up --build -d
```
In case using docker image from cloud
```bash
docker-compose up -d
```

## Add sample data
```bash
Ref: SampleData.txt
Run: docker-compose up --build
Open: http://localhost:8080/swagger/index.html
Use: POST on each API
```

## Run Kubernetes cluster in minikube
```bash
cd kube-deploy
minikube start --driver=docker
kubectl apply -f .
kubectl get deployment
kubectl get service
kubectl get pods
minikube dashboard
minikube stop
```

## Delete Kubernetes cluster and clear docker cache
To clean all should run the folowing command
```bash
kubectl get deployment
kubectl delete deployment sth
kubectl delete --all pods
kind delete cluster
docker system prune -a
```

## Local Frontend url
http://localhost/home


## Docker Swarm using Docker-Compose Example
Create a Swarm
```bash
docker swarm init
```
Join a Swarm
```bash
sudo docker swarm join <TOKEN>
```
In SWARM MANAGER
```bash
touch docker-compose.yml
cat > docker-compose.yml
```
COPY docker-compose for SWARM.yml from addtional file then
```bash
sudo docker stack deploy -c docker-compose.yml smart-farm-web
```