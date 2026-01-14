QRcode_pix
Projeto backend simples em Python + Flask para criação e exibição de pagamentos via Pix com QR Code, utilizando SQLite como banco de dados.
O foco do projeto é simular o fluxo de criação de um pagamento Pix e exibir uma página com o QR Code para pagamento.

Para que serve
Esse projeto serve para:
Estudar Flask e SQLAlchemy
Simular pagamentos via Pix
Criar endpoints REST
Renderizar páginas HTML com dados dinâmicos
Trabalhar com banco SQLite em projetos pequenos
Não há integração real com bancos ou APIs de pagamento. É um mock funcional para estudo.

Como funciona
O usuário faz um POST informando o valor do pagamento
O backend cria um pagamento no banco de dados
Um ID único é gerado automaticamente
O pagamento pode ser acessado por uma rota específica
Uma página HTML exibe o QR Code, valor e tempo de expiração

Como rodar o projeto

1️⃣ Clonar o repositório
git clone https://github.com/devromanin/QRcode_pix.git
cd QRcode_pix

2️⃣ Criar ambiente virtual
python -m venv venv

Ativar o ambiente virtual:

Windows:
venv\Scripts\activate

Linux / Mac:
source venv/bin/activate

3️⃣ Instalar dependências
pip install -r requirements.txt

4️⃣ Rodar a aplicação
python app.py

A aplicação ficará disponível em:
http://127.0.0.1:5000

📡 Endpoints disponíveis
🔹 Criar pagamento Pix
POST /payments/pix
Body JSON esperado:
{
"value": 150.50
}
Cria um novo pagamento e retorna os dados salvos no banco.

🔹 Visualizar pagamento Pix
GET /payments/pix/<payment_id>

Exemplo:
http://127.0.0.1:5000/payments/pix/1

Exibe uma página HTML com:
QR Code
Valor da compra
Tempo de expiração
Número do pedido

🔹 Webhook de confirmação (mock)
POST /payments/pix/confirmation
Atualmente retorna apenas uma mensagem fixa.
Serve como base para futuras integrações com sistemas externos.
