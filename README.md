# Instalação Automatizada do Ubuntu Desktop 24.04 – Versão Brasileira 🇧🇷

**Desenvolvido por Vitor Cruz – Licença GPLv3**

Este projeto fornece um arquivo `autoinstall.yaml` para instalação automática do **Ubuntu Desktop 24.04 LTS**, com configurações ideais para usuários brasileiros em ambientes corporativos, educacionais e governamentais.

Este projeto utiliza o recurso de instalação automatizada (`autoinstall`) do Ubuntu 24.04, com foco em:

- Remoção de telemetria
- Instalação de codecs, fontes e pacotes essenciais
- Configuração regional para o Brasil (pt_BR.UTF-8, teclado ABNT2)
- Ativação de firewall, RDP e SSH
- Suporte completo a Flatpak, Snap, OnlyOffice, Thunderbird em PT-BR
- Otimizações inspiradas no [sysboost.sh](https://github.com/vcruz/sysboost.sh)
- Pronto para uso doméstico, empresarial e educacional

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
## 🌐 Instalação via rede (sem ISO personalizada)

Você pode usar este arquivo `autoinstall.yaml` sem precisar recriar uma ISO personalizada do Ubuntu. Basta hospedá-lo em um servidor HTTP local ou remoto e apontar a instalação para ele com o parâmetro de boot:

### 1. Estrutura no servidor HTTP

No servidor HTTP (ex: um notebook com Python):

```
/autoinstall/
├── user-data        ← renomeie seu autoinstall.yaml para "user-data"
└── meta-data        ← pode ser um arquivo vazio
```

### 2. Hospedar via Python (modo rápido)

```bash
cd /caminho/para/autoinstall/
python3 -m http.server 80
```

### 3. Parâmetro de boot no Ubuntu (pressione `e` no GRUB)

Adicione na linha que começa com `linux`:

```text
autoinstall ds=nocloud-net;s=http://192.168.0.10/autoinstall/
```

> O Subiquity buscará automaticamente o arquivo `user-data` e executará a instalação automática com base nele.

---

📜 Licença
Este projeto está licenciado sob a GNU General Public License v3.0 (GPL-3.0).
Você é livre para usar, modificar e distribuir, desde que mantenha os créditos e licencie derivados sob os mesmos termos.

🙋 Autor
Desenvolvido por Vitor Cruz, com ❤️ para a comunidade brasileira de software livre.

