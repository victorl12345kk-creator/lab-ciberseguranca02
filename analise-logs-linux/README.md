# 🔍 Análise de Logs Linux + Resposta a Incidente

## 🎯 Objetivo
Simular uma tentativa de acesso não autorizado via SSH, identificar a atividade suspeita através de logs do sistema e aplicar uma medida de mitigação.

---

## 🧪 Ambiente do Laboratório

- Kali Linux (máquina de origem)
- Metasploitable 2 (máquina vulnerável)
- VirtualBox (virtualização)
- UFW (firewall)

---

## 🌐 Configuração de Rede

As máquinas foram configuradas na mesma rede host-only:

- Kali Linux → 192.168.56.103  
- Metasploitable → 192.168.56.102  

---

## 📌 Etapas do Projeto

### 🔹 1. Teste de Conectividade

Verificação de comunicação entre as máquinas utilizando ping:

![Ping](prints/01-ping.png)

---

### 🔹 2. Tentativa de Acesso SSH

Simulação de tentativa de login com credenciais incorretas:

![SSH Falha](prints/02-ssh-falha.png)

---

### 🔹 3. Análise de Logs

Investigação no arquivo `/var/log/auth.log` para identificar a tentativa de acesso:

![Auth Log](prints/03-auth-log.png)

📍 Evidências encontradas:
- Falha de autenticação
- IP de origem (atacante)
- Usuário alvo (msfadmin)

---

### 🔹 4. Mitigação com Firewall

Bloqueio do IP atacante utilizando UFW:

![UFW](prints/04-ufw-bloqueio.png)

---

## 🛡️ Resultado

- Detecção de tentativa de acesso não autorizado  
- Identificação do IP atacante  
- Análise de logs do sistema  
- Aplicação de regra de bloqueio com firewall  

---

## 📚 Aprendizados

- Análise de logs no Linux  
- Identificação de eventos suspeitos  
- Uso de SSH em ambiente controlado  
- Aplicação de medidas de segurança (UFW)  
- Organização e documentação de incidentes  

---

## 🚀 Conclusão

Este projeto demonstra na prática um fluxo básico de segurança:

**Tentativa de ataque → Detecção → Análise → Resposta**

Simulando atividades reais de um analista de segurança (SOC).
