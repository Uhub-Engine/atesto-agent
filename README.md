# Atesto agent — releases

**Português** · [English](#english)

Este repositório só distribui o agente do Atesto. Cada versão traz os binários para macOS (Apple Silicon e Intel) e Windows (x64), e o arquivo `SHA256SUMS`. O código-fonte não fica aqui.

## Como instalar

Pelo comando que a tela **Dispositivos** do Atesto gera. Ele já leva a chave de instalação da sua organização, baixa o binário daqui, confere o SHA-256 contra o valor que o servidor do Atesto informa e instala o serviço. Se o hash não bater, nada é instalado.

## Conferir à mão

Baixe o binário e o `SHA256SUMS` da mesma versão e compare:

- macOS: `shasum -a 256 atesto-sentinel-darwin-arm64`
- Windows: `Get-FileHash .\atesto-sentinel-windows-amd64.exe -Algorithm SHA256`

## O que o agente faz

Lê e só lê: o nome da máquina, o número de série e se ela é gerenciada pela empresa; a versão do sistema; a configuração de segurança (criptografia de disco, firewall, antivírus, bloqueio de tela, Secure Boot e atualizações); os programas instalados; as ferramentas de IA instaladas ou rodando; e o nome da conta que usa a máquina, que a empresa pode desligar. Não altera nada na máquina e nunca lê conteúdo de arquivo, e-mail ou mensagem, a tela, a área de transferência, os sites visitados, as teclas digitadas nem conversas com ferramentas de IA.

## Assinatura

Os binários ainda não têm assinatura de código da Apple e da Microsoft; ela entra numa versão próxima. Até lá, o SHA-256 é a forma de conferir a integridade.

---

## English

This repository only distributes the Atesto agent. Each release ships the binaries for macOS (Apple Silicon and Intel) and Windows (x64), plus a `SHA256SUMS` file. The source code does not live here.

**Install** with the command the Atesto **Devices** screen generates. It carries your organization's install key, downloads the binary from here, checks its SHA-256 against the value the Atesto server reports, and installs the service. If the hash does not match, nothing is installed.

**Verify by hand** by comparing the binary with the `SHA256SUMS` of the same release: `shasum -a 256 <file>` on macOS, `Get-FileHash <file> -Algorithm SHA256` on Windows.

**What the agent does:** it reads, and only reads — the machine's name, serial number and whether the company manages it; the OS version; the security configuration (disk encryption, firewall, antivirus, screen lock, Secure Boot and updates); installed programs; the AI tools installed or running; and the name of the account using the machine, which the company can switch off. It changes nothing on the machine and never reads file, e-mail or message content, the screen, the clipboard, visited sites, keystrokes or conversations with AI tools.

**Signing:** the binaries are not yet code-signed by Apple and Microsoft; that comes in an upcoming release. Until then, the SHA-256 is how integrity is checked.
