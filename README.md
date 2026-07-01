# 🛡️ Projeto Guardião da Carteira

> **Agente de IA Generativa Consultivo para Detecção de Phishing Bancário e Engenharia Social.**

Este projeto foi desenvolvido como desafio prático para o Bootcamp de IA Generativa da **DIO (Digital Innovation One)** em parceria com o **Bradesco**. O objetivo é simular um assistente financeiro proativo focado na segurança digital do cliente.

---

## 🚀 Funcionalidades Principais

* **Validação de URLs em Tempo Real:** Identifica se links compartilhados pertencem a domínios bancários oficiais ou se são páginas de fraude.
* **Análise de Engenharia Social:** Utiliza a API do Gemini para detectar técnicas de *typosquatting* (erros propositais em links).
* **Segurança de Dados:** Arquitetura local protegida contra vazamento de credenciais e chaves de API (`.env` blindado).

---

## 📂 Estrutura do Repositório

O projeto foi organizado seguindo rigorosamente as boas práticas de engenharia de software do mercado:

* 📁 `data/`: Contém a base histórica estruturada de links suspeitos (`fraude.json`).
* 📁 `docs/`: Documentação técnica completa do agente (Prompts, Métricas e Arquitetura).
* 📁 `src/`: Código-fonte da aplicação desenvolvido em Python.

---

## 📖 Documentação Detalhada e Pitch

Para entender o funcionamento conceitual do modelo e assistir à demonstração prática, acesse os artefatos oficiais na pasta de documentação:

1. [📄 Caso de Uso e Persona](./docs/01-documentacao-agente.md)
2. [📄 Base de Conhecimento](./docs/02-base-conhecimento.md)
3. [📄 Engenharia de Prompt](./docs/03-prompts.md)
4. [📄 Avaliação e Métricas de Erro](./docs/04-metricas.md)
5. [📺 **Demonstração em Vídeo/GIF (Pitch)**](./docs/05-pitch.md)

---
*Desenvolvido com foco em Cibersegurança, Inteligência Artificial e LGPD.*
