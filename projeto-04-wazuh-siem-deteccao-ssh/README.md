# 🛡️ Projeto 04 — Wazuh SIEM + Detecção de Eventos SSH

# 📌 Visão Geral

Este projeto foi desenvolvido com foco em monitoramento de eventos de segurança utilizando o Wazuh SIEM em um laboratório virtualizado.

O ambiente foi criado para simular atividades comuns monitoradas em ambientes SOC (Security Operations Center), incluindo:

* autenticação SSH
* tentativas de brute force
* geração de logs
* análise de eventos
* monitoramento de endpoints
* investigação de atividades suspeitas

Durante os testes, foi utilizada uma máquina Kali Linux para gerar eventos de autenticação contra um alvo vulnerável (Metasploitable 2), enquanto o Wazuh centralizou os logs e realizou a detecção dos eventos no ambiente.

O objetivo principal foi praticar conceitos de:

* Blue Team
* Threat Detection
* SIEM
* Monitoramento de logs
* Investigação de eventos
* Segurança ofensiva controlada
* Análise de incidentes

---

# 🖥️ Arquitetura do Laboratório

| Máquina          | Função                   | Sistema Operacional   | IP             |
| ---------------- | ------------------------ | --------------------- | -------------- |
| Kali Linux       | Máquina atacante/análise | Kali Linux            | 192.168.56.106 |
| Metasploitable 2 | Máquina vulnerável/alvo  | Linux Vulnerável      | 192.168.56.101 |
| Ubuntu + Wazuh   | SIEM/Monitoramento       | Ubuntu Server/Desktop | 192.168.56.104 |

---

# 🛠️ Ferramentas Utilizadas

| Ferramenta           | Finalidade                                   |
| -------------------- | -------------------------------------------- |
| Wazuh SIEM           | Monitoramento e análise de logs              |
| Kali Linux           | Simulação de ataques e testes                |
| Metasploitable 2     | Ambiente vulnerável controlado               |
| Hydra                | Simulação de brute force SSH                 |
| OpenSSH              | Serviço de autenticação remota               |
| Linux                | Sistema operacional utilizado no laboratório |
| Oracle VM VirtualBox | Virtualização do ambiente                    |

---

# 🎯 Objetivo do Projeto

O projeto teve como objetivo:

* implementar um ambiente SIEM funcional
* monitorar eventos de autenticação SSH
* detectar comportamentos suspeitos
* analisar logs de segurança
* praticar investigação de eventos
* compreender fluxo de monitoramento em ambientes SOC

---

# ⚙️ Etapas Realizadas

## 1️⃣ Configuração do laboratório virtualizado

Foi criado um ambiente isolado utilizando Oracle VM VirtualBox contendo:

* Kali Linux
* Metasploitable 2
* Ubuntu com Wazuh

As máquinas foram configuradas na mesma rede virtual para permitir comunicação entre os hosts.

---

## 2️⃣ Instalação e validação do Wazuh

O Wazuh foi instalado no Ubuntu para atuar como SIEM do laboratório.

Após a instalação:

* serviços foram inicializados
* dashboard foi validado
* logs passaram a ser monitorados
* o agente Kali foi registrado no manager

---

## 3️⃣ Validação do agente Wazuh

O endpoint Kali Linux foi registrado corretamente no Wazuh.

Isso permitiu:

* coleta de logs
* envio de eventos
* monitoramento em tempo real
* análise centralizada

---

## 4️⃣ Ativação do serviço SSH

O serviço OpenSSH foi iniciado no ambiente Linux para permitir testes de autenticação.

Isso possibilitou:

* simulação de login
* geração de falhas de autenticação
* monitoramento de eventos SSH

---

## 5️⃣ Simulação de brute force com Hydra

Foi utilizada a ferramenta Hydra para realizar múltiplas tentativas de autenticação SSH contra o alvo vulnerável.

O objetivo foi gerar eventos monitoráveis pelo SIEM.

---

## 6️⃣ Coleta e análise de logs

Os eventos gerados durante os testes foram enviados para o Wazuh, permitindo:

* visualização dos logs
* análise de eventos
* investigação das atividades
* detecção de comportamento suspeito

---

# 💻 Comandos Utilizados

## Verificação do serviço SSH

```bash
sudo systemctl status ssh
```

---

## Inicialização do serviço SSH

```bash
sudo systemctl start ssh
```

---

## Simulação de brute force SSH

```bash
hydra -l msfadmin -P /usr/share/wordlists/rockyou.txt ssh://192.168.56.101
```

---

# 📸 Evidências do Projeto

---

# 📸 01 — Agente Wazuh ativo e conectado


![text]()

## 🧪 O que foi realizado

Foi realizada a validação do agente Wazuh instalado no Kali Linux.

O endpoint foi registrado corretamente no Wazuh Manager e permaneceu ativo durante o monitoramento.

---

## 🔍 Resultado Obtido

O painel do Wazuh apresentou:

* agente online
* status ativo
* IP monitorado
* versão do agente
* comunicação funcional com o manager

---

## 🛡️ Importância para Segurança

O monitoramento de endpoints permite:

* coleta centralizada de logs
* auditoria de eventos
* investigação de incidentes
* visibilidade do ambiente
* monitoramento contínuo

---

# 📸 02 — Simulação de brute force SSH com Hydra

![Simulação de brute force SSH com Hydra](evidencias/02-hydra-ssh-bruteforce.png)

## 🧪 O que foi realizado

Foi utilizada a ferramenta Hydra para simular um ataque de brute force SSH contra o alvo vulnerável.

---

## 🔍 Resultado Obtido

As tentativas de autenticação geraram eventos de segurança monitorados pelo ambiente SIEM.

---

## 🛡️ Importância para Segurança

Ataques de brute force podem indicar:

* tentativa de invasão
* exploração de credenciais fracas
* credential access
* atividade maliciosa

Esse tipo de evento é frequentemente monitorado em ambientes SOC.

---

# 📸 03 — Execução das tentativas de autenticação

![Execução das tentativas de autenticação](evidencias/03-hydra-execution.png)

## 🧪 O que foi realizado

Durante os testes com Hydra, múltiplas tentativas de autenticação SSH foram executadas contra o alvo monitorado.

---

## 🔍 Resultado Obtido

O sistema registrou:

* falhas de login
* tentativas repetidas
* erros de autenticação
* geração de logs SSH

---

## 🛡️ Importância para Segurança

Falhas repetidas de autenticação podem indicar:

* brute force
* tentativa de acesso não autorizado
* reconhecimento de serviços
* atividade suspeita

---

# 📸 04 — Serviço SSH ativo no alvo

![Serviço SSH ativo no alvo](evidencias/04-ssh-service-status.png)

## 🧪 O que foi realizado

O serviço OpenSSH foi iniciado e validado no ambiente Linux.

---

## 🔍 Resultado Obtido

O ambiente ficou apto para:

* conexões SSH
* autenticação remota
* geração de eventos monitoráveis

---

## 🛡️ Importância para Segurança

Serviços SSH expostos podem ser alvo de:

* brute force
* exploração remota
* credenciais comprometidas

Por isso seu monitoramento é essencial em ambientes corporativos.

---

# 📸 05 — Eventos e alertas detectados pelo Wazuh

![Eventos e alertas detectados pelo Wazuh](evidencias/05-wazuh-threat-detection.png)

## 🧪 O que foi realizado

Os eventos gerados durante os testes foram enviados para o Wazuh SIEM.

---

## 🔍 Resultado Obtido

O painel apresentou:

* logs do sistema
* eventos SSH
* alertas monitorados
* registros AppArmor
* informações do endpoint monitorado
* análise centralizada de eventos

---

## 🛡️ Importância para Segurança

O uso de SIEM permite:

* centralização de logs
* correlação de eventos
* investigação de incidentes
* detecção de ameaças
* resposta rápida
* monitoramento contínuo

---

# 📊 Tabela de Evidências

| Evidência | Descrição                               |
| --------- | --------------------------------------- |
| 01        | Agente Wazuh ativo e conectado          |
| 02        | Simulação de brute force SSH            |
| 03        | Execução das tentativas de autenticação |
| 04        | Serviço SSH ativo no alvo               |
| 05        | Eventos detectados pelo Wazuh           |

---

# 📌 Resultado Final

O laboratório foi capaz de:

* monitorar eventos SSH
* detectar tentativas de brute force
* registrar falhas de autenticação
* centralizar logs no Wazuh
* investigar eventos de segurança
* praticar análise de logs
* aplicar conceitos de Blue Team
* simular monitoramento SOC

---

# 🎯 Competências Desenvolvidas

* SIEM
* Wazuh
* Threat Detection
* Blue Team
* Análise de Logs
* SSH Monitoring
* Linux
* Investigação de Eventos
* Monitoramento de Endpoints
* Correlação de Logs
* Troubleshooting Linux
* Segurança em Ambientes Virtualizados
* Simulação de Ataques Controlados

---

# 📚 Conclusão

Este projeto permitiu aprofundar conhecimentos em monitoramento de eventos e análise de logs utilizando Wazuh SIEM em ambiente virtualizado.

Além da parte ofensiva controlada com Hydra, o laboratório possibilitou compreender como eventos de autenticação são registrados, analisados e monitorados em plataformas SIEM utilizadas em ambientes corporativos.

O projeto também contribuiu para o desenvolvimento prático de habilidades relacionadas a:

* SOC
* monitoramento de segurança
* investigação de eventos
* análise de incidentes
* Blue Team
* administração Linux
* segurança ofensiva controlada
