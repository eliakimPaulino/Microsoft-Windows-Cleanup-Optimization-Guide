# Microsoft Windows Cleanup & Optimization Guide

Complete Windows maintenance, cleanup, repair, and optimization guide for gaming and daily use.

---

# Antes de começar

- Fechar programas abertos.
- Criar um ponto de restauração do Windows.
- Atualizar o Windows Update antes da manutenção.
- Reiniciar o PC se ele estiver ligado há muitos dias.

---
# 🚀 Seção 1 - Como Desativar Serviços Desnecessários do Windows e Melhorar o Desempenho

> Este guia mostra como reduzir o consumo de RAM, CPU e processos em segundo plano no Windows desativando serviços desnecessários.

---
### Benefícios:
- ✅ Menor uso de RAM
- ✅ Menor uso de CPU
- ✅ Menos processos rodando
- ✅ Sistema mais rápido
- ✅ Menos travamentos
- 
---

# 🛡️ PASSO 1 — Criar um ponto de restauração

## Abrindo a ferramenta

1. Abra o menu **Iniciar**
2. Pesquise:

```text
Criar ponto de restauração
```

3. Abra o aplicativo

---

## Ativando a proteção do sistema

Na janela aberta:

1. Selecione o disco onde o Windows está instalado (`C:`)
2. Clique em:

```text
Configurar
```

3. Marque:

```text
Ativar proteção do sistema
```

4. Em **Uso máximo**, selecione:
- Entre `4%` e `5%`

5. Clique em:
- `Aplicar`
- `OK`

---

## Criando o ponto de restauração

1. Clique em:

```text
Criar
```

2. Digite um nome:

```text
Antes da otimização
```

3. Clique novamente em:

```text
Criar
```

4. Aguarde finalizar

---

# ⚙️ PASSO 2 — Abrir os Serviços do Windows

## Método 1 — Pelo menu iniciar

1. Abra o menu **Iniciar**
2. Pesquise:

```text
Serviços
```

3. Abra o aplicativo

---

## Método 2 — Pelo Gerenciador de Tarefas

1. Pressione:

```text
Ctrl + Shift + Esc
```

2. Vá na aba:

```text
Serviços
```

3. Clique nos três pontinhos (`⋮`)
4. Clique em:

```text
Abrir Serviços
```

---

# 📋 PASSO 3 — Organizar os serviços

Para facilitar:

1. Clique na coluna:

```text
Nome
```

Assim os serviços ficarão em ordem alfabética.

---

# 🧠 PASSO 4 — Verificar a versão do Windows

1. Pressione:

```text
Win + R
```

2. Digite:

```text
winver
```

3. Pressione `Enter`

### Exemplo:
- Windows 11 Pro
- Versão 24H2

---

# 🔥 PASSO 5 — Desativar serviços desnecessários

---

# 1️⃣ Cartão Inteligente

## Função
Gerencia cartões inteligentes usados para autenticação.

## Pode desativar se:
- Você NÃO usa crachá corporativo
- Você NÃO usa autenticação por cartão

## Configuração

| Atual | Novo |
|---|---|
| Manual | Desativado |

### Como aplicar
1. Clique duas vezes no serviço
2. Em **Tipo de inicialização**, escolha:

```text
Desativado
```

3. Clique em:
- `Aplicar`
- `OK`

---

# 2️⃣ Configuração da Área de Trabalho Remota

## Função
Gerencia conexões remotas ao computador.

## Pode desativar se:
- Você NÃO acessa o PC remotamente

## Configuração

| Atual | Novo |
|---|---|
| Automático | Desativado |

### Como aplicar
1. Clique duas vezes no serviço
2. Altere para:

```text
Desativado
```

3. Clique em:

```text
Parar
```

4. Depois:
- `Aplicar`
- `OK`

---

# 3️⃣ Controles Parentais

## Função
Controle de uso do computador para crianças.

## Pode desativar se:
- Você não usa controle parental

## Configuração

| Atual | Novo |
|---|---|
| Automático | Desativado |

### Aplicação
1. Alterar para:

```text
Desativado
```

2. Clique em:
- `Parar`
- `Aplicar`
- `OK`

---

# 4️⃣ Diagnóstico de Execução de Serviços

## Função
Executa diagnósticos automáticos do sistema.

## Configuração

| Atual | Novo |
|---|---|
| Manual | Desativado |

### Aplicação
1. Altere para:

```text
Desativado
```

2. Clique em:
- `Aplicar`
- `OK`

---

# 5️⃣ Experiências do Usuário Conectado e Telemetria

## Função
Coleta e envia dados de uso para a Microsoft.

## Benefícios ao desativar
- Mais privacidade
- Menor uso de recursos

## Configuração

| Atual | Novo |
|---|---|
| Automático | Desativado |

### Aplicação
1. Altere para:

```text
Desativado
```

2. Clique em:
- `Parar`
- `Aplicar`
- `OK`

---

# 6️⃣ Gerenciador de Autenticação Xbox Live

## Função
Serviços relacionados ao Xbox.

## Pode desativar se:
- Você NÃO usa Xbox no PC

## Configuração

| Novo |
|---|
| Desativado |

### Aplicação
1. Altere para:

```text
Desativado
```

2. Clique em:
- `Parar`
- `Aplicar`
- `OK`

---

# 7️⃣ Serviço de Geolocalização

## Função
Fornece localização para aplicativos.

## Pode desativar se:
- Você não usa aplicativos de localização

## Configuração

| Atual | Novo |
|---|---|
| Manual | Desativado |

### Aplicação
1. Altere para:

```text
Desativado
```

2. Clique em:
- `Parar`
- `Aplicar`
- `OK`

---

# 8️⃣ Serviço de Hotspot Móvel

## Função
Compartilha internet do PC via Wi-Fi.

## Pode desativar se:
- Você não usa hotspot

## Configuração

| Novo |
|---|
| Desativado |

---

# 9️⃣ Serviço de Relatório de Erro do Windows

## Função
Envia relatórios de erro para a Microsoft.

## Benefícios
- Menor uso de recursos

## Configuração

| Novo |
|---|
| Desativado |

---

# 🔟 Serviço de Suporte a Bluetooth

## Função
Gerencia dispositivos Bluetooth.

## Pode desativar se:
- Você NÃO usa Bluetooth

## Configuração

| Novo |
|---|
| Desativado |

---

# 1️⃣1️⃣ SysMain (Superfetch)

## Função
Pré-carrega aplicativos na memória RAM.

## Problemas comuns
- HD em 100%
- Alto uso de disco
- Lentidão
- Travamentos

## Recomendado desativar se:
- Seu PC está lento
- O disco fica constantemente em 100%

## Configuração

| Novo |
|---|
| Desativado |

### Aplicação
1. Altere para:

```text
Desativado
```

2. Clique em:
- `Parar`
- `Aplicar`
- `OK`

---

# 🔄 PASSO 6 — Reiniciar o computador

Depois de finalizar todas as alterações:

1. Reinicie o computador
2. Aguarde o Windows iniciar normalmente

---

# 📊 PASSO 7 — Verificar o resultado

## Abrir o Gerenciador de Tarefas

Pressione:

```text
Ctrl + Shift + Esc
```

---

## Verificando os processos

Na aba **Processos**, veja quantos processos estão em execução.

### Exemplo do vídeo:
- Antes: `147`
- Depois: `81`

---

# ✅ Melhorias esperadas

Após a otimização você pode perceber:

- 🚀 Inicialização mais rápida
- 🚀 Menor uso de RAM
- 🚀 Menor uso de CPU
- 🚀 Menos processos em segundo plano
- 🚀 Sistema mais fluido
- 🚀 Menos travamentos

---

# ⚠️ Serviços que você NÃO deve desativar

Evite desativar:
- Windows Update
- Áudio do Windows
- Plug and Play
- RPC
- Serviços de rede
- Serviços gráficos
- Serviços de drivers

---

# 💡 Dicas extras de otimização

## Desative programas da inicialização

1. Abra o Gerenciador de Tarefas
2. Vá em:

```text
Inicializar Aplicativos
```

3. Desative programas desnecessários

---

## Limpe arquivos temporários

Pressione:

```text
Win + R
```

Digite:

```text
temp
```

E apague os arquivos.

Repita com:

```text
%temp%
```

---

## Use SSD
Se ainda usa HD, trocar para SSD traz MUITO mais desempenho.

---

## Mantenha drivers atualizados

Principalmente:
- Placa de vídeo
- Chipset
- Rede

---

# 🧯 Como restaurar caso algo dê errado

1. Pesquise:

```text
Criar ponto de restauração
```

2. Clique em:

```text
Restauração do Sistema
```

3. Escolha o ponto criado anteriormente

---

# 🎯 Conclusão

Desativar serviços desnecessários pode reduzir significativamente o consumo de recursos do Windows e melhorar a fluidez do sistema.

Os ganhos variam dependendo:
- da versão do Windows
- do hardware
- da quantidade de programas instalados

Mas, no geral, o sistema tende a ficar:
- mais leve
- mais rápido
- mais responsivo

---
---

# Seção 2 - Limpeza básica de arquivos temporários

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

# 3° seção - Google Chrome Optimization

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
