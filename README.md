# autoinstall.yaml
Instalação Automatizada do Ubuntu Desktop 24.04 LTS – Versão Brasileira 🇧🇷
🇧🇷 Instalação Automatizada do Ubuntu Desktop 24.04 – Versão Brasileira
Desenvolvido por Vitor Cruz – Licença GPLv3

Este projeto fornece um arquivo autoinstall.yaml para instalação automática do Ubuntu Desktop 24.04 LTS, com configurações voltadas para:

✅ Usuários brasileiros (idioma, teclado, fuso horário)
✅ Eliminação de telemetria
✅ LibreOffice completo com tradução e ajuda offline
✅ OnlyOffice (Snap) incluso
✅ GNOME Weather com localização padrão no Rio de Janeiro
✅ Suporte completo a Snap e Flatpak via GNOME Software
✅ RDP nativo via GNOME e SSH já ativados
✅ Thunderbird traduzido para o português do Brasil
✅ GNOME Dock ajustado para a base da tela com botão inicial à esquerda
✅ Configuração ideal para escolas, repartições públicas, escritórios e uso geral no Brasil
✅ Firewall UFW configurado e ativo
✅ Instalação de codecs, fontes da Microsoft, e suporte multimídia

⚙️ Requisitos
Ubuntu Desktop 24.04 LTS ISO oficial

Pendrive com o instalador customizado (veja instruções abaixo)

BIOS configurada para modo UEFI (preferencial)

🧰 Como usar
Baixe a ISO oficial do Ubuntu Desktop 24.04 LTS

Crie um pendrive bootável com a ISO usando Rufus, balenaEtcher, etc.

Monte a partição writable do pendrive e crie a seguinte estrutura:

bash
Copy
Edit
/writable/
└── autoinstall/
    └── autoinstall.yaml
Copie o arquivo autoinstall.yaml deste repositório para dentro da pasta

Inicie o computador com o pendrive e selecione "Instalação automática"

O instalador seguirá o procedimento padrão, com personalizações descritas acima, sem interação humana.

🔐 Senha do usuário
A senha do usuário administrador está definida via hash. Para gerar uma nova senha, utilize:

bash
Copy
Edit
openssl passwd -6
Copie o hash gerado e substitua o valor em:

yaml
Copy
Edit
password: "$6$rounds=4096$..."
📜 Licença
Este projeto é distribuído sob a Licença GPLv3.

