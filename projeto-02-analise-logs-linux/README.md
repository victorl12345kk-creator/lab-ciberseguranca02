🛡️ Projeto 02 — Detecção, Investigação e Mitigação de Incidente em Linux
📌 Visão Geral

Neste projeto foi montado um cenário prático de segurança ofensiva e defensiva em laboratório controlado, simulando uma tentativa de acesso indevido via SSH, realizando investigação dos logs do sistema e aplicando mitigação por firewall.

O objetivo foi reproduzir um fluxo real de trabalho comum em times de Segurança da Informação / SOC:

Detectar → Investigar → Responder → Mitigar

🎯 Objetivos do Projeto

✔ Validar comunicação entre máquinas em rede controlada
✔ Simular tentativa de autenticação mal sucedida via SSH
✔ Identificar evidências em logs Linux
✔ Correlacionar IP de origem da tentativa de acesso
✔ Aplicar bloqueio por firewall
✔ Documentar processo técnico

🧪 Ambiente de Laboratório
Máquina de Origem

🖥️ Kali Linux
IP: 192.168.56.103

Função:

geração de evento de segurança
simulação de tentativa de autenticação
Máquina Alvo

🎯 Metasploitable 2
IP: 192.168.56.102

Função:

servidor alvo
geração de logs
aplicação de mitigação
Ferramentas utilizadas

⚙️ Oracle VM VirtualBox
🔍 OpenSSH
🧱 UFW
📄 /var/log/auth.log

Etapa 01 — Conectividade

Antes da simulação, foi validada a comunicação entre as máquinas.

Comando:

ping 192.168.56.102

Resultado:
✅ comunicação estabelecida

📸 Evidência:
prints/ ![text](https://github.com/victorl12345kk-creator/lab-ciberseguranca02/blob/main/projeto-02-analise-logs-linux/evidencias/01-ping.png?raw=true)

Etapa 02 — Simulação de Tentativa de Acesso

Foi realizada conexão SSH com credencial inválida para gerar evento de autenticação falha.

Comando:

ssh -oHostKeyAlgorithms=+ssh-rsa msfadmin@192.168.56.102

Resultado:

Permission denied

Interpretação:

tentativa de autenticação rejeitada pelo servidor.

📸 Evidência:
prints/02-ssh-falha.png

Etapa 03 — Investigação Forense Inicial

Análise dos registros de autenticação:

Comando:

tail -20 /var/log/auth.log

Evento encontrado:

authentication failure
rhost=192.168.56.103
Failed password for msfadmin
Informações extraídas:

✔ IP de origem identificado
✔ serviço utilizado: SSH
✔ usuário alvo identificado
✔ tentativa malsucedida registrada

📸 Evidência:
prints/03-auth-log.png

Etapa 04 — Resposta e Mitigação

Foi aplicada contenção bloqueando o IP de origem.

Comandos:

sudo ufw enable
sudo ufw deny from 192.168.56.103
sudo ufw status

Resultado:
✅ Firewall ativado
✅ Regra aplicada com sucesso
✅ Bloqueio persistente configurado

📸 Evidência:
prints/04-ufw-bloqueio.png

📚 Aprendizados Técnicos

Durante o projeto foram praticados conceitos de:

🔹 Linux Administration
🔹 SSH Authentication
🔹 Log Analysis
🔹 Incident Investigation
🔹 Firewall Management
🔹 Security Monitoring
🔹 Incident Response
🔹 Technical Documentation

🎯 Conclusão

Este laboratório simulou um fluxo básico porém realista de tratamento de incidente:

Tentativa de acesso → geração de log → investigação → identificação → mitigação

Competências demonstradas:

✅ análise de logs
✅ investigação inicial
✅ correlação de eventos
✅ resposta a incidente
✅ hardening básico
✅ documentação técnica
