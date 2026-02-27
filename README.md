# ftr-n8n

Desafio Fase 2 - Bot de Clima no Telegram com N8N

## 🎯 Objetivo do Projeto

Desenvolver um chatbot no Telegram utilizando N8N que informe a temperatura atual de qualquer cidade do Brasil. O chatbot recebe o nome da cidade e o estado via mensagem, consulta a API gratuita do OpenWeather, processa a resposta e devolve ao usuário uma mensagem curta, clara e amigável com a temperatura.

## ✅ Pré-requisitos

- **API OpenWeather:** Obtenha uma chave gratuita em [openweathermap.org](https://openweathermap.org/) e adicione-a na área de credenciais do N8N como **Query Auth**.
- **Bot no Telegram:** Crie um bot através do [@BotFather](https://t.me/BotFather) no Telegram e adicione o token gerado na área de credenciais do N8N como **Telegram account**.

## 📥 Importar o workflow dentro do n8n

Siga os passos abaixo para importar o workflow na sua instância do n8n:

1. Acesse o painel do **n8n** pelo navegador.
2. No menu lateral esquerdo, clique em **Workflows**.
3. Clique no botão **Import** (canto superior direito).
4. Selecione a opção **Import from File**.
5. Escolha o arquivo `.json` do workflow que você baixou.
6. Clique em **Import** para concluir.
7. Ativar o workflow clicando em **Activate** (canto superior direito).


## 🔑 Configuração de Credenciais no n8n

Para que o bot funcione, você deve configurar as duas credenciais exibidas na aba de **Credentials** do seu projeto:

</br>

1️⃣ Telegram API

Utilizada para permitir que o n8n receba e envie mensagens através do seu bot.

1. No painel lateral esquerdo do n8n, clique em **Credentials**.  
2. Clique no botão **Add Credential** (canto superior direito).  
3. Pesquise por **Telegram API** e selecione-a.  
4. No campo **Access Token**, cole o token gerado pelo **@BotFather** no Telegram.  
5. Clique em **Save** para finalizar.  

</br>

2️⃣ OpenWeather (Query Auth)

Como a OpenWeather exige a chave de API diretamente na URL (*query parameters*), utilizamos o tipo **Query Auth**.

1. Clique em **Add Credential** novamente.  
2. Pesquise por **HTTP Header Auth** e, dentro das opções, selecione **Query Auth**.  
3. Configure os campos da seguinte maneira:

   - **Name:** Digite exatamente `appid` (este é o nome do parâmetro que a API espera).  
   - **Value:** Cole a sua API Key gerada no site da OpenWeather.  
4. Dê um nome amigável à credencial, como `OPENWEATHER_API_KEY`, e clique em **Save**.

</br>

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
