<p align="center">
  <img src="./assets/banner.png" alt="0xDepCheck Banner" width="100%">
</p>

# 0xDepCheck 🏴‍☠️

Ferramenta de validação para **Dependency Confusion**.

O 0xDepCheck verifica a disponibilidade de pacotes e organizações no registro público do NPM para confirmar se uma dependência interna pode ser sequestrada.

## Funcionalidades
* **Automated Validation:** Checa se o pacote retorna 404 (livre) no registro oficial.
* **Org Hijacking Check:** Verifica se a organização do escopo está disponível para registro.
* **Smart Logic:** Diferencia pacotes globais de pacotes escopados automaticamente.
* **Bug Bounty Ready:** Focado em agilizar o PoC (Proof of Concept) para reportes de segurança.

## ⚙️ Instalação Global
Para facilitar o uso durante o reconhecimento (recon), instale o `0xDepCheck` globalmente:

```
# Dar permissão de execução
chmod +x 0xDepCheck
```
```
# Mover para o diretório de binários
sudo mv 0xDepCheck /usr/local/bin/
```
