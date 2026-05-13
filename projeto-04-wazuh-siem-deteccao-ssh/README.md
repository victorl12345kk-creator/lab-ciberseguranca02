# 🛡️ Projeto 04 — Wazuh SIEM + Detecção de Eventos SSH

## 📌 Objetivo

Este projeto teve como objetivo implementar um laboratório de monitoramento e detecção de eventos de segurança utilizando Wazuh SIEM em ambiente virtualizado.

O laboratório foi utilizado para simular tentativas de autenticação SSH e atividades relacionadas a brute force, permitindo coleta de logs, análise de eventos e investigação em ambiente SOC.

---

# 🖥️ Ambiente Utilizado

| Máquina | Função | IP |
|---|---|---|
| Kali Linux | Máquina atacante/análise | 192.168.56.106 |
| Metasploitable 2 | Máquina vulnerável/alvo | 192.168.56.101 |
| Ubuntu + Wazuh | SIEM/Monitoramento | 192.168.56.104 |

---

# 🛠️ Ferramentas Utilizadas

- Wazuh SIEM
- Kali Linux
- Metasploitable 2
- Hydra
- SSH
- Linux
- VirtualBox

---

# ⚙️ Etapas Realizadas

1. Configuração do laboratório virtualizado
2. Validação do agente Wazuh
3. Ativação do serviço SSH
4. Simulação de brute force com Hydra
5. Geração de eventos de autenticação
6. Monitoramento e análise de logs no Wazuh

---

# 💻 Comandos Utilizados

## Verificação do serviço SSH

bash sudo systemctl status ssh 

## Inicialização do serviço SSH

bash sudo systemctl start ssh 

## Simulação de brute force SSH

bash hydra -l msfadmin -P /usr/share/wordlists/rockyou.txt ssh://192.168.56.101 

---

# 📸 Evidências

---

## 📸 01 — Simulação de brute force com Hydra

Hydra brute force

### Análise Técnica

Foi realizada simulação de brute force SSH utilizando a ferramenta Hydra contra o alvo monitorado no laboratório.

### Importância para Segurança

Ataques de força bruta podem indicar:
- tentativa de acesso não autorizado
- credential access
- exploração de credenciais fracas

Esse tipo de evento é frequentemente monitorado em ambientes SOC.

---

## 📸 02 — Serviço SSH ativo no ambiente Linux

SSH ativo

### Análise Técnica

O serviço OpenSSH foi iniciado e validado no ambiente Linux para permitir os testes de autenticação controlados.

### Importância para Segurança

Serviços SSH expostos na rede podem ser alvo de:
- brute force
- exploração remota
- credenciais comprometidas

Por isso o monitoramento desse serviço é fundamental em ambientes corporativos.

---

## 📸 03 — Falhas de autenticação e erros de conexão

Falhas de autenticação

### Análise Técnica

As múltiplas tentativas de autenticação realizadas pelo Hydra geraram erros e eventos registrados no sistema monitorado.

### Importância para Segurança

Eventos repetidos de falha de login podem indicar:
- brute force
- tentativa de invasão
- atividade suspeita

Esses eventos são frequentemente correlacionados em plataformas SIEM.

---

## 📸 04 — Eventos e alertas identificados no Wazuh

Alertas Wazuh

### Análise Técnica

O Wazuh identificou eventos relacionados a autenticação SSH e atividades monitoradas durante os testes realizados no laboratório.

### Importância para Segurança

O monitoramento SIEM permite:
- análise centralizada
- investigação de eventos
- correlação de logs
- identificação de comportamento suspeito

---

## 📸 05 — Agente Kali Linux ativo no Wazuh

Agente Kali

### Análise Técnica

O endpoint Kali Linux foi registrado corretamente no Wazuh Manager e permaneceu ativo durante o monitoramento do ambiente.

### Importância para Segurança

A visibilidade dos endpoints monitorados é essencial para:
- coleta de logs
- auditoria
- investigação de incidentes
- monitoramento contínuo

---

# 📌 Resultado Final

O laboratório foi capaz de:

- monitorar eventos SSH
- registrar logs de autenticação
- detectar atividades suspeitas
- analisar eventos em ambiente SIEM
- centralizar logs no Wazuh
- praticar conceitos de Blue Team e SOC

---

# 🎯 Competências Desenvolvidas

- SIEM
- Monitoramento de eventos
- Análise de logs
- SSH Monitoring
- Threat Detection
- Blue Team
- Investigação de eventos
- Troubleshooting Linux
- Segurança em ambientes virtualiza
