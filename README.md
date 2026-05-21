# Microsoft Windows Cleanup & Optimization Guide

Complete Windows maintenance, cleanup, repair, and optimization guide for gaming and daily use.

---

# Antes de começar

- Feche programas abertos.
- Crie um ponto de restauração do Windows.
- Atualize o Windows Update antes da manutenção.
- Reinicie o PC se ele estiver ligado há muitos dias.

---

# 1. Limpeza básica de arquivos temporários

## TEMP

```bat
temp
```

Apague tudo.

## %TEMP%

```bat
%temp%
```

Apague tudo.

## PREFETCH

```bat
prefetch
```

Apague tudo.

---

# 2. Limpeza do sistema Windows

Execute como Administrador:

```bat
cleanmgr
```

Marque:

- Windows Update Cleanup
- Temporary Files
- Delivery Optimization Files
- DirectX Shader Cache
- Recycle Bin

---

# 3. Reparação da imagem do Windows (DISM)

```bat
DISM /Online /Cleanup-Image /RestoreHealth
```

---

# 4. Verificação de integridade do sistema (SFC)

```bat
sfc /scannow
```

---

# 5. Desativar programas de inicialização

Abrir:

```bat
taskmgr
```

Ir em:

```text
Inicializar
```

Desativar programas desnecessários.

## NÃO desative:

- NVIDIA Drivers
- AMD Drivers
- Intel Drivers
- Windows Security
- Drivers de áudio
- TouchPad

---

# 6. Desativar serviços desnecessários

Abrir:

```bat
services.msc
```

## Serviços que podem ser desativados com baixo risco

- Fax
- Xbox Services
- Remote Registry
- Connected User Experiences and Telemetry

## Melhor deixar como MANUAL

- Bluetooth → apenas se não usa
- Print Spooler → não desative se usa impressora
- Windows Search → pode piorar pesquisas
- SysMain → testar antes; SSD moderno pode não precisar

---

# 7. Remover aplicativos desnecessários

## Listar aplicativos

```bat
winget list
```

## Pesquisar aplicativo

```bat
winget list nome_do_programa
```

## Desinstalar

```bat
winget uninstall PROGRAMA
```

## Se houver nomes duplicados

```bat
winget uninstall --id ID_DO_PROGRAMA
```

---

# 8. Ativar Ultimate Performance

```bat
powercfg -duplicatescheme e9a42b02-d5df-448d-aa00-03f14749eb61
```

Depois:

```text
Painel de Controle → Opções de Energia
```

Selecionar:

```text
Ultimate Performance
```

---

# 9. Otimizações de Registro

## Network Throttling

```bat
reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile" /v NetworkThrottlingIndex /t REG_DWORD /d 4294967295 /f
```

## System Responsiveness

```bat
reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Multimedia\SystemProfile" /v SystemResponsiveness /t REG_DWORD /d 0 /f
```

## Win32 Priority Separation

```bat
reg add "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\PriorityControl" /v Win32PrioritySeparation /t REG_DWORD /d 38 /f
```

## Telemetria

```bat
reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\DataCollection" /v AllowTelemetry /t REG_DWORD /d 0 /f
```

---

# Observações importantes

## NetworkThrottlingIndex

Pode ajudar em:

- Jogos online
- Redução de latência

## SystemResponsiveness

Pode ajudar em:

- Games
- Prioridade para aplicações em foreground

## Win32PrioritySeparation

Muito usado em tweaks gamer.

## AllowTelemetry

Reduz telemetria do Windows.

Pode afetar:

- Xbox Services
- Diagnósticos
- Recursos do Windows

---

# 10. Reinicialização FINAL

Reinicie o PC após tudo.

Importante para aplicar:

- Serviços
- Registro
- Power Plan
- Cache rebuild

---

# EXTRAS

# Verificar disco

```bat
chkdsk /scan
```

---

# Ver drivers instalados

## Lista simples

```bat
driverquery
```

## Lista detalhada

```bat
driverquery /v
```

## Exportar para TXT

```bat
driverquery /v > C:\drivers.txt
```

---

# Ver versões dos drivers

## Nome + versão

```bat
wmic path win32_pnpsigneddriver get deviceName,driverVersion
```

## Nome + versão + fabricante

```bat
wmic path win32_pnpsigneddriver get deviceName,driverVersion,manufacturer
```

---

# Ver dispositivos com problema

```bat
pnputil /enum-devices /problem
```

Pode identificar:

- Drivers faltando
- Drivers corrompidos
- Conflitos

---

# Ver todos os drivers do sistema

```bat
pnputil /enum-drivers
```

---

# Atualizar drivers via Windows Update

## Instalar módulo

```powershell
Install-Module PSWindowsUpdate
```

## Procurar atualizações

```powershell
Get-WindowsUpdate
```

## Instalar atualizações

```powershell
Install-WindowsUpdate
```

---

# Ferramentas úteis

## Informações completas do sistema

```bat
msinfo32
```

## Diagnóstico DirectX/GPU

```bat
dxdiag
```

---

# Melhor sequência prática

1. Verificar dispositivos com problema:

```bat
pnputil /enum-devices /problem
```

2. Atualizar Windows Update

3. Atualizar GPU pelo software oficial

- NVIDIA App
- AMD Adrenalin
- Intel Driver Assistant

4. Atualizar chipset pelo site da fabricante

5. Revisar drivers:

```bat
driverquery /v
```

---

# Google Chrome Optimization

# 1. Ativar Economia de Memória

```text
Configurações → Desempenho → Economia de memória
```

Usar:

- Equilibrada
- Máximo

---

# 2. Desativar apps em segundo plano

```text
Configurações → Sistema
```

Desativar:

```text
Executar aplicativos em segundo plano quando o Google Chrome estiver fechado
```

---

# 3. Remover extensões desnecessárias

Abrir:

```text
chrome://extensions/
```

Remover extensões que não usa.

---

# 4. Limpar cache do Chrome

Atalho:

```text
Ctrl + Shift + Del
```

Selecionar:

- Todo o período
- Imagens e arquivos armazenados em cache
- Cookies e outros dados do site

Evite apagar senhas sem necessidade.

---

# 5. Ajustar aceleração de hardware

```text
Configurações → Sistema
```

## Recomendações

### GPU dedicada (NVIDIA/AMD)

Deixar ativado.

### GPU integrada / PC simples

Testar desativado.

---

# 6. Atualizar Chrome

```text
Configurações → Ajuda → Sobre o Google Chrome
```

---

# SSD

## Verificar TRIM

```bat
fsutil behavior query DisableDeleteNotify
```

Resultado esperado:

```text
DisableDeleteNotify = 0
```

---

# Monitorar RAM

```bat
resmon
```

ou:

```bat
taskmgr
```

---

# Temperaturas

Ferramentas úteis:

- HWMonitor
- HWiNFO64
- MSI Afterburner

---

# Reinício final recomendado

```text
REINICIE O COMPUTADOR
```

Para aplicar:

- Tweaks
- Serviços
- Drivers
- Registro
- Power Plan
- Cache rebuild

---