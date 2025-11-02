# installapps-macos-usb-no-packages

Script para instalar **vários apps `.pkg` no macOS via pendrive/USB**, de forma **offline**, com **log** e execução simples.  
> **Atenção:** este repositório **não inclui** arquivos `.pkg`. Cada usuário deve adicionar seus próprios pacotes em `AppPadrao/`.

---

## ✨ O que este projeto faz
- Instala todos os **`.pkg`** colocados na pasta `AppPadrao/`
- Remove a **quarentena** dos pacotes (evita bloqueios do Gatekeeper)
- Gera **log** em `~/Desktop/InstallApps.log`
- Funciona mesmo em pendrives **exFAT** (executa via `/bin/bash`, sem depender do bit “executável”)

---

## 🗂️ Estrutura recomendada do pendrive

/Volumes/InstallApps/
├─ install.sh # script principal (você já tem este arquivo)
└─ AppPadrao/ # adicione aqui os seus .pkg (não incluídos)

yaml
Copiar código

> **Nome do volume recomendado:** `InstallApps` (assim o caminho fica `/Volumes/InstallApps`).

---

## ▶️ Como executar no macOS

Com o pendrive montado como `/Volumes/InstallApps`, abra o **Terminal** e rode:

```bash
sudo /bin/bash "/Volumes/InstallApps/install.sh" | tee ~/Desktop/InstallApps.log
Dica: se você editou o install.sh em Windows, converta CRLF → LF antes de usar no Mac (ou regrave o arquivo no próprio macOS).

💾 Formato do pendrive
exFAT (se também usa Windows) — funciona com o comando acima via /bin/bash

APFS ou Mac OS Expandido (HFS+) (se só usar em Mac)

🧪 Troubleshooting rápido
“Nada acontece” — verifique:

bash
Copiar código
ls -l "/Volumes/InstallApps/install.sh"
ls -1 "/Volumes/InstallApps/AppPadrao"/*.pkg
sudo /bin/bash -x "/Volumes/InstallApps/install.sh"
sudo tail -n 200 /var/log/install.log


bash
Copiar código
xattr -dr com.apple.quarantine "/Volumes/InstallApps/AppPadrao/NOME-DO-PACOTE.pkg"
📦 O que não está neste repositório
Nenhum instalador .pkg de terceiros

Scripts para montar .dmg/.app (o foco aqui é .pkg)

🔒 Nota legal
Este projeto não distribui instaladores de terceiros.
Verifique as licenças dos softwares que você pretende instalar via .pkg.

🤝 Contribuições
PRs e sugestões são bem-vindos! Exemplos de melhorias: cronômetro de tempo, logs detalhados, detecção de pacotes problemáticos, etc.
