# 🇧🇷 Instalação Automatizada do Ubuntu Desktop 24.04 – Versão Brasileira

**Desenvolvido por Vitor Cruz – Licença GPLv3**

Este projeto fornece um arquivo `autoinstall.yaml` para instalação automática do **Ubuntu Desktop 24.04 LTS**, com configurações ideais para usuários brasileiros em ambientes corporativos, educacionais e governamentais.

## ✨ Funcionalidades

- 🌐 Suporte completo ao idioma **português do Brasil** (sistema, LibreOffice, Thunderbird)
- ⌨️ Teclado **ABNT2** e fuso horário de **São Paulo**
- 🔒 **Privacidade aprimorada**, com remoção de telemetria e software indesejado
- 📦 Instalação de:
  - **LibreOffice completo** com ajuda e tradução PT-BR
  - **Thunderbird PT-BR**
  - **OnlyOffice (Snap)**
  - **Codecs multimídia** e **fontes da Microsoft**
  - **GNOME Weather** via Snap, com localização padrão no Rio de Janeiro
  - **GNOME Software** com suporte a Snap e Flatpak
- ⚡ Otimizações de desempenho com `preload` e `zram-tools`
- 🛡️ **Firewall UFW** ativado com regras seguras
- 🌐 **RDP nativo (GNOME Remote Desktop)** e **OpenSSH** ativados
- 🖱️ Dock do Ubuntu movido para a base da tela, com botão de menu à esquerda
- 🧩 GNOME Extensions App incluído (sem pré-instalar extensões)

## 🖥️ Requisitos

- Imagem ISO oficial do Ubuntu Desktop 24.04 LTS
- Pendrive com o instalador modificado
- BIOS/UEFI em modo UEFI (recomendado)

## ⚙️ Como usar

1. Baixe a ISO oficial do Ubuntu Desktop 24.04 LTS
2. Crie um pendrive bootável com a ISO (usando Rufus, balenaEtcher ou ferramenta de sua preferência)
3. Monte a partição `writable` do pendrive
4. Crie a seguinte estrutura de diretórios:

```bash
/writable/
└── autoinstall/
    └── autoinstall.yaml
Copie o arquivo autoinstall.yaml deste repositório para a pasta autoinstall

Inicie o computador pelo pendrive e selecione a opção Instalação automática

A instalação será iniciada e concluída automaticamente com as personalizações incluídas.

```
🔐 Como definir a senha
A senha do usuário padrão administrador está definida por hash. Para gerar o hash de uma nova senha, execute:

```bash
openssl passwd -6
Substitua o conteúdo da linha abaixo no arquivo autoinstall.yaml:
```

```bash
password: "$6$rounds=4096$...seu_hash_aqui..."
```

📜 Licença
Este projeto está licenciado sob a GNU General Public License v3.0 (GPL-3.0).
Você é livre para usar, modificar e distribuir, desde que mantenha os créditos e licencie derivados sob os mesmos termos.
