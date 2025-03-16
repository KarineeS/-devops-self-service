# -devops-self-service
trabalho pessoal
# 📌 DevOps Self-Service Portal

## 🚀 Visão Geral
Este projeto implementa um **portal DevOps Self-Service** para provisionamento automatizado de ambientes na AWS, utilizando práticas modernas de **GitOps, CI/CD, escalabilidade e segurança**. 

O objetivo é permitir que equipes de desenvolvimento possam criar e gerenciar seus próprios ambientes sem dependência do time de infraestrutura, acelerando entregas e reduzindo custos operacionais.

---

## ⚙️ Tecnologias Utilizadas

| Área | Tecnologias |
|------|------------|
| **Infraestrutura** | AWS EKS, Terraform, Karpenter |
| **Automação** | GitLab CI/CD, AWS Lambda, ArgoCD |
| **Monitoramento** | Prometheus, Grafana, Loki |
| **Segurança** | Istio (mTLS), Kyverno |
| **FinOps** | Kubecost, AWS Cost Explorer |
| **Provisionamento Self-Service** | AWS Lambda, API Gateway, DynamoDB |

---

## 🏗️ Arquitetura do Projeto

### 🔹 Componentes Principais
1️⃣ **Portal Web/API:** Interface para solicitação de ambientes.<br>
2️⃣ **AWS Lambda:** Responsável por executar o provisionamento sob demanda.<br>
3️⃣ **GitOps (ArgoCD):** Sincroniza automaticamente a infraestrutura via Git.<br>
4️⃣ **Kubernetes (EKS):** Cluster para executar os workloads provisionados.<br>
5️⃣ **Observabilidade:** Logs, métricas e tracing distribuído com Prometheus, Loki e Grafana.<br>
6️⃣ **Gerenciamento de Custos:** Integração com Kubecost para controle financeiro.<br>

![Arquitetura DevOps Self-Service](https://via.placeholder.com/800x400?text=Diagrama+da+Arquitetura)

---

## 🛠️ Como Configurar e Executar

### **🔹 Pré-requisitos**
Antes de iniciar, você precisa ter instalado:
- **AWS CLI** configurado com credenciais válidas
- **Terraform** instalado na máquina
- **kubectl** para gerenciar o Kubernetes
- **Helm** para instalar componentes no EKS

### **🔹 Passo a Passo para Deploy**
1. **Clone o repositório**:
   ```sh
   git clone https://github.com/seuusuario/devops-self-service.git
   cd devops-self-service
   ```

2. **Crie o cluster EKS com Terraform**:
   ```sh
   cd terraform
   terraform init
   terraform apply -auto-approve
   ```

3. **Configure o ArgoCD para GitOps**:
   ```sh
   kubectl apply -f manifests/argocd-install.yaml
   ```

4. **Implante o portal Self-Service**:
   ```sh
   kubectl apply -f manifests/self-service-api.yaml
   ```

5. **Acesse a interface web**
   ```sh
   kubectl port-forward svc/self-service-portal 8080:80
   ```
   - Acesse em `http://localhost:8080`

---

## 📊 Insights e Aprendizados

### **✔️ Benefícios da Abordagem Self-Service**
✅ Redução da dependência do time de infraestrutura.<br>
✅ Provisionamento rápido e seguro, seguindo padrões DevOps.<br>
✅ Maior controle de custos e melhor governança com GitOps.<br>
✅ Maior produtividade para equipes de desenvolvimento.

### **📌 Possíveis Melhorias Futuras**
- Implementação de uma interface gráfica para facilitar o uso.
- Integração com ferramentas de autenticação (SSO, IAM, RBAC).
- Implementação de monitoramento avançado com OpenTelemetry.

---

## 📂 Estrutura do Repositório

```
/devops-self-service
│── terraform/          # Infraestrutura como código (IaC)
│── manifests/          # Manifests Kubernetes (ArgoCD, Deployments)
│── self-service-api/   # Código da API de provisionamento
│── docs/               # Documentação adicional
│── README.md           # Documentação principal
```

---

## 🔗 Links Úteis
- [Documentação Oficial do ArgoCD](https://argo-cd.readthedocs.io/)
- [Karpenter - AWS Auto Scaling](https://karpenter.sh/)
- [Guia de Observabilidade com Prometheus e Grafana](https://prometheus.io/docs/introduction/overview/)
- [Terraform AWS EKS Module](https://registry.terraform.io/modules/terraform-aws-modules/eks/aws/latest)

---

## 📢 Contribuições e Feedback
Caso tenha alguma sugestão ou melhoria, fique à vontade para abrir uma issue ou pull request neste repositório!
