
# 🚀 Rodando N8N + MongoDB no Kubernetes

## 📁 1. Aplicar os Manifests

Certifique-se de ter os seguintes arquivos:

- `mongo-deployment.yaml`
- `n8n-deployment.yaml`
- `n8n-service.yaml`

**Execute os comandos:**

```bash
kubectl apply -f mongo-deployment.yaml
kubectl apply -f n8n-deployment.yaml
kubectl apply -f n8n-service.yaml
```

---

## 📊 2. Verificar os Pods

Verifique se os pods estão rodando corretamente:

```bash
kubectl get pods
```

Os pods `n8n` e `mongodb` devem aparecer com o STATUS `Running`.

---

## 🌐 3. Obter IP de Acesso

### 👉 Se estiver usando **Minikube**:

```bash
minikube ip
```

Suponha que o IP retornado seja `192.168.49.2`, use esse IP no navegador.

### 👉 Se estiver usando **Docker Desktop no Windows**, acesse via:

```bash
http://localhost:30078
```

---

## 🔗 4. Acessar a Interface do N8N

Abra no navegador:

```
http://<SEU_IP>:30078
```

Exemplos:
- Minikube: `http://192.168.49.2:30078`
- Docker Desktop: `http://localhost:30078`

---

## ✅ 5. Autenticação

As credenciais definidas no `n8n-deployment.yaml` são:

```
Usuário: admin
Senha:   admin
```

```
kubectl apply -f .\mongo\mongo-deployment.yaml
kubectl apply -f .\mongo\mongo-service.yaml

kubectl apply -f .\postgres\postgres-deployment.yaml
kubectl apply -f .\postgres\postgres-service.yaml

kubectl apply -f .\n8n\n8n-deployment.yaml
kubectl apply -f .\n8n\n8n-service.yaml
```

```
kubectl rollout restart deployment/n8n
```

http://localhost:30078
