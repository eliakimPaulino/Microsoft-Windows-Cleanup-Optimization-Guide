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