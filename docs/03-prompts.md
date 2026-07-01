import streamlit as st
import os
from dotenv import load_dotenv
import google.generativeai as genai

# 1. Carrega as configurações do .env
load_dotenv(override=True)
api_key = os.getenv("GEMINI_API_KEY")#por motivos de Segurança esta chave esta protegida e nao aprece, mas esta ativa.

if not api_key:
    st.error("ERRO: A chave GEMINI_API_KEY não foi encontrada no ficheiro .env!")
    st.stop()

# 2. Configura a SDK do Google
genai.configure(api_key=api_key)

# 3. Lista de modelos atuais em ordem de preferência
MODELOS = [
    "gemini-2.5-flash",
    "gemini-2.5-flash-lite",
    "gemini-3.1-flash-lite",
]

model = None
for nome_modelo in MODELOS:
    try:
        model = genai.GenerativeModel(model_name=nome_modelo)
        modelo_usado = nome_modelo
        break
    except Exception:
        continue

if model is None:
    st.error("Nenhum modelo Gemini disponível encontrado. Verifique sua chave de API.")
    st.stop()

# 4. Interface Visual (Streamlit)
st.set_page_config(page_title="Guardião da Carteira", page_icon="🛡️")
st.title("🛡️ Guardião da Carteira")
st.subheader("Análise de Segurança Financeira com IA")
st.caption(f"Modelo em uso: `{modelo_usado}`")

user_input = st.text_area("Cole aqui a mensagem, e-mail ou link suspeito que recebeu:")

if st.button("Analisar Risco"):
    if user_input:
        with st.spinner("O Guardião está a analisar a mensagem contra fraudes..."):
            try:
                prompt = (
                    f"Você é um especialista em cibersegurança financeira. Analise a seguinte "
                    f"mensagem em busca de golpes, phishing ou engenharia social: {user_input}. "
                    f"Dê um veredito claro se é SEGURO ou SUSPEITO, explique os pontos de risco "
                    f"e dê dicas de proteção."
                )
                
                response = model.generate_content(prompt)
                
                st.write("---")
                st.success("Análise Concluída!")
                st.write(response.text)
                
            except Exception as e:
                st.error(f"Erro ao comunicar com a IA: {e}")
    else:
        st.warning("Por favor, cole alguma mensagem para eu poder analisar.")