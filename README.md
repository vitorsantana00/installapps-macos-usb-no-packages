## Passo a passo (bem simples)

1) **Formate o pendrive em APFS**  
   - Abra **Utilitário de Disco** → selecione o pendrive → **Apagar**  
   - **Nome:** `InstallApps`  •  **Formato:** `APFS`  •  **Esquema:** `GUID`

2) **Descompacte o ZIP** do projeto no seu computador.

3) **Copie para o pendrive** (raiz do volume `InstallApps`):
   - `install.sh`
   - pasta `AppPadrao/`

4) **Coloque somente arquivos `.pkg`** dentro de `AppPadrao/`.  
   > Não coloque `.dmg` nem `.app` — o script instala apenas `.pkg`.

5) **Execute no macOS** (com o pendrive montado):
   ```bash
   sudo /bin/bash "/Volumes/InstallApps/install.sh" | tee ~/Desktop/InstallApps.log
