# 🚀 Pitch: Projeto Guardião da Carteira

> **Agente de IA Generativa para Detecção de Phishing e Fraudes Bancárias em Tempo Real.**

---

## 🎯 O Problema
O setor financeiro sofre diariamente com ataques de engenharia social. Links falsos (*phishing*) que imitam perfeitamente bancos reais enganam milhares de usuários, resultando em fraudes financeiras massivas. Identificar esses links antes que o usuário insira suas credenciais é um dos maiores desafios de cibersegurança atuais.

## 💡 A Solução
O **Guardião da Carteira** é um agente inteligente proativo alimentado pela API do Gemini. Ele não é um simples bloqueador de links: ele atua como um analista de segurança consultivo. 
O agente analisa a estrutura da URL em tempo real, cruza com nossa base de dados (`data/fraude.json`) e avalia padrões de *typosquatting* (erros de digitação propositais em domínios), alertando o usuário instantaneamente de forma didática e preventiva.

## ✨ O Diferencial Inovador
* **Anti-Alucinação Estrito:** O modelo foi blindado via Engenharia de Prompt para não inventar ameaças, garantindo 0% de falsos positivos em bancos reais nos testes homologados.
* **Privacidade por Design:** O agente analisa a URL localmente e remove parâmetros sensíveis antes de qualquer processamento externo, respeitando a LGPD.
* **Interface Fluida:** Prototipado em Streamlit para uma experiência de usuário simples e direta.

---

## 📺 Demonstração em Ação

![Demonstração do Guardião da Carteira]((teste_guardiao).gif)

---
*Projeto desenvolvido para o Bootcamp de IA Generativa da DIO em parceria com o Bradesco.*