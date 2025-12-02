📦 Ecommerce Microservices – .NET 9 + Docker + RabbitMQ + MongoDB

Este projeto é um exemplo funcional de arquitetura de microservices, utilizando .NET 9, comunicação assíncrona e containers Docker.
Ele representa a base de um sistema de e-commerce dividido em serviços independentes.

🏗 Arquitetura do Projeto

A solução é dividida nos seguintes serviços:

🔹 ApiGateway

Responsável por receber as requisições do cliente e rotear para os microserviços internos.

🔹 Inventory.Api

Gerencia produtos e estoque.

🔹 Sales.Api

Gerencia pedidos e integra com os outros serviços via RabbitMQ.

🔹 Shared

Biblioteca compartilhada contendo:

Models

DTOs

Mensagens de integração

Configurações comuns

🐳 Infraestrutura com Docker

O projeto utiliza os seguintes containers:

Serviço	Porta	Descrição
MongoDB	27017	Banco de dados NoSQL
RabbitMQ	5672 / 15672	Mensageria e painel visual
ApiGateway	8000	Roteador principal
Inventory.Api	8001	Serviço de estoque
Sales.Api	8002	Serviço de vendas
▶️ Como Executar o Projeto (Docker)
1️⃣ Requisitos

Docker Desktop

.NET 9 SDK (opcional se rodar pelo Docker)

2️⃣ Subir toda a aplicação

No diretório raiz ecommerce-microservices:

docker compose up -d --build

3️⃣ Ver serviços ativos
docker ps

4️⃣ Acessos Importantes
Recurso	URL
API Gateway	http://localhost:8000

Inventory API	http://localhost:8001

Sales API	http://localhost:8002

RabbitMQ Dashboard	http://localhost:15672
 (login: guest / guest)
🧪 Endpoints de Teste
Health Check
GET http://localhost:8000/health
GET http://localhost:8001/health
GET http://localhost:8002/health

📁 Estrutura de Pastas
ecommerce-microservices/
│── ApiGateway/
│── Inventory.Api/
│── Sales.Api/
│── Shared/
│── docker-compose.yml
└── EcommerceMicroservices.sln

🚀 Próximos Passos / Melhorias Futuras

Implementar autenticação (JWT)

Logging distribuído com Elastic Stack

Observabilidade com OpenTelemetry

Persistência para Sales.Api

Deploy em Kubernetes

🤝 Contribuição

Pull Requests são bem-vindos!
Fique à vontade para sugerir melhorias.

📜 Licença

Este projeto é livre para estudo e evolução.
