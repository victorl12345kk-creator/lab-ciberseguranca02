🔍 Projeto 02 — Análise de Logs Linux e Resposta a Incidente
Objetivo

Simular uma tentativa de acesso remoto via SSH, investigar logs de autenticação e aplicar mitigação com firewall em ambiente controlado.

Ambiente
Kali Linux → máquina de origem (192.168.56.103)
Metasploitable 2 → alvo (192.168.56.102)
Oracle VM VirtualBox → virtualização
UFW → mitigação
Etapa 1 — Teste de conectividade

Foi validada a comunicação entre as máquinas.

Comando:

ping 192.168.56.102

Print:

01-ping.png
Etapa 2 — Tentativa de autenticação SSH

Foi realizada tentativa de login com credencial inválida para gerar evento de segurança.

Comando:

ssh -oHostKeyAlgorithms=+ssh-rsa msfadmin@192.168.56.102

Resultado:

Permission denied

Print:

02-ssh-falha.png
Etapa 3 — Investigação de logs

Foi analisado o log de autenticação Linux.

Comando:

tail -20 /var/log/auth.log

Achados:

falha de autenticação
IP de origem identificado
usuário alvo identificado

Trecho encontrado:

authentication failure
rhost=192.168.56.103
Failed password for msfadmin

Print:

03-auth-log.png
Etapa 4 — Mitigação

Foi ativado firewall e aplicada regra de bloqueio ao IP de origem.

Comandos:

sudo ufw enable
sudo ufw deny from 192.168.56.103
sudo ufw status

Resultado:
✔ firewall ativo
✔ regra aplicada

Print:

04-ufw-bloqueio.png
Aprendizados

✔ análise de logs Linux
✔ investigação inicial de incidente
✔ identificação de origem de acesso
✔ autenticação SSH
✔ firewall básico
✔ mitigação por IP
✔ documentação técnica
