# Projeto 04 — SIEM + Detecção de Ataques SSH com Wazuh

## Visão Geral

Este projeto teve como objetivo implementar um laboratório de monitoramento e detecção de ameaças utilizando o Wazuh SIEM em ambiente virtualizado.

O laboratório foi desenvolvido para simular atividades suspeitas relacionadas a autenticação SSH e brute force, permitindo monitoramento de logs, análise de eventos e investigação de alertas de segurança.

---

# Ambiente do Laboratório


| Máquina | Função | IP |
|---|---|---|
| Kali Linux | Máquina atacante | 192.168.56.106 |
| Metasploitable 3 | Máquina alvo vulnerável | 192.168.56.101 |
| Ubuntu + Wazuh | SIEM/Monitoramento | 192.168.56.104 |

---

# Ferramentas Utilizadas
- Wazuh SIEM
- Kali Linux
- Metasploitable 3
- Hydra
- SSH
- Linux
- VirtualBox
  
# Etapas do Projeto

## 1. Validação da conectividade entre as máquinas

Inicialmente foi realizado teste de comunicação entre as máquinas do laboratório utilizando o comando ping, garantindo que os hosts estavam se comunicando corretamente na rede Host-Only.

### Evidência
Validação de conectividade

---

## 2. Verificação do funcionamento do agente Wazuh

Foi realizada validação do agente Wazuh no Kali Linux para confirmar comunicação correta com o servidor SIEM.

### Evidência
Wazuh Agent

---

## 3. Ativação do serviço SSH

O serviço SSH foi iniciado no Kali Linux para permitir a simulação de autenticações e geração de logs de segurança.

### Evidência
SSH Active

---

## 4. Simulação de ataque brute force SSH

Foi utilizada a ferramenta Hydra para simular múltiplas tentativas de autenticação SSH utilizando wordlists de senhas.

Com isso, o laboratório gerou eventos de autenticação falha e comportamento semelhante a brute force.

### Evidência
Hydra SSH

---

## 5. Detecção de eventos no Wazuh

O Wazuh SIEM identificou eventos relacionados a:
- brute force
- credential access
- authentication failure
- ssh events

Os eventos foram detectados automaticamente pelo sistema de monitoramento.

### Evidência
Wazuh Detection

---

## 6. Investigação de eventos de segurança

Os logs foram analisados no dashboard do Wazuh através da área de Security Events e Discover, permitindo investigação dos eventos gerados durante o ataque.

### Evidência
Security Events

### Evidência
Log Analysis

---

# Resultado Final

O laboratório foi capaz de:

- detectar eventos de brute force SSH
- registrar logs de autenticação
- monitorar eventos de segurança
- identificar comportamento suspeito
- centralizar logs no Wazuh SIEM
- realizar investigação básica de eventos

---

# Tecnologias Utilizadas

- Wazuh
- Hydra
- Kali Linux
- Linux
- SSH
- VirtualBox

---

# Habilidades Desenvolvidas

- SIEM
- Threat Detection
- SSH Monitoring
- Log Analysis
- Blue Team
- Security Monitoring
- Troubleshooting
- Investigação de Eventos
