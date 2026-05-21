# Microsoft-Windows-Cleanup-Optimization-Guide
Complete Windows maintenance, cleanup, repair, and optimization guide with temporary file cleanup, DISM/SFC repair, startup optimization, service tuning, registry tweaks, driver diagnostics, and performance improvements for gaming and daily use.

Clean them ALL!

Fechar programas e criar ponto de restauração
criar um ponto de restauração do Windows
atualizar Windows Update antes da manutenção
reiniciar o PC antes de começar se estiver ligado há muitos dias

1. Limpeza básica de arquivos temporários
win+r temp [delete all]
win+r %temp% [delete all]
win+r prefetch [delete all]

1. Limpeza do sistema Windows
cmd cleanmgr

Execute como administrador e limpe:

Windows Update Cleanup
Temporary Files
Delivery Optimization
DirectX Shader Cache
Recycle Bin



1. Reparação da imagem do Windows (DISM primeiro)
O DISM corrige a imagem do Windows usada pelo SFC.

cmd DISM /Online /Cleanup-Image /RestoreHealth



1. Verificação de integridade do sistema (SFC depois)

cmd sfc /scannow
1. Desativar programas de inicialização
cmd taskmgr

Ir em Inicializar e Desativar programas desnecessários. Mas NUNCA:
Driver NVIDIA
AMD
Intel
Windows Security
TouchPad
Audio
1. Desativar serviços desnecessários
cmd services.msc
sysmain
fax
print spooler
Xbox
Windows search
remote registry
bluetooth
connected user experiences and telemetry

OBS: Pode desativar sem muito risco:
• Fax
• Xbox
• Remote Registry
• Connected User Experiences and Telemetry

Melhor deixar MANUAL ao invés de desativado:
• Bluetooth → apenas se realmente não usa
• Print Spooler → se usa impressora, NÃO desative
• Windows Search → desativar pode piorar busca/explorer
• SysMain → bom testar; em SSD moderno às vezes não ajuda desativar
1. Remover aplicativos desnecessários
cmd winget list
cmd winget list app_name_sort_name
cmd winget uninstall PROGRAM
[if there's duplicate names, use the --id property]
1. Ativar Ultimate Performance
cmd powercfg -duplicatescheme e9a42b02-d5df-448d-aa00-03f14749eb61

Depois:
abrir opções de energia
selecionar “Ultimate Performance”

1. Otimizações de registro
cmd reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile" /v NetworkThrottlingIndex /t REG_DWORD /d 4294967295 /f

cmd reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile" /v SystemResponsiveness /t REG_DWORD /d 0 /f

cmd reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\PriorityControl" /v Win32PrioritySeparation /t REG_DWORD /d 38 /f

cmd reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\DataCollection" /v AllowTelemetry /t REG_DWORD /d 0 /f

Observações sobre essas otimizações:
NetworkThrottlingIndex
Boa para:
• jogos online
• baixa latência

SystemResponsiveness
Pode ajudar em:
• games
• foreground priority

Win32PrioritySeparation
• Muito usado em tweaks gamer.

AllowTelemetry
• Reduz telemetria.

Importante:
Pode afetar:
• Xbox services
• algumas métricas Windows
• certos recursos de diagnóstico

Reinicialização FINAL
Após tudo, REINICIAR.
Importante para:
• aplicar serviços
• registro
• power plan
• cache rebuild

EXTRAS

Verificar disco:
chkdsk /scan

Ver drivers instalados
driverquery
driverquery /v (detalhado)
driverquery /v > C:\drivers.txt (exportar para txt)

Ver versão dos drivers via WMIC

wmic path win32_pnpsigneddriver get deviceName,driverVersion

wmic path win32_pnpsigneddriver get deviceName,driverVersion,manufacturer

Ver dispositivos com problema
pnputil /enum-devices /problem

Se aparecer algo:
• driver faltando
• corrompido
• conflito

Ver todos os drivers do sistema
pnputil /enum-drivers

Procurar drivers pelo Windows Update (melhor método nativo)

Install-Module PSWindowsUpdate

Get-WindowsUpdate

Install-WindowsUpdate

Comandos úteis para identificar hardware
msinfo32
dxdiag

Melhor sequência prática
1. pnputil /enum-devices /problem
2. Windows Update
3. GPU official updater
4. chipset/site fabricante
5. driverquery /v

N A V E G A D O R CHROME

1. Ativar a Economia de Memória

Essa função coloca abas inativas em "suspensão", economizando muita memória RAM e deixando o PC mais fluido.
- Abra o Chrome e clique nos três pontinhos no canto superior direito.
- Vá em Configurações.No menu lateral esquerdo, clique em Desempenho.
- Ative a Economia de memória. Pode escolher o nível entre "Equilibrada" ou "Máximo".

2. Desativar aplicativos em segundo plano

Evita que o navegador continue rodando e consumindo recursos mesmo depois que você o fecha.
- Configurações, clique em Sistema no menu lateral esquerdo.
- Desative a opção Executar aplicativos em segundo plano quando o Google Chrome estiver fechado.

3. Remover extensões que você não usa

As extensões ficam rodando o tempo todo e pesam bastante no navegador.
- Acesse a página chrome://extensions/ diretamente na barra de pesquisa.
- Analise sua lista e clique em Remover em todas as extensões que não são essenciais para você.

4. Limpar o cache e dados de navegação

Arquivos temporários acumulados podem deixar o carregamento lento.

- Pressione as teclas Ctrl + Shift + Del no seu teclado.
- Em "Período", selecione Todo o período.
- Marque apenas Imagens e arquivos armazenados em cache e Cookies e outros dados do site (evite apagar senhas, a menos que necessário).
- Clique em Limpar dados.

5. Ajustar a Aceleração de Hardware

- Vá em Configurações > Sistema.
- Se você tem um PC mais simples ou usa apenas placa de vídeo integrada, desative a Usar aceleração gráfica quando disponível. 
- Se você possui uma placa de vídeo dedicada (como NVIDIA ou AMD), deixe essa opção ativada para melhorar o desempenho.

6. Atualizar o navegador

Manter o Chrome na versão mais recente corrige falhas de segurança e melhora o desempenho.
- Vá em Configurações > Ajuda (no menu lateral) > Sobre o Google Chrome para verificar se há atualizações.