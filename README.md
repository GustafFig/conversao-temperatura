# Projeto conversão de temperatura

## O desafio foi criar o arquivo src/Dockerfile
Então foi rodado
```sh
docker build -t gustaff77/temperature_conversion:v1
```
Para rodar
```sh
docker run --name temperature -p 80:8080 -d -t gustaff77/temperature_conversion:v1
```
e para subir
```sh
docker push gustaff77/temperature_conversion:v1
```
O mesmo foi feito para a tag latest

### Sobre o projeto
Ele foi disponibilizado e realizado um fork

## Desafio 2 k3d
Reutilizando esse projeto e os containers criados a partir dele para criar um cluster kubernetes local com k3d

Isto está sendo feito e representado pelo arquivo deployment.manifest que faz um deployment com um replicaset com alguns pods

### Para rodar

#### Pré-requisitos
 - docker
 - k3d
 - kubectl

```sh
k3d cluster create temperature-cluster -p "80:30000@loadbalancer"
```
**Note que a porta 80 pode ser outra porta livre na sua máquina**
Depois de criar o cluster rode

```sh
k3d cluster create temperature-cluster -p "80:30000@loadbalancer"
```
```
kubectl apply -f k3d/deployment.yaml
```

**Aguarde o sistema levantar**. Você pode usar
```sh
watch -n 1 kubectl get pod
```
e esperar todos levantarem, a partir disso entre no browser e navegue em http://localhost:80

**note que deve ser a mesma porta que colocada no comando do k3d**
