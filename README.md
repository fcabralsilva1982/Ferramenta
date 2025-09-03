# 🛠️ Menu de Suporte e Reparo - FUNESA

Este repositório contém um **script batch** (`.bat`) que cria um menu interativo de suporte técnico no **Windows**.  
O objetivo é fornecer acesso rápido a ferramentas de diagnóstico, manutenção e reparo do sistema, reunindo em um único menu comandos úteis para administradores e usuários avançados.

---

## ⚙️ Funcionamento do Script

O script utiliza comandos nativos do Windows, exibindo um **menu interativo** no Prompt de Comando.  
O usuário escolhe uma opção digitando o número correspondente (1 a 22), e o script executa a ação selecionada.

### Estrutura Principal:
1. **Cabeçalho** – Define título, cor e estilo da janela.
2. **Menu de opções** – Exibe uma lista numerada de ferramentas de suporte.
3. **Seleção do usuário** – Aguarda a entrada de um número.
4. **Execução do comando** – Executa a função correspondente.
5. **Loop infinito** – Após a execução, o menu é exibido novamente até que o usuário escolha `22 (Sair)`.

---

## 📋 Opções do Menu

| Nº | Função | Comando Executado |
|----|---------|------------------|
| 1  | Verificar e reparar disco | `chkdsk` |
| 2  | Reparar arquivos de sistema | `sfc /scannow` |
| 3  | Limpar arquivos temporários | `cleanmgr` |
| 4  | Diagnóstico de memória | `mdsched` |
| 5  | Restaurar sistema | `rstrui` |
| 6  | Testar conectividade de rede | `ping 8.8.8.8 -n 5` |
| 7  | Gerenciar processos | `taskmgr` |
| 8  | Backup de drivers (placeholder) | Exibe aviso |
| 9  | Verificar logs de atualização do Windows | `powershell -command "Get-WindowsUpdateLog"` |
| 10 | Informações do sistema | `systeminfo | more` |
| 11 | Limpar cache DNS | `ipconfig /flushdns` |
| 12 | Reiniciar serviços de rede | `netsh winsock reset` + `netsh int ip reset` |
| 13 | Desfragmentar disco | `defrag C:` |
| 14 | Gerenciar usuários locais | `lusrmgr.msc` |
| 15 | Verificar integridade com DISM | `DISM /Online /Cleanup-Image /ScanHealth` |
| 16 | Ativar/Desativar Firewall | `netsh advfirewall set allprofiles state off` |
| 17 | Visualizar logs de eventos | `eventvwr` |
| 18 | Testar velocidade do disco | `winsat disk` |
| 19 | Criar ponto de restauração | `powershell -Command "Checkpoint-Computer -Description 'Ponto de Restauracao Manual'"` |
| 20 | Executar comando personalizado | `cmd` |
| 21 | Atualizar programas via Winget | `winget update --all` |
| 22 | Sair do menu | `exit` |

---

## 🔒 Observações Importantes

- Algumas funções requerem **permissão de administrador** (por exemplo: SFC, DISM, reset de rede).  
- A opção **8 (Backup de drivers)** é apenas um **placeholder** e requer script adicional para funcionar.  
- A opção **16 (Firewall)** está configurada para **desativar o firewall**. Isso pode expor o sistema a riscos — use com cautela.  
- É recomendável executar o script em um ambiente de teste antes de aplicá-lo em máquinas de produção.  

---

## 🚀 Como Usar

1. Baixe ou copie o arquivo `.bat`.
2. Clique com o botão direito e selecione **Executar como administrador**.
3. Escolha a opção desejada no menu digitando o número correspondente.
4. O menu será exibido novamente até que a opção `22 (Sair)` seja selecionada.

---

## 👨‍💻 Autor

Script criado por **Pablo Oliveira** – versão **1.0**.  
Documentação adaptada para GitHub.

