# Assistente-de-Delivery-com-AWS-Step-Functions-e-Amazon-Bedrock
🚀 Assistente de Delivery com AWS Step Functions e Amazon Bedrock

Este repositório contém um projeto prático para criar um Assistente de Delivery utilizando AWS Step Functions e Amazon Bedrock. O objetivo é orquestrar diferentes serviços AWS para automatizar e gerenciar o fluxo de pedidos de delivery, desde a recepção do pedido até a entrega final. O projeto visa melhorar a eficiência e a personalização da experiência do cliente.

🛠️ Tecnologias Utilizadas
AWS Step Functions: Para orquestrar o fluxo de trabalho do processo de delivery.
Amazon Bedrock: Para personalizar e otimizar a experiência do cliente com base em suas preferências e histórico.
AWS Lambda: Para execução de funções sem servidor, como validação de pedidos e integração com serviços de pagamento.
Amazon S3: Para armazenar dados relacionados aos pedidos e à entrega.
Amazon DynamoDB: Para armazenamento de dados estruturados sobre pedidos e status.
Amazon SNS: Para notificações sobre o status do pedido.
Amazon API Gateway: Para expor APIs que interagem com o assistente de delivery.

🗂️ Estrutura de Diretórios
aws-delivery-assistant/
│
├── .github/
│   └── workflows/   # Configurações para CI/CD e pipelines
│
├── src/             # Código-fonte do projeto
│   ├── lambdas/     # Funções Lambda
│   │   ├── validate_order.py
│   │   ├── process_payment.py
│   │   └── update_status.py
│   ├── step_functions/  # Definições do fluxo de trabalho do Step Functions
│   │   └── delivery_workflow.asl.json
│   └── bedrock/     # Integração com Amazon Bedrock
│       └── personalize_experience.py
│
├── terraform/       # Scripts de Terraform para infraestrutura como código
│   ├── main.tf
│   └── variables.tf
│
├── data/            # Dados de exemplo e arquivos de configuração
│   ├── example_orders.json
│   └── ...
│
├── docs/            # Documentação do projeto
│   └── setup.md
│
├── tests/           # Testes automatizados
│   ├── test_lambdas.py
│   └── test_step_functions.py
│
├── Dockerfile       # Dockerfile para desenvolvimento e containerização
├── requirements.txt # Dependências do projeto
└── README.md        # Documentação principal do projeto

📜 Descrição do Projeto
Funcionalidades
Recepção do Pedido: O fluxo inicia com a recepção do pedido via API Gateway, acionando a função Lambda que valida os dados do pedido.
Validação de Pedido: A função Lambda validate_order.py verifica a integridade e a validade dos dados do pedido.
Processamento de Pagamento: Após a validação, a função Lambda process_payment.py integra-se com serviços de pagamento para processar o pagamento do pedido.
Atualização de Status: A função Lambda update_status.py atualiza o status do pedido no DynamoDB e notifica o cliente via SNS.
Personalização da Experiência: Utilizando Amazon Bedrock, o projeto oferece recomendações personalizadas e ajustes na experiência de delivery com base em preferências do cliente.

Orquestração com Step Functions
O workflow do pedido é gerenciado pelo AWS Step Functions, definindo a sequência de tarefas e as transições entre elas. A definição do fluxo de trabalho está em src/step_functions/delivery_workflow.asl.json.

🚀 Instruções de Instalação
Clone o Repositório:
git clone https://github.com/seu-usuario/aws-delivery-assistant.git
cd aws-delivery-assistant

Configure o Ambiente:
Configure suas credenciais AWS.
Instale as dependências do projeto:
pip install -r requirements.txt

Implante a Infraestrutura:
Utilize Terraform para configurar a infraestrutura na AWS:
terraform init
terraform apply

Desenvolva e Teste:
Faça o desenvolvimento das funções Lambda e integre-as com o Step Functions e Amazon Bedrock.
Execute os testes automatizados:
pytest tests/

🧪 Testes
Execute os testes automatizados para garantir que todas as partes do projeto funcionem conforme esperado:
pytest tests/

📦 Docker
Para rodar o projeto em um container Docker, se necessário:
Build o Docker container:
docker build -t delivery-assistant .

Execute o container:
docker run -p 8501:8501 delivery-assistant

Agora, você pode acessar o aplicativo em http://localhost:8501.

📄 Licença
Este projeto é licenciado sob a MIT License.
