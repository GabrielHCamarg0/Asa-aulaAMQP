Asa-aulaAMQP 

   
    Um projeto educacional 
    para explorar a comunicação assíncrona usando o protocolo AMQP (Advanced Message Queuing Protocol). 
     

Índice 

    Sobre o Projeto 
    Funcionalidades 
    Pré-requisitos 
    Instalação com Docker Compose 
    Uso 
    Estrutura do Projeto 
    Contribuição 
     

Sobre o Projeto 

Este projeto foi desenvolvido como parte de uma aula prática sobre o protocolo AMQP. Ele demonstra como configurar e usar filas de mensagens para comunicação entre diferentes componentes de software. O objetivo é fornecer uma base sólida para entender os conceitos de mensageria e integração de sistemas distribuídos. 

O projeto utiliza Docker Compose  para facilitar a configuração do ambiente, incluindo o servidor AMQP (ex.: RabbitMQ) e os scripts Python para envio e recepção de mensagens 

. 
Funcionalidades 

    Envio de Mensagens : Envie mensagens para uma fila AMQP.
    Recepção de Mensagens : Receba e processe mensagens de uma fila AMQP.
    Configuração Flexível : Personalize o servidor AMQP, nome da fila e outras configurações.
    Ambiente Dockerizado : Execute tudo em containers Docker para simplificar a configuração.
     

Pré-requisitos 

Antes de começar, certifique-se de ter os seguintes requisitos instalados: 

    Docker : Download Docker 
    Docker Compose : Já incluído no Docker Desktop ou disponível separadamente 

    .
     

Instalação com Docker Compose 

    Clone este repositório: 
    bash
     

 
1
2
git clone https://github.com/GabrielHCamarg0/Asa-aulaAMQP.git
cd Asa-aulaAMQP
 
 

Certifique-se de que o Docker e o Docker Compose estão instalados: 
bash
 
 
1
2
docker --version
docker-compose --version
 
 

Inicie o ambiente com Docker Compose: 
bash
 
 
1
docker-compose up --build
 
 

    Este comando criará e iniciará os containers necessários, incluindo o servidor AMQP (RabbitMQ) e os scripts Python para envio e recepção de mensagens 

    .
     

Para parar o ambiente, use: 
bash
 

     
    1
    docker-compose down
     
     
     

    Nota : Certifique-se de que nenhuma outra instância do servidor AMQP (ex.: RabbitMQ) esteja rodando na sua máquina para evitar conflitos de portas. 
     

Uso 
Enviar Mensagens 

Para enviar uma mensagem para a fila AMQP, o container responsável pelo script sender.py já estará configurado no Docker Compose. Basta iniciar o ambiente com docker-compose up e verificar os logs. 
Receber Mensagens 

Da mesma forma, o container responsável pelo script receiver.py estará ativo e pronto para processar mensagens da fila AMQP. 

    Logs : Você pode visualizar os logs dos containers em tempo real para acompanhar o envio e recebimento de mensagens: 
    bash
     

     
    1
    docker-compose logs -f
     
     
     

Estrutura do Projeto 
 
 
1
2
3
4
5
6
7
Asa-aulaAMQP/
├── docker-compose.yml       # Configuração do Docker Compose
├── sender.py                # Script para enviar mensagens para a fila AMQP
├── receiver.py              # Script para receber mensagens da fila AMQP
├── requirements.txt         # Dependências do projeto
├── Dockerfile               # Definição da imagem Docker
└── README.md                # Documentação do projeto
 
 
Contribuição 

Contribuições são bem-vindas! Se você deseja contribuir para este projeto, siga os passos abaixo: 

    Faça um fork do repositório.
    Crie uma branch para sua feature (git checkout -b feature/nome-da-feature).
    Faça commit das suas alterações (git commit -m 'Adiciona nova feature').
    Faça push para a branch (git push origin feature/nome-da-feature).
    Abra um Pull Request.
     
