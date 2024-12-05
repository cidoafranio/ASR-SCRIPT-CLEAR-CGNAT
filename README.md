# ASR-SCRIPT-CLEAR-CGNAT
ASR SCRIPT CLEAR CGNAT
Esse script foi desenvolvido para monitorar o uso de NAT (Network Address Translation) em um roteador e garantir que a alocação de recursos seja otimizada. Ele utiliza o recurso EEM (Embedded Event Manager), uma ferramenta disponível em dispositivos Cisco, para executar ações automaticamente com base em condições específicas. A lógica do script funciona da seguinte maneira:

Monitoramento periódico: O script é acionado a cada 5 minutos (300 segundos), definido pelo comando event timer watchdog.
Execução de comandos: Ele executa o comando show ip nat statistics | include allocated para verificar o uso atual de NAT.
Análise do uso: Através de uma expressão regular (regexp), o script extrai a porcentagem de alocação de NAT.
Tomada de decisão:
Uso acima de 95%: Se a utilização do NAT exceder 95%, o script:
Gera uma mensagem de log com prioridade "crítica" para alertar sobre o alto uso.
Limpa as traduções de NAT (clear ip nat translation *) para liberar recursos.
Uso abaixo de 95%: Se a utilização estiver abaixo desse limite, o script apenas registra um log informativo de que nenhuma ação é necessária.
Autoria: Este script foi desenvolvido por mim, Cido, da cidade de Afrânio-PE, com o objetivo de automatizar o gerenciamento de recursos de NAT e evitar possíveis interrupções na rede.
