# Aula 1 — Fundamentos de Cloud Computing e AWS Cloud Practitioner

## 📋 Sobre a certificação

**AWS Certified Cloud Practitioner (CLF-C02)** — certificação de nível de entrada.

**Roadmap sugerido para DevOps:**
```
Cloud Practitioner → Solutions Architect Associate → CloudOps Engineer Associate → DevOps Engineer
```

### Formato do exame

| Aspeto | Detalhe |
|---|---|
| Duração | 90 minutos |
| Nº de perguntas | 65 (50 contam para a nota, 15 são de teste/não contam) |
| Tipo de perguntas | Escolha múltipla e resposta múltipla |
| Pontuação para passar | 700 em 1000 |
| Validade da certificação | 3 anos |

### Domínios do exame

| Domínio | Peso |
|---|---|
| 1. Cloud Concepts | 24% |
| 2. Security and Compliance | 30% |
| 3. Cloud Technology and Services | 34% |
| 4. Billing, Pricing and Support | 12% |

### Como estudar
- Ver vídeos das aulas
- Fazer hands-on labs
- Fazer exames de prática online

---

## ☁️ O que é Cloud Computing

> Prática de usar uma rede de servidores remotos alojados na internet para armazenar, gerir e processar dados, em vez de usar um servidor local.

### Evolução do alojamento (hosting)

```mermaid
flowchart LR
    A["Dedicated Server<br/>1 máquina por negócio"] --> B["VPS<br/>1 máquina, virtualizada<br/>em sub-máquinas"]
    B --> C["Shared Hosting<br/>1 máquina física partilhada<br/>por centenas de negócios"]
    C --> D["Cloud Hosting<br/>Múltiplas máquinas físicas<br/>a agir como um único sistema"]
```

### O que é um Cloud Service Provider (CSP)

Empresa que fornece múltiplos serviços cloud. Características típicas:

- Os serviços podem ser encadeados entre si
- Acessíveis através de uma API unificada
- Faturação **metered** (pagas pelo que consomes)
- Monitorização integrada
- Oferecem **IaaS** (Infrastructure as a Service)
- Automação via **IaC** (Infrastructure as Code)

**Principais fornecedores:** AWS, Azure, GCP

### Categorias de serviços cloud

- Compute
- Networking
- Storage
- Databases

> A AWS tem mais de 200 serviços disponíveis.

---

## 🧱 Modelos de serviço cloud

```mermaid
flowchart TB
    subgraph SaaS["SaaS"]
        S1["Aplicação pronta a usar.<br/>Não te preocupas com manutenção.<br/>Ex: Gmail, Office 365"]
    end
    subgraph PaaS["PaaS"]
        P1["Focas-te no deployment e gestão<br/>das tuas próprias aplicações.<br/>A infraestrutura é gerida pelo provider"]
    end
    subgraph IaaS["IaaS"]
        I1["Controlo total sobre servidores,<br/>rede e storage virtualizados.<br/>Ex: EC2, VPC"]
    end
```

| Modelo | O que geres tu | O que é gerido pelo provider |
|---|---|---|
| **IaaS** | SO, runtime, apps, dados | Servidores físicos, virtualização, rede |
| **PaaS** | Apps e dados | SO, runtime, servidores, infraestrutura |
| **SaaS** | Apenas a utilização | Tudo (a app já vem pronta a usar) |

---

## 🌍 Modelos de deployment

- **Public cloud** — infraestrutura partilhada, gerida por um provider (ex.: AWS)
- **Private cloud** — infraestrutura dedicada a uma única organização
- **Hybrid cloud** — combinação de cloud pública e privada
- **Cross/Multi cloud** — utilização de múltiplos providers cloud em simultâneo

---

## 🔐 IAM — primeiros passos

- Criar **utilizadores** e **grupos** no IAM (ex.: grupo `admin` com *Administrator Access*)
- **Nunca usar a conta root** para tarefas do dia a dia — usar sempre utilizadores IAM

---

## 🌎 Regiões

Uma **região** é uma área geográfica onde a AWS tem infraestrutura. Os recursos são criados dentro de uma região específica.

---

## 💰 Billing e controlo de custos

> O custo é sempre proporcional ao que consomes: **poder computacional × tempo em execução**.

Uma "história de overbilling" comum: recursos deixados a correr sem necessidade acabam por gerar custos inesperados — daí a importância de configurar alertas.

### AWS Budgets / Billing Alerts

Fluxo típico para criar um alerta de custos:

```mermaid
flowchart LR
    A[CloudWatch] --> B[Billing]
    B --> C[Criar um Alarm]
    C --> D{Condição atingida?}
    D -->|Valor de budget ultrapassado| E[Notificação]
    D -->|Anomalia de custo detetada| E
    E --> F["Ação automática opcional<br/>(ex: desligar um serviço)"]
```

Pode-se definir o alarme para dois tipos de situação:
1. Um valor de budget específico foi atingido.
2. Algo anómalo aconteceu (ex.: aparece um custo excessivo sem explicação).

---

📺 *Progresso: 1h08min de vídeo assistido.*