# 🚀 ArgoCD GitOps Platform

Projeto GitOps utilizando ArgoCD e Kubernetes para entrega automatizada de aplicações através de sincronização declarativa baseada em Git.

---

# 📌 Visão Geral

Este projeto demonstra um fluxo moderno de GitOps utilizando:

- Kubernetes
- ArgoCD
- GitHub
- Kustomize

O objetivo é automatizar deploys em Kubernetes utilizando o Git como fonte única da verdade (Single Source of Truth).

---

# 🧱 Arquitetura

```text
Developer
    ↓
Git Push
    ↓
GitHub Repository
    ↓
ArgoCD
    ↓
Kubernetes Cluster
    ↓
Deploy Automático
```

---

# ⚙️ Tecnologias Utilizadas

- Kubernetes
- ArgoCD
- GitOps
- Kustomize
- YAML
- GitHub

---

# 🎯 Objetivo

Demonstrar conhecimentos práticos em:

- GitOps
- Continuous Delivery
- Kubernetes
- Deploy declarativo
- Automação DevOps
- Gerenciamento de manifests
- ArgoCD

---

# 📁 Estrutura do Projeto

```text
argocd-gitops-platform/
│
├── k8s/
│   └── base/
│       ├── deployment.yaml
│       ├── service.yaml
│       └── kustomization.yaml
│
└── README.md
```

---

# 🚀 Conceito GitOps

Neste modelo:

- Toda alteração ocorre via Git
- O ArgoCD monitora o repositório
- Mudanças são sincronizadas automaticamente
- Kubernetes permanece alinhado ao estado declarado no Git

---

# 🔄 Fluxo GitOps

## 1️⃣ Alterar manifests Kubernetes

Exemplo:

```yaml
replicas: 3
```

---

## 2️⃣ Realizar commit

```bash
git add .
git commit -m "feat: scale application"
git push
```

---

## 3️⃣ ArgoCD detecta alteração

O ArgoCD monitora continuamente o repositório Git.

---

## 4️⃣ Sincronização automática

A aplicação é atualizada automaticamente no Kubernetes.

---

# 📦 Deployment Kubernetes

## deployment.yaml

Responsável por:

- criar pods,
- controlar réplicas,
- definir containers,
- gerenciar rollout.

---

# 🌐 Service Kubernetes

## service.yaml

Responsável por:

- exposição interna,
- comunicação entre serviços,
- acesso aos pods.

---

# 🧩 Kustomize

O projeto utiliza Kustomize para organização dos manifests Kubernetes.

## kustomization.yaml

```yaml
---
resources:
  - deployment.yaml
  - service.yaml
```

Benefícios:

- organização modular,
- reutilização,
- escalabilidade,
- padrão Kubernetes moderno.

---

# ▶️ Execução Local

## Aplicar manifests

```bash
kubectl apply -k k8s/base
```

---

## Verificar pods

```bash
kubectl get pods
```

---

## Verificar serviços

```bash
kubectl get svc
```

---

# 🚀 Instalação do ArgoCD

## Criar namespace

```bash
kubectl create namespace argocd
```

---

## Instalar ArgoCD

```bash
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

---

## Verificar pods

```bash
kubectl get pods -n argocd
```

---

# 🌐 Acesso à Interface ArgoCD

## Port Forward

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

---

## Acessar navegador

```text
https://localhost:8080
```

---

# 🔑 Credenciais Admin

## Usuário

```text
admin
```

---

## Obter senha

```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

---

# 🔄 Configuração GitOps

## Repository URL

```text
https://github.com/danielviana2127/argocd-gitops-platform.git
```

---

## Path

```text
k8s/base
```

---

## Sync Policy

- Automatic
- Self Heal
- Prune Resources

---

# 🧠 Conceitos Demonstrados

Este projeto demonstra:

- GitOps
- ArgoCD
- Kubernetes Deployments
- Kubernetes Services
- Kustomize
- Declarative Infrastructure
- Continuous Delivery
- Infraestrutura moderna baseada em Git

---

# 🔍 Troubleshooting Realizado

Durante o desenvolvimento foram resolvidos problemas reais como:

- sincronização GitOps,
- configuração Auto Sync,
- organização Kustomize,
- deploy declarativo,
- troubleshooting Kubernetes,
- troubleshooting ArgoCD.

---

# 📚 Aprendizados

- Fluxo GitOps completo
- Deploy automatizado
- Sincronização declarativa
- Gerenciamento de Kubernetes via Git
- Organização profissional de manifests
- Continuous Delivery moderno

---

# 🚀 Melhorias Futuras

Possíveis evoluções:

- Multi-environment overlays
- Helm integration
- Observabilidade integrada
- Deploy Blue/Green
- Canary Deployments
- Policy as Code
- Secret Management

---

# 👨‍💻 Autor

Daniel Viana

🔗 https://github.com/danielviana2127

---

# ⭐ Destaque

Projeto desenvolvido com foco em práticas modernas de GitOps e Continuous Delivery utilizando ArgoCD e Kubernetes.
