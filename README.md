# installapps-macos-usb-no-packages

Script para instalar **vários apps `.pkg` no macOS via pendrive/USB**, de forma **offline**, com **log** e execução simples.  
> **Atenção:** este repositório **não inclui** arquivos `.pkg`. Cada usuário deve adicionar seus próprios pacotes dentro de `AppPadrao/`.

## ✨ O que este projeto faz
- Instala todos os **`.pkg`** colocados em `AppPadrao/`
- Remove a **quarentena** dos pacotes (evita bloqueios do Gatekeeper)
- Gera **log** em `~/Desktop/InstallApps.log`
- Pode rodar mesmo em pendrives **exFAT** (não depende do bit executável)

## 🗂️ Estrutura recomendada do pendrive
