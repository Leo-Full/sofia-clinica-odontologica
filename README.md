# 🦷 Sofia — Atendente Virtual para Clínica Odontológica

![n8n](https://img.shields.io/badge/n8n-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)
![JSON](https://img.shields.io/badge/JSON-000000?style=for-the-badge&logo=json&logoColor=white)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white)
![Google Calendar](https://img.shields.io/badge/Google%20Calendar-4285F4?style=for-the-badge&logo=googlecalendar&logoColor=white)
![WhatsApp](https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white)

## Sobre o projeto

Automação construída em **n8n** que atua como recepcionista virtual de uma clínica odontológica, atendendo pacientes diretamente pelo WhatsApp. O agente ("Sofia") entende a mensagem do paciente, consulta a agenda em tempo real e conduz todo o fluxo de agendamento sem intervenção humana.

## O que o fluxo faz

- 📩 Recebe mensagens de texto e áudio via webhook (WhatsApp), com transcrição automática de áudios
- 🤖 Usa um agente de IA (OpenAI) com prompt estruturado para conduzir a conversa de forma natural
- 🩹 Identifica relatos de dor/urgência e prioriza o atendimento
- 📅 Consulta a Google Agenda em tempo real antes de oferecer horários
- ✅ Confirma o agendamento com o paciente antes de criar o evento
- 📝 Registra os dados do paciente automaticamente
- 🔄 Lida com cancelamentos e remarcações
- 🧠 Mantém memória de contexto por conversa (janela de histórico por paciente)

## Como está estruturado

Webhook (recebe mensagem) → Code (processa texto/áudio) → AI Agent (decide a resposta) → Ferramentas (consultar agenda / criar agendamento / registrar paciente / cancelar) → HTTP Request (envia resposta pelo WhatsApp) 

## Tecnologias e integrações

- **n8n** — orquestração do fluxo
- **OpenAI (GPT)** — modelo de linguagem do agente
- **Google Calendar API** — consulta e criação de eventos
- **uazapi** — gateway de envio/recebimento de mensagens no WhatsApp

## Como importar

1. Baixe o arquivo `.json` deste repositório
2. No n8n, vá em **Import from File** e selecione o arquivo
3. Configure suas próprias credenciais de OpenAI e Google Calendar (via sistema de credenciais do n8n)
4. Substitua os placeholders `YOUR_OPENAI_API_KEY_HERE` e `YOUR_UAZAPI_TOKEN_HERE` pelos seus próprios valores
5. Ative o webhook e conecte sua instância de WhatsApp

> ⚠️ Este JSON foi sanitizado para portfólio: todas as credenciais reais foram substituídas por placeholders.
