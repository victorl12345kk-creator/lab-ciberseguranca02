# Laboratório SOC - Detecção de Ameaças com Wazuh

## 📌 Visão Geral

Este projeto simula um pequeno ambiente de Security Operations Center (SOC) focado em detecção de ameaças, análise de logs, reconhecimento de rede e monitoramento utilizando o Wazuh SIEM.

O laboratório foi construído em um ambiente virtualizado controlado utilizando VirtualBox com múltiplas máquinas virtuais se comunicando através de uma rede Host-Only.

O objetivo deste projeto foi obter experiência prática com:

* Configuração de SIEM
* Monitoramento de ameaças
* Análise de logs
* Monitoramento de autenticação SSH
* Reconhecimento de rede
* Enumeração de serviços
* Investigação de eventos de segurança
* Fundamentos Blue Team
---

# 🖥️ Ambiente do Laboratório

## Máquinas Virtuais

### 🔴 Máquina Atacante

* Kali Linux
* IP: `192.168.56.106`

### 🎯 Máquina Alvo

* Metasploitable 2
* IP: `192.168.56.101`

### 🛡️ Servidor SIEM / Monitoramento

* Wazuh Server
* IP: `192.168.56.104`

---

# 🌐 Configuração de Rede

O ambiente foi configurado utilizando um adaptador Host-Only no VirtualBox para permitir comunicação entre todas as máquinas virtuais mantendo o laboratório isolado.

Testes de conectividade foram realizados utilizando:

```bash
ping 192.168.56.101
```

---

# ⚙️ Instalação do Wazuh

A plataforma Wazuh SIEM foi instalada e configurada no Ubuntu.

A instalação incluiu:

Wazuh Manager
Wazuh Dashboard
Wazuh Indexer
Integração de agentes

O painel web foi iniciado com sucesso e acessado através de:

```text
https://<wazuh-ip>:443
```

## Evidence

### 📸 Print to use:

![text](https://github.com/victorl12345kk-creator/lab-ciberseguranca02/blob/main/projeto-03-siem-wazuh/evidencias/01-wazuh-installation-finished.png?raw=true)




---

# 🔌 Validação da Conectividade de Rede

Antes de iniciar as atividades de monitoramento, foi validada a conectividade entre as máquinas do laboratório.

Os testes incluíram:

Validação de ping
Scans iniciais com Nmap
Testes de alcance dos serviços

## Comandos utilizados

```bash
ping 192.168.56.101
```

```bash
nmap 192.168.56.101
```

## Evidence

### 📸 Print to use: 

![text](https://github.com/victorl12345kk-creator/lab-ciberseguranca02/blob/main/projeto-03-siem-wazuh/evidencias/02-network-connectivity-test.png?raw=true)





---

# 🛰️ Integração do Agente Wazuh
O agente Wazuh foi integrado ao Wazuh Manager para permitir monitoramento centralizado e coleta de eventos de segurança.

O painel confirmou:

* Comunicação do agente
* Status ativo
* Registro realizado com sucesso

## Evidence

### 📸 Print to use:


![text](https://github.com/victorl12345kk-creator/lab-ciberseguranca02/blob/main/projeto-03-siem-wazuh/evidencias/03-wazuh-agent-active.png?raw=true)



---

# 🔥 Simulação de Falha de Autenticação SSH

Foi realizada uma simulação controlada de ataque de autenticação utilizando SSH.

Múltiplas tentativas de login falharam propositalmente a partir do Kali Linux contra o alvo Metasploitable 2.

## Comando utilizado

```bash
ssh msfadmin@192.168.56.101
```

Objetivo

Esta atividade simulou:

Tentativas de autenticação inválidas
Comportamento suspeito de login
Simulação básica de brute force
Geração de eventos de segurança
## Evidence

### 📸 Print to use:


![text](https://github.com/victorl12345kk-creator/lab-ciberseguranca02/blob/main/projeto-03-siem-wazuh/evidencias/04-ssh-failed-authentication.png?raw=true)



---

# 🔎 Reconhecimento de Rede e Enumeração de Serviços

Foi realizado reconhecimento de rede utilizando Nmap para identificar:

* Portas abertas
* Serviços ativos
* Versões dos serviços
* Informações do sistema operacional
* Informações da superfície de ataque

## Enumeração básica

```bash
nmap 192.168.56.101
```

## Detecção de serviços

```bash
nmap -sV -sC 192.168.56.101
```

## Scan agressivo

```bash
nmap -A 192.168.56.101
```

Alguns serviços identificados durante os scans incluíram:

* SSH
* FTP
* HTTP
* Samba
* MySQL
* Telnet
* PostgreSQL

## Evidence

### 📸 Print to use:


![text](https://github.com/victorl12345kk-creator/lab-ciberseguranca02/blob/main/projeto-03-siem-wazuh/evidencias/05-nmap-service-enumeration.png?raw=true)


---

# 🚨 Reconhecimento Avançado com Nmap

O scan agressivo forneceu:

* Fingerprinting do sistema operacional
* Execução de scripts NSE
* Detecção avançada de serviços
* Informações avançadas de reconhecimento de rede

Esta etapa simulou técnicas reais de reconhecimento frequentemente utilizadas em testes de invasão e atividades Red Team.

## Evidence

### 📸 Print to use:

![text](https://github.com/victorl12345kk-creator/lab-ciberseguranca02/blob/main/projeto-03-siem-wazuh/evidencias/06-nmap-aggressive-scan.png?raw=true)


---

# 📊 Detecção de Ameaças e Análise de Logs

Os eventos de segurança gerados durante as tentativas de autenticação SSH foram coletados e analisados utilizando o painel Discover do Wazuh.

O SIEM detectou com sucesso:

* Falhas de autenticação
* Eventos de login SSH
* Eventos de autenticação PAM
* Logs de atividades suspeitas
* Informações de sessão de usuários

## Atividades de Threat Hunting

O painel Discover foi utilizado para:

* Pesquisar logs relacionados a SSH
* Filtrar eventos de autenticação
* Investigar alertas gerados
* Analisar entradas de logs

## Evidence

### 📸 Print to use:



![text](https://github.com/victorl12345kk-creator/lab-ciberseguranca02/blob/main/projeto-03-siem-wazuh/evidencias/07-wazuh-threat-detection.png?raw=true)


---

# 🛠️ Tecnologias Utilizadas

* Wazuh SIEM
* Kali Linux
* Metasploitable 2
* Nmap
* VirtualBox
* Linux
* SSH

---

#🎯 Habilidades Demonstradas

Este projeto demonstra experiência prática com:

* Implementação de SIEM
* Monitoramento de segurança
* Detecção de ameaças
* Análise de logs SSH
* Operações Blue Team
* Reconhecimento de rede
* Enumeração de serviços
* Investigação de eventos de segurança
* Análise de logs
* Ambientes virtuais de laboratório
* Administração Linux
📚 Aprendizados Obtidos

Durante este projeto foram desenvolvidos conhecimentos práticos em:

* Construção de ambientes estilo SOC
* Geração e análise de eventos de segurança
* Monitoramento de tentativas de autenticação
* Identificação de serviços expostos
* Investigação de logs utilizando ferramentas SIEM
* Visibilidade da superfície de ataque
* Fundamentos Blue Team
🚀 Melhorias Futuras

Versões futuras deste laboratório poderão incluir:

* Ataques brute force com Hydra
* Automação com Active Response
* Bloqueio automático de IP
* File Integrity Monitoring (FIM)
* Threat hunting avançado
* Regras customizadas no Wazuh
* Simulação de malware
* Enumeração web


# ✅ Conclusão

Este projeto demonstrou com sucesso a implementação de um ambiente funcional de monitoramento estilo SOC utilizando o Wazuh SIEM.

O laboratório simulou:

* Detecção de ameaças
* Monitoramento de autenticação
* Análise de logs
* Reconhecimento de rede
* Enumeração de serviços
* Investigação de eventos de segurança

O projeto proporcionou experiência prática tanto com conceitos ofensivos quanto defensivos de cibersegurança dentro de um ambiente virtual controlado.
