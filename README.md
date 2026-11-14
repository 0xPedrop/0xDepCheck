<p align="center">
  <img src="Banner.png" alt="0xDepCheck Banner" width="80%">
</p>

<h1 align="center">0xDepCheck 🏴‍☠️</h1>

<p align="center">
  Ferramenta de validação para <strong>Dependency Confusion</strong>.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/license-Apache%202.0-blue.svg" alt="License">
  <img src="https://img.shields.io/badge/registry-NPM-red.svg" alt="NPM">
  <img src="https://img.shields.io/badge/purpose-Bug%20Bounty-black.svg" alt="Bug Bounty">
</p>

---

O **0xDepCheck** consulta o registro público do NPM para confirmar se uma
dependência interna pode ser sequestrada, verificando tanto a disponibilidade
do pacote quanto a da organização (escopo).

## ✨ Funcionalidades

- **Validação automatizada** - checa se o pacote retorna `404` (livre) no registro oficial.
- **Verificação de org hijacking** - confirma se o escopo (`@org`) está disponível para registro.
- **Detecção de escopo** - diferencia pacotes globais de pacotes escopados automaticamente.
- **Pronto para bug bounty** - agiliza a prova de conceito (PoC) para relatórios de segurança.

## ⚙️ Instalação

Instale globalmente para usar durante o reconhecimento (recon):

```bash
chmod +x 0xDepCheck          # dá permissão de execução
sudo mv 0xDepCheck /usr/local/bin/   # move para o PATH
```

## 🚀 Uso

**Pacotes com escopo (org hijacking)** - verifica se o namespace da empresa pode ser sequestrado:

```bash
0xDepCheck @minhacorp/auth-lib
```

**Pacotes sem escopo (registro direto)** - para pacotes internos sem o prefixo `@`:

```bash
0xDepCheck lib-interna-secreta
```

**Modo interativo** - execute sem argumentos para digitar o nome manualmente:

```bash
0xDepCheck
```

## 🧠 Lógica de diagnóstico

| Resultado           | Significado                                                                              |
| ------------------- | ---------------------------------------------------------------------------------------- |
| `200`               | Pacote já existe publicamente - **seguro**.                                              |
| `404` (pacote)      | Potencialmente vulnerável a registro direto.                                             |
| `404` (organização) | **Crítico** - o namespace inteiro da empresa pode ser registrado para hospedar o pacote. |

## ⚠️ Aviso legal

Esta ferramenta destina-se exclusivamente a testes autorizados e pesquisa de
segurança dentro do escopo de programas de bug bounty ou com permissão explícita
do proprietário. O uso contra sistemas sem autorização é ilegal. O autor não se
responsabiliza por uso indevido.

## ⚖️ Licença

Licenciado sob a **Apache License 2.0** — veja o arquivo [LICENSE](LICENSE) para detalhes.

---

<p align="center">
  Desenvolvido por <strong>0xPedrop</strong> · <a href="https://github.com/0xPedrop">github.com/0xPedrop</a>
</p>
