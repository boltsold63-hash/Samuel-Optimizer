# SAMUEL OPTIMIZER — Windows Performance Toolkit
Desenvolvido por **SAMUEL**. Ferramenta de otimização do Windows 10/11 (64 bits) executada no terminal.
C# (.NET 8) no aplicativo principal + PowerShell embutido para operações nativas do Windows.

## Gerar o executável (um comando)
Em um Windows com o **.NET SDK 8** instalado, na pasta do projeto, no PowerShell:

```powershell
.\build.ps1
```
Saídas em `dist\`: `SamuelOptimizer-1.0.0-portable-win-x64.zip` (portátil) e `SamuelOptimizer-1.0.0-setup.exe`
(instalador, se o Inno Setup 6 estiver instalado; senão, `...-installer-win-x64.zip` com `Instalar.cmd`).
O `.exe` é self-contained: o usuário final não instala nada.

Sem Windows local? Suba a pasta num repositório GitHub: o workflow `.github/workflows/build.yml` compila tudo e publica os arquivos como artefato.

## Estrutura
```
src/SamuelOptimizer/
  Program.cs, MainMenu.cs, SelfTest.cs
  Core/      UI, log, diário de backup, registro, tweaks, limpeza, inicialização, processos, PowerShell...
  Modules/   um arquivo por módulo do menu (14 módulos)
  Scripts/   scripts PowerShell embutidos no .exe (somente leitura)
installer/   Inno Setup (.iss) + instalador alternativo
docs/        MANUAL.md, FUNCIONALIDADES.md, LIMITACOES.md
build.ps1    compila, testa, empacota
```
Comandos úteis: `SamuelOptimizer.exe --selftest` (autotestes, não alteram o sistema), `--version`.
