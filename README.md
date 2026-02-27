# ftr-n8n

Desafio Fase 2 - Bot de Clima no Telegram com N8N

## 🎯 Objetivo do Projeto

Desenvolver um chatbot no Telegram utilizando N8N que informe a temperatura atual de qualquer cidade do Brasil. O chatbot recebe o nome da cidade e o estado via mensagem, consulta a API gratuita do OpenWeather, processa a resposta e devolve ao usuário uma mensagem curta, clara e amigável com a temperatura.

## ✅ Pré-requisitos

- **API OpenWeather:** Obtenha uma chave gratuita em [openweathermap.org](https://openweathermap.org/) e adicione-a na área de credenciais do N8N como **Query Auth**.
- **Bot no Telegram:** Crie um bot através do [@BotFather](https://t.me/BotFather) no Telegram e adicione o token gerado na área de credenciais do N8N como **Telegram account**.

## 📋 Regras de Negócio

### Formato de entrada

O usuário deve enviar a mensagem no seguinte formato:

```
Cidade,UF
```

**Exemplo:** `Santos,SP`

### Mensagem de sucesso

```
🌤️ A temperatura em Belo Horizonte é de 25°C.
```

### Mensagem de erro

```
❌ Cidade não encontrada. Use o formato Cidade,UF (ex.: São Paulo,SP).
```
