# Instalação Automatizada do Ubuntu Desktop 24.04 LTS / 25.04 – Versão Brasileira 🇧🇷

**Desenvolvido por Vitor Cruz – Licença GPLv3**

Este projeto fornece um arquivo `autoinstall.yaml` para instalação **totalmente automatizada** do Ubuntu Desktop, com foco em:

- Segurança corporativa, produtividade imediata, remoção de telemetria, desempenho otimizado
- Pronto para uso doméstico, corporativo, educacional, governamental
- Suporte completo ao Brasil
- Configuração regional para o Brasil (pt_BR.UTF-8, teclado ABNT2) e fuso horário de **São Paulo**
- Instalação de:
  - **LibreOffice** (completo com ajuda e tradução PT-BR)
  - **Mozilla Firefox (Snap)** 
  - **Thunderbird (Snap)** (tradução PT-BR)
  - **OnlyOffice (Snap)**
  - **Codecs multimídia** e **fontes da Microsoft**
  - **GNOME Weather** via Snap, com localização padrão no Rio de Janeiro
  - **GNOME Software** com suporte a Snap e Flatpak
- **Firewall UFW** ativado com regras seguras, permitindo RDP e SSH (Logging ativado)
- Suporte completo a Flatpak, Snap em Português do Brasil (pt-br)
- Otimizações de desempenho com `preload` e `zram-tools`
- **Privacidade aprimorada**, com remoção de telemetria e software indesejado
- Otimizações inspiradas no [sysboost.sh](https://github.com/vitorcruzfaculdade/sysboost.sh)

---

## ✨ Funcionalidades principais

| Área              | Descrição                                                                                      |
|-------------------|------------------------------------------------------------------------------------------------|
| **Localização**   | Português do Brasil e Europeu (sistema, LibreOffice, Thunderbird, GNOME)                       |
| **Produtividade** | LibreOffice, Thunderbird, Firefox, Google Chrome, OnlyOffice (Snap), Flatpak, Snap Store       |
| **Segurança**     | UFW, Fail2Ban, ClamAV, AppArmor, bloqueio root SSH, remoção de telemetria, hardening de kernel |
| **Desempenho**    | preload, zram, mesa, vulkan, firmware atualizado                                               |
| **Acessórios**    | GNOME Weather, Cheese, codecs, fontes, extensões GNOME                                         |

---

Compatível com:

- **Ubuntu Desktop 24.04 LTS (Noble Numbat)**  
- **Ubuntu Desktop 25.04 (Plucky Puffin)**

---

## 🚀 Instalação automática via Subiquity (método mais simples e recomendado)

Você pode usar a **ISO oficial do Ubuntu Desktop** diretamente, sem modificar ou remasterizar nada.

O instalador gráfico (Subiquity) possui uma opção chamada **"Instalação Automatizada"**, onde você pode colar diretamente a URL do arquivo `autoinstall.yaml` hospedado neste repositório, ou uma cópia em um endereço local seu caso prefira.

### 🧭 Como fazer:

1. Baixe e grave a ISO oficial do Ubuntu Desktop (24.04 ou 25.04)
2. Inicie o computador pelo pendrive
3. Na tela de boas-vindas, clique em **“Instalação Automatizada”**
4. Digite o seguinte link no campo solicitado:

```
https://raw.githubusercontent.com/vitorcruzfaculdade/autoinstall.yaml/refs/heads/main/autoinstall.yaml
```

5. A instalação será executada com todas as configurações e softwares definidos

### ✅ Vantagens

- Nenhuma ISO modificada
- Nenhuma configuração de GRUB
- Atualizações futuras no YAML são aplicadas automaticamente

---

## 🖥️ Requisitos

- ISO oficial do Ubuntu Desktop 24.04 LTS ou 25.04  
- Pendrive de instalação ou rede com acesso HTTP/HTTPS  
- BIOS/UEFI preferencialmente em modo UEFI  

---

## 🔐 Definir a senha do usuário administrador

O usuário padrão se chama `administrador`. A senha está armazenada no arquivo como **hash** por segurança.

### Para definir sua própria senha:

1. No terminal, gere um hash com:

```bash
openssl passwd -6
```

2. Copie a saída e substitua no campo `password:` dentro do YAML:

```yaml
password: "$6$rounds=4096$...seuhashgeradoaqui..."
```

---

## ⚙️ Alternativa: Instalação via rede (NoCloud)

Você também pode hospedar o arquivo `autoinstall.yaml` em um servidor HTTP local (sem usar GitHub) e apontar o instalador para ele via GRUB:

### Estrutura esperada:

```
/autoinstall/
├── user-data     ← renomeie o autoinstall.yaml
└── meta-data     ← pode ser um arquivo vazio
```

### Servidor HTTP local:

```bash
cd /caminho/para/autoinstall/
python3 -m http.server 80
```

### Parâmetro de boot (pressione `e` no GRUB):

```
autoinstall ds=nocloud-net;s=http://IP_DO_SERVIDOR/autoinstall/
```

---

## 📜 Licença

Este projeto está licenciado sob a **GNU General Public License v3.0 (GPL-3.0)**.  
Você pode usar, modificar e redistribuir livremente, desde que mantenha os créditos e distribua sob a mesma licença.

---

## 🙋 Autor

**Vitor Cruz**  
Feito usando 💻☕ , com ❤️ para a comunidade brasileira de software livre.

- [Linktree](https://linktr.ee/vitorcruzcode)
- [GitHub](https://github.com/vitorcruzfaculdade)
