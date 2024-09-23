# Kill Zombie Process Script

## Descrição

O script `kill-zumbi.sh` é uma ferramenta simples para identificar e matar processos zumbis em sistemas Linux. Um processo zumbi é aquele que já terminou sua execução, mas seu processo pai não fez a devida coleta, deixando um "resíduo" no sistema. O objetivo deste script é encontrar esses processos e eliminar seus processos pais, caso seja seguro fazê-lo.

## Como funciona

1. O script identifica todos os processos zumbis no sistema usando o comando `ps`.
2. Ele verifica o **PID do processo pai** (PPID) de cada processo zumbi encontrado.
3. Para cada PPID identificado, o script tenta finalizar o processo pai com o comando `kill -9`.
4. Se o processo pai não estiver mais em execução, ele será ignorado.

## Uso

### Download do script

Você pode baixar o script diretamente do GitHub usando o comando `wget`:

```bash
wget --no-check-certificate https://raw.githubusercontent.com/danielson-alencar/scritps-shell/refs/heads/main/kill-zumbi.sh
chmod +x kill-zumbi.sh
sudo ./kill-zumbi.sh


