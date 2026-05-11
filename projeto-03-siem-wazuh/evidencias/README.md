# Laboratório SOC - Detecção de Ameaças com Wazuh

## 📌 Visão Geral

Este projeto simula um pequeno ambiente de Security Operations Center (SOC) focado em detecção de ameaças, análise de logs, reconhecimento de rede e monitoramento utilizando o Wazuh SIEM.

O laboratório foi construído em um ambiente virtualizado controlado utilizando VirtualBox com múltiplas máquinas virtuais se comunicando através de uma rede Host-Only.

O objetivo deste projeto foi obter experiência prática com:

* SIEM configuration
* Threat monitoring
* Log analysis
* SSH authentication monitoring
* Network reconnaissance
* Service enumeration
* Security event investigation
* Blue Team fundamentals

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

Connectivity tests were performed using:

```bash
ping 192.168.56.101
```

---

# ⚙️ Instalação do Wazuh

The Wazuh SIEM platform was installed and configured on Ubuntu.

The installation included:

* Wazuh Manager
* Wazuh Dashboard
* Wazuh Indexer
* Agent integration

The web dashboard was successfully initialized and accessed through:

```text
https://<wazuh-ip>:443
```

## Evidence

### 📸 Print to use: ![text](https://github.com/victorl12345kk-creator/lab-ciberseguranca02/blob/main/projeto-03-siem-wazuh/evidencias/01-wazuh-installation-finished.png?raw=true)




---

# 🔌 Validação da Conectividade de Rede

Before starting monitoring activities, connectivity between the machines was validated.

Tests included:

* Ping validation
* Initial Nmap scans
* Service reachability tests

## Commands Used

```bash
ping 192.168.56.101
```

```bash
nmap 192.168.56.101
```

## Evidence

### 📸 Print to use: ![text]()



![Connectivity](evidencias/02-network-connectivity-test.png)

---

# 🛰️ Integração do Agente Wazuh

The Wazuh agent was integrated with the Wazuh Manager to allow centralized monitoring and event collection.

The dashboard confirmed:

* Agent communication
* Active status
* Successful registration

## Evidence

### 📸 Print to use:

![text]()

![Agent Active](evidencias/03-wazuh-agent-active.png)

---

# 🔥 Simulação de Falha de Autenticação SSH

A controlled authentication attack simulation was performed using SSH.

Multiple failed login attempts were generated from Kali Linux against the Metasploitable target.

## Command Used

```bash
ssh msfadmin@192.168.56.101
```

Incorrect passwords were intentionally used multiple times to generate authentication failure logs.

## Objective

This activity simulated:

* Failed authentication attempts
* Suspicious login behavior
* Basic brute force behavior
* Security event generation

## Evidence

### 📸 Print to use:

![text]()

![SSH Failed Authentication](evidencias/04-ssh-failed-authentication.png)

---

# 🔎 Reconhecimento de Rede e Enumeração de Serviços

Network reconnaissance was performed using Nmap to identify:

* Open ports
* Running services
* Service versions
* Operating system details
* Attack surface information

## Basic Enumeration

```bash
nmap 192.168.56.101
```

## Service Detection

```bash
nmap -sV -sC 192.168.56.101
```

## Aggressive Scan

```bash
nmap -A 192.168.56.101
```

## Services Identified

Some services identified during the scan included:

* SSH
* FTP
* HTTP
* Samba
* MySQL
* Telnet
* PostgreSQL

## Evidence

### 📸 Print to use:

![text]()

![Nmap Enumeration](evidencias/05-nmap-service-enumeration.png)

---

# 🚨 Reconhecimento Avançado com Nmap

The aggressive scan provided:

* OS fingerprinting
* NSE script execution
* Advanced service detection
* Network reconnaissance data

This step simulated real-world reconnaissance techniques commonly used during penetration testing and red team activities.

## Evidence

### 📸 Print to use:

![text]()

![Nmap Aggressive Scan](evidencias/06-nmap-aggressive-scan.png)

---

# 📊 Detecção de Ameaças e Análise de Logs

Security events generated during the SSH authentication attempts were collected and analyzed using the Wazuh Discover dashboard.

The SIEM successfully detected:

* Authentication failures
* SSH login events
* PAM authentication events
* Suspicious activity logs
* User session information

## Threat Hunting Activities

The Discover dashboard was used to:

* Search for SSH-related logs
* Filter authentication events
* Investigate generated alerts
* Analyze log entries

## Evidence

### 📸 Print to use:

![text]()

![Threat Detection](evidencias/07-wazuh-threat-detection.png)

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

# 🎯 Habilidades Demonstradas

This project demonstrates practical experience with:

* SIEM deployment
* Security monitoring
* Threat detection
* SSH log analysis
* Blue Team operations
* Network reconnaissance
* Service enumeration
* Security event investigation
* Log analysis
* Virtual lab environments
* Linux administration

---

# 📚 Aprendizados Obtidos

Through this project, practical knowledge was gained in:

* Building SOC-style environments
* Generating and analyzing security events
* Monitoring authentication attempts
* Identifying exposed services
* Investigating logs using SIEM tools
* Understanding attack surface visibility
* Blue Team fundamentals

---

# 🚀 Melhorias Futuras

Future versions of this lab may include:

* Hydra brute force attacks
* Active Response automation
* Automatic IP blocking
* File Integrity Monitoring (FIM)
* Advanced threat hunting
* Custom Wazuh rules
* Malware simulation
* Web enumeration

---

# 📸 Estrutura das Evidências

```text
📁 evidencias
 ├── 01-wazuh-installation-finished.png
 ├── 02-network-connectivity-test.png
 ├── 03-wazuh-agent-active.png
 ├── 04-ssh-failed-authentication.png
 ├── 05-nmap-service-enumeration.png
 ├── 06-nmap-aggressive-scan.png
 └── 07-wazuh-threat-detection.png
```

---

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
