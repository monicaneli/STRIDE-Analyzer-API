# STRIDE Analyzer API

> API para análise automática de ameaças em arquiteturas de sistemas, utilizando Python, FastAPI, Azure OpenAI (GPT-4) e visualização com Cytoscape.js no frontend.

---

## Visão Geral
Esta API recebe uma imagem de arquitetura de sistema e dados do contexto da aplicação, aplica técnicas de prompt engineering e utiliza o modelo GPT-4 da Azure OpenAI para identificar ameaças de segurança segundo a metodologia STRIDE. O resultado é apresentado em formato estruturado e visualizado no frontend.

---

## Dependências do Projeto

### Backend (API)
- Python 3.11+
- fastapi
- uvicorn
- python-dotenv
- openai (AzureOpenAI)

### Frontend
- HTML5, CSS3, JavaScript
- [Cytoscape.js](https://js.cytoscape.org/) (CDN)

---

## Instalação e Configuração

### 1. Clone o repositório
```bash
git clone <url-do-repositorio>
cd STRIDE-Analyzer-API
```

### 2. Crie e ative o ambiente virtual (opcional)
```bash
python -m venv AV
# Ative no Windows:
.\ AV\Scripts\Activate.ps1
# Ou no Linux/Mac:
source  AV/bin/activate
```

### 3. Instale as dependências
```bash
pip install fastapi uvicorn python-dotenv openai
```

### 4. Configure o arquivo `.env`
Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis (obtenha os valores no portal Azure, conforme instruções abaixo):

```
AZURE_OPENAI_API_KEY=chave_da_api
AZURE_OPENAI_ENDPOINT=https://<seu-endpoint>.openai.azure.com/
AZURE_OPENAI_API_VERSION=2023-12-01-preview
AZURE_OPENAI_DEPLOYMENT_NAME=<nome_da_deployment>
```

#### Como obter as credenciais:
1. Acesse o [Portal Azure](https://portal.azure.com/).
2. Crie ou acesse um recurso "Azure OpenAI".
3. Implemente um modelo GPT-4 com suporte a imagens.
4. No "Playground de chat", clique em "Exibir código" para copiar as credenciais.

---

## Como Executar o Projeto

### 1. Inicie a API (Backend)
No terminal, execute:
```bash
python -m uvicorn main:app --reload
```
Ou, se estiver usando o ambiente virtual:
```bash
.\ AV\Scripts\python.exe -m uvicorn main:app --reload
```
A API estará disponível em: http://127.0.0.1:8000

### 2. Execute o Frontend
Abra o arquivo `frontend/index.html` no navegador.

**Dica:** Para melhor experiência, utilize a extensão "Live Server" no VS Code. Clique com o botão direito no arquivo `index.html` e selecione "Open with Live Server" ou "Show Preview".

---

## Como Usar
1. Faça upload de uma imagem da arquitetura do sistema (PNG ou JPG).
2. Preencha os campos do formulário com os detalhes da aplicação.
3. Clique em "Analisar Ameaças".
4. O resultado será exibido em formato JSON e visualizado como grafo.

---

## Estrutura do Projeto

```
STRIDE-Analyzer-API/
│   main.py
│   .env.example
│   README.md
│
├───frontend/
│       index.html
```

---

## Observações
- Certifique-se de que as credenciais Azure OpenAI estejam corretas.
- O modelo precisa ser compatível com entrada de imagem.
- Para dúvidas, consulte a documentação oficial do [FastAPI](https://fastapi.tiangolo.com/) e [Azure OpenAI](https://learn.microsoft.com/pt-br/azure/ai-services/openai/).

## Exemplos de Interface e Arquitetura

<div align="center">
	<img src="https://github.com/monicaneli/STRIDE-Analyzer-API/blob/55b6d1baa2fb85590b036a722f660ce0eec8a2cd/interface/Formulario.JPG" alt="Interface 1" width="45%" style="display:inline-block; margin-right:10px;"/>
	<img src="https://github.com/monicaneli/STRIDE-Analyzer-API/blob/55b6d1baa2fb85590b036a722f660ce0eec8a2cd/interface/Resposta.JPG" alt="Interface 2" width="45%" style="display:inline-block;"/>
</div>

<p align="center"><i>Exemplo da interface web da aplicação</i></p>

---

### Exemplo de Arquitetura

<div align="center">
	<img src="https://github.com/monicaneli/STRIDE-Analyzer-API/blob/55b6d1baa2fb85590b036a722f660ce0eec8a2cd/imagens/arquitetura1.JPG" alt="Exemplo de Arquitetura" width="60%"/>
</div>

<p align="center"><i>Exemplo de uma imagem de arquitetura utilizada na análise</i></p>

---

## Licença
MIT
