# QRcode_pix

API backend em **Python + Flask** que simula **pagamentos via Pix com QR Code**, utilizando **SQLite** e **SQLAlchemy**.

Projeto focado em backend: criação de pagamentos, persistência em banco e renderização de página HTML com dados dinâmicos.

---

## O que esse projeto faz

- Cria pagamentos Pix via API
- Salva os dados no banco SQLite
- Gera um ID único para cada pagamento
- Exibe uma página HTML com QR Code, valor e tempo de expiração
- Simula um webhook de confirmação

Não há integração real com bancos ou APIs financeiras. É um projeto educacional e de portfólio.

---

## Como funciona

1. O cliente envia uma requisição POST com o valor do pagamento
2. O backend valida os dados recebidos
3. O pagamento é salvo no banco de dados
4. Um ID único é gerado automaticamente
5. O pagamento pode ser acessado por uma rota específica
6. Uma página HTML exibe o QR Code e as informações do Pix

---

## Como rodar o projeto

1. Clone o repositório

   git clone https://github.com/devromanin/QRcode_pix.git
   cd QRcode_pix

2. Crie um ambiente virtual

   python -m venv venv

   Ative o ambiente:

   Windows:
   venv\Scripts\activate

   Linux / Mac:
   source venv/bin/activate

3. Instale as dependências

   pip install -r requirements.txt

4. Execute a aplicação

   python app.py

A aplicação ficará disponível em:
http://127.0.0.1:5000

---

## Endpoints

Criar pagamento Pix  
POST /payments/pix

Corpo da requisição (JSON):
{
  "value": 150.50
}

---

Visualizar pagamento Pix  
GET /payments/pix/<payment_id>

Exibe a página HTML com:
- QR Code
- Valor da compra
- Tempo de expiração
- Número do pedido

---

Webhook de confirmação (mock)  
POST /payments/pix/confirmation

Endpoint placeholder para futuras integrações.

---

## Banco de dados

- Banco: SQLite
- Arquivo: database.db
- ORM: SQLAlchemy
