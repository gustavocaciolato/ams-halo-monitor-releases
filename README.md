# AMS Halo Monitor — releases

Monitor em terminal dos chamados Halo em status **Novo** nas filas AMS. Este repositório público só publica as releases (pacote, SHA256 e instaladores) para instalar e atualizar o app **sem token do GitHub**.

**Autor:** Gu Caciolato (Quality Digital)

## Instalar

macOS e Linux (Terminal):

```bash
curl -fsSL https://github.com/gustavocaciolato/ams-halo-monitor-releases/releases/latest/download/install.sh | bash
```

Windows (PowerShell):

```powershell
irm https://github.com/gustavocaciolato/ams-halo-monitor-releases/releases/latest/download/install.ps1 | iex
```

O instalador procura o Python 3.10+ (instala pelo Homebrew ou pelo winget se faltar), baixa a última release, confere o SHA256, cria o ambiente, deixa um atalho e abre o app.

Na primeira execução o app pede o **client secret do Halo** dentro do próprio TUI (o texto fica oculto) e o guarda só no seu computador. Ninguém digita token do GitHub.

## Atualizar

Dentro do app, pressione `u`, ou rode o instalador de novo. O `.env`, o `config.toml` e o banco `alertas.db` são preservados.

## Alerta

Cada chamado novo toca o áudio do Bob Esponja triste (configurável em `som_alerta` no `config.toml`) e mostra a notificação do sistema. O app guarda em um SQLite local os números dos chamados já alertados para não repetir o aviso.

## Conferir o download

Cada release traz o arquivo `SHA256SUMS`. Os instaladores já fazem essa conferência e não instalam nada se o valor não bater.
