# Boilerplate de Manifestos Kubernetes

Este repositório contém um conjunto de manifestos Kubernetes prontos para uso, facilitando a reutilização no dia a dia. Esses manifestos servem como base para diferentes cenários e podem ser personalizados conforme necessário.

## Estrutura do Repositório

Explicação breve sobre a estrutura de diretórios e arquivos.

```plaintext
├── Dockerfile
├── server.go
├── k8s/
│   ├── configmap.yaml
│   ├── deployment.yaml
│   ├── kind.yaml
│   ├── livenessprob-deployment.yaml
│   ├── pod.yaml
│   ├── readinessprob-deployment.yaml
│   ├── replicaset.yaml
│   ├── secret.yaml
│   ├── service.yaml
│   ├── startupprob-deployment.yaml
└── README.md
```

## Como Usar

### 1. Clonar o Repositório

Clone o repositório para sua máquina local.

```bash
git clone https://github.com/seu-usuario/boilerplate-k8s-manifestos.git
cd boilerplate-k8s-manifestos
```

### 2. Customizar os Manifestos

Edite os arquivos YAML na pasta `k8s` de acordo com suas necessidades específicas.

### 3. Exemplos de Uso

#### ConfigMap

Use o ConfigMap para configurar suas aplicações.

```yaml
# k8s/configmap.yaml
apiVersion: v1
kind: ConfigMap
metadata:
  name: example-config
data:
  example.property: "value"
```

#### Deployment

Descreva um deployment básico para sua aplicação.

```yaml
# k8s/deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: example-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: example
  template:
    metadata:
      labels:
        app: example
    spec:
      containers:
      - name: example-container
        image: seu-usuario/seu-app:latest
        ports:
        - containerPort: 80
```

#### Serviço

Defina um serviço para expor sua aplicação.

```yaml
# k8s/service.yaml
apiVersion: v1
kind: Service
metadata:
  name: example-service
spec:
  selector:
    app: example
  ports:
    - protocol: TCP
      port: 80
      targetPort: 80
```

### 4. Aplicar os Manifestos

Use o kubectl para aplicar os manifestos no seu cluster Kubernetes.

```bash
kubectl apply -f k8s/configmap.yaml
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
```

## Documentação do Kubernetes

Para mais informações sobre como utilizar e configurar recursos no Kubernetes, consulte a [Documentação Oficial do Kubernetes](https://kubernetes.io/docs/).
