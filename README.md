# 🎯 Guia de Estudos — Rumo a Analista de Cloud

> Roadmap revisado a partir de uma avaliação por um conselho técnico de 4 perspectivas independentes (Arquiteto, Cético, Pragmático, Pesquisador) sobre o plano original. Meta: núcleo empregável em **10-14 meses**, com itens condicionais deixados para depois da contratação.

**Como usar esta página:**
- Marque `- [ ]` → `- [x]` conforme avança. Se você tem permissão de escrita neste repositório, dá para clicar direto nas caixas quando visualizar este arquivo no site do GitHub (ou no app do celular) — cada clique salva um commit automaticamente.
- Os módulos **1** e **2** são **contínuos**: rodam em paralelo com tudo o resto, começando hoje — não são fases para esperar a vez.
- Regra de honestidade (sugestão do Cético do conselho): toda sexta-feira, pergunte "isso gerou um artefato?" (commit, recurso provisionado, lab documentado). Se não, não foi estudo — foi só trabalho com nome bonito.

---

## 📊 Visão geral

| # | Nome do Estudo | Skills contidas | Onde estudar | Vale certificação? | Tempo estimado |
|---|---|---|---|---|---|
| 1 | [Git & GitHub como hábito](#1-git--github-como-hábito-contínuo) | Versionamento, branch, commit, PR, .gitignore | GitHub Skills (gratuito, interativo) | Não existe cert relevante — não aplicável | 2-3 dias de base + uso diário a partir daí |
| 2 | [Linux essencial + Bash](#2-linux-essencial--bash-contínuo) | Shell, permissões, systemd, pacotes, SSH, scripts | Linux Journey; OverTheWire Bandit; WSL2 na prática | **Não vale** — CompTIA Linux+/LFCS têm ROI baixo para este objetivo | 60-80h ao longo de ~4 meses |
| 3 | [AZ-104 (finalizar)](#3-az-104-finalizar) | VMs, VNet, Storage, RBAC, Monitor, Bicep básico | Microsoft Learn (oficial, gratuito); canal John Savill (YouTube) | **Sim** — é o certificado-âncora do plano | 6-10 semanas (restante) |
| 4 | [Terraform em Azure](#4-terraform-em-azure) | HCL, providers, state remoto, módulos, plan/apply | HashiCorp Learn (tutoriais oficiais gratuitos); recriar os labs do AZ-104 em Terraform | **Não por ora** — Terraform Associate é opcional, portfólio pesa mais | 3-4 semanas |
| 5 | [CI/CD mínimo](#5-cicd-mínimo) | GitHub Actions, OIDC, pipeline plan/apply | Docs do GitHub Actions; GitHub Skills "Continuous Integration" | Não existe cert de entrada relevante | 1-2 semanas (junto com o módulo 4) |
| 6 | [Rede em nuvem avançada](#6-rede-em-nuvem-avançada) | VNet peering, hub-spoke, VPN S2S, DNS híbrido, Private Endpoint | Microsoft Learn (trilha AZ-700, sem prova) | **Não agora** — estude o conteúdo, adie o exame | 4-5 semanas |
| 7 | [Governança, Backup e DR](#7-governança-backup-e-dr) | Management Groups, Azure Policy, tags, Azure Backup, Site Recovery, RPO/RTO | Microsoft Learn (módulos de Governance e Business Continuity) | Coberto pelo AZ-104/AZ-305, não precisa de cert isolada | 2-3 semanas |
| 8 | [Observabilidade e KQL](#8-observabilidade-e-kql) | Azure Monitor, Log Analytics, KQL, alert rules | Microsoft Learn ("KQL for Azure Monitor"); documentação do Kusto | Não existe cert de entrada específica | 2-3 semanas |
| 9 | [Docker + Kubernetes conceitual](#9-docker--kubernetes-conceitual) | Imagens, containers, pods, deployments (conceito, não operar cluster) | Docker Curriculum (gratuito); "Kubernetes for Beginners" (KodeKloud) | **Não** — CKA fica para quando o cargo exigir operação de cluster | 2-3 semanas |
| 10 | [Portfólio & Processo seletivo](#10-portfólio--processo-seletivo) | CV para cloud, LinkedIn, repositórios públicos, simulado de entrevista | GitHub (seus próprios repositórios); LinkedIn Learning para CV | Não aplicável | Contínuo, a partir do mês 4-5 |
| 11 | [AWS — mapeamento conceitual](#11-aws--mapeamento-conceitual) | IAM vs Entra, VPC vs VNet, EC2/S3/RDS vs VM/Blob/Azure SQL | AWS Skill Builder (módulos gratuitos de fundamentos) | **Condicional** — só tire o SAA-C03 se vagas reais da sua região pedirem | 2 semanas de mapeamento; SAA-C03 fica para pós-contratação |
| 12 | [SC-300 (opcional)](#12-sc-300-opcional) | Identity governance, Conditional Access avançado, PIM | Microsoft Learn (trilha SC-300) | **Condicional** — só se você decidir mirar vagas de Identidade/IAM | 6-8 semanas, se optar por ela |

---

## Módulos em detalhe

### 1. Git & GitHub como hábito (contínuo)
Não é uma fase a concluir — é uma regra a adotar. A partir de agora, nada do que você produzir nos módulos abaixo existe fora de um repositório.

- [ ] Fluxo básico: `clone`, `add`, `commit`, `push`, `.gitignore`
- [ ] Branches e Pull Requests (mesmo sozinho, pratique abrir PR e revisar seu próprio diff)
- [ ] Resolver um conflito de merge de propósito, num repo de teste
- [ ] Regra adotada: **todo lab feito a partir daqui vira commit neste ou em outro repositório público**

### 2. Linux essencial + Bash (contínuo)
Pré-requisito de tudo o que vem depois — Azure CLI, Terraform, runners de CI/CD, containers. Não espere o módulo 9 para começar.

- [ ] Ambiente pronto: WSL2 + Ubuntu (ou VM Ubuntu própria)
- [ ] Navegação, permissões, processos, systemd
- [ ] Gerenciamento de pacotes (`apt`), SSH, variáveis de ambiente
- [ ] Bash scripting básico (loops, condicionais, um script real de automação)
- [ ] Terminal padrão do dia a dia trocado para bash/WSL

### 3. AZ-104 (finalizar)
Certificado-âncora do plano — mantém, é o que sua bagagem de IAM/AD já acelera.

- [ ] Identity, governance, RBAC
- [ ] Storage e Azure Files
- [ ] Compute (VMs, escalonamento)
- [ ] Virtual networking básico
- [ ] Monitoramento básico e backup
- [ ] Prova AZ-104 agendada e feita

### 4. Terraform em Azure
Entra logo após o AZ-104, contra Azure — não espere a AWS para "multicloud deixar de ser abstrato".

- [ ] HCL básico: providers, resources, variables, outputs
- [ ] State remoto com locking (Azure Storage backend)
- [ ] Recriar em Terraform pelo menos 3 recursos que você fez clicando no AZ-104
- [ ] Módulos reutilizáveis
- [ ] Projeto: 1 repositório público com um mini ambiente completo (VNet + NSG + Key Vault + RBAC)

### 5. CI/CD mínimo
Junto com o Terraform — não deixe para o final.

- [ ] Pipeline GitHub Actions: `fmt` + `validate` + `plan` no Pull Request
- [ ] `apply` automático no merge
- [ ] Autenticação via OIDC (sem secret de service principal em texto puro)
- [ ] README do repositório documentando o pipeline

### 6. Rede em nuvem avançada
Gap real e citado por todo o conselho — mas o exame de especialista pode esperar.

- [ ] VNet peering e topologia hub-spoke
- [ ] VPN Site-to-Site / ExpressRoute (conceito)
- [ ] DNS híbrido e Private DNS Zones
- [ ] Private Endpoint (e por que o on-prem às vezes não resolve o nome)
- [ ] Landing Zone / Cloud Adoption Framework — visão geral

### 7. Governança, Backup e DR
Onde sua bagagem de AD/GPO converte de verdade — não deixe de fora.

- [ ] Management Groups e estrutura de subscriptions
- [ ] Azure Policy (efeitos audit/deny/deployIfNotExists) — atenção: **não é GPO**, é avaliação de conformidade de recursos
- [ ] Tagging e budget alerts (configure um budget na sua própria subscription de lab)
- [ ] Azure Backup e Site Recovery — RPO/RTO na prática

### 8. Observabilidade e KQL
Item de alto retorno que o roadmap original tratou como "um dia de comparação" — merece módulo próprio.

- [ ] Azure Monitor e Log Analytics Workspace
- [ ] KQL básico: `where`, `summarize`, `join`
- [ ] Alert rules e Action Groups
- [ ] Aplicar KQL em algo real: sign-in logs do Entra ID ou logs de Conditional Access

### 9. Docker + Kubernetes conceitual
Prático em Docker, conceitual em K8s — não vire fase de operação de cluster agora.

- [ ] Imagens, containers, Dockerfile básico
- [ ] `docker-compose` para subir um app com 2 serviços
- [ ] Conceitos de K8s: pods, deployments, services (sem operar cluster de produção)
- [ ] AKS — visão geral de quando faz sentido usar

### 10. Portfólio & Processo seletivo
A fase que o roadmap original não tinha nenhuma linha dedicada — comece em paralelo, não no fim.

- [ ] CV reescrito com linguagem de cloud
- [ ] LinkedIn atualizado
- [ ] Pelo menos 2 repositórios públicos com README e diagrama de arquitetura
- [ ] Primeira leva de candidaturas enviada (não espere se sentir "pronto")
- [ ] Simulado de entrevista técnica feito

### 11. AWS — mapeamento conceitual
Profundidade em uma nuvem primeiro. AWS entra como mapeamento, não como certificação, a menos que os dados de vaga da sua região confirmem a necessidade.

- [ ] IAM vs Entra ID
- [ ] VPC vs VNet, Security Groups vs NSG
- [ ] EC2/S3/RDS vs VM/Blob Storage/Azure SQL
- [ ] Pesquisa de mercado feita: 30-40 vagas reais de "Analista Cloud" tabuladas por palavra-chave (Azure vs AWS vs ambos)
- [ ] Decisão tomada: SAA-C03 vale a pena para o seu mercado? (sim/não, com base na pesquisa acima)

### 12. SC-300 (opcional)
Só siga em frente aqui se você decidir conscientemente mirar vagas de Identidade/IAM em vez de Analista de Cloud generalista.

- [ ] Decisão consciente registrada: quero mirar identidade/IAM como trilha? (sim/não)
- [ ] Se sim: Identity governance, Conditional Access avançado, PIM
- [ ] Se sim: prova SC-300 agendada

---

## 📈 Progresso

Atualize esta seção conforme for concluindo os módulos (marque com ✅):

- [ ] Módulo 1 — Git & GitHub
- [ ] Módulo 2 — Linux essencial
- [ ] Módulo 3 — AZ-104
- [ ] Módulo 4 — Terraform
- [ ] Módulo 5 — CI/CD
- [ ] Módulo 6 — Rede avançada
- [ ] Módulo 7 — Governança/Backup/DR
- [ ] Módulo 8 — Observabilidade/KQL
- [ ] Módulo 9 — Docker/K8s
- [ ] Módulo 10 — Portfólio/Processo seletivo
- [ ] Módulo 11 — AWS (mapeamento)
- [ ] Módulo 12 — SC-300 (opcional)

---

*Última atualização: 26/08/2026. Baseado na síntese de um Conselho Técnico de 4 agentes Claude independentes avaliando o roadmap original de transição de carreira Infra → Cloud.*
