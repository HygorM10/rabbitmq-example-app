# Repositório de Estudo de Mensageria com RabbitMQ

Este repositório contém um projeto Java que consiste em três aplicações relacionadas a ordens, notificações e cashback.
O objetivo deste projeto é estudar a integração de sistemas por meio de mensageria utilizando o RabbitMQ.

## Aplicações

### API Rest (Order)

A aplicação API Rest é responsável por receber requisições relacionadas a ordens e produzir mensagens no RabbitMQ. Ela
utiliza o MySQL como banco de dados para armazenar informações relacionadas às ordens. Essa aplicação expõe endpoints
que permitem a criação, atualização, exclusão e consulta de ordens.

### Listener (Notification)

A aplicação Listener (Notification) é um consumidor de mensagens do RabbitMQ. Ela está configurada para escutar as
mensagens relacionadas às ordens e executar ações de notificação com base nas informações contidas nas mensagens
recebidas. Por exemplo, pode enviar e-mails ou mensagens de texto para notificar os usuários sobre o status das ordens.

### Listener (Cashback)

A aplicação Listener (Cashback) é outro consumidor de mensagens do RabbitMQ. Ela também escuta as mensagens relacionadas
às ordens, mas sua função é calcular o cashback a ser oferecido aos usuários com base nas informações das ordens. Essa
aplicação pode armazenar essas informações em um banco de dados ou realizar outras ações relacionadas ao cashback.

## Estrutura do Repositório

O repositório possui a seguinte estrutura:

```
├── api-rest-order/
│   ├── src/
│   ├── pom.xml
│   └── ...
├── listener-notification/
│   ├── src/
│   ├── pom.xml
│   └── ...
├── listener-cashback/
│   ├── src/
│   ├── pom.xml
│   └── ...
├── docker-compose.yml
├── postman_collection.json
└── README.md
```

- `api-rest-order/`: Contém o código fonte da API Rest responsável por receber as requisições relacionadas a ordens e
  produzir mensagens no RabbitMQ.
- `listener-notification/`: Contém o código fonte do listener responsável por receber as mensagens do RabbitMQ e
  executar ações de notificação.
- `listener-cashback/`: Contém o código fonte do listener responsável por receber as mensagens do RabbitMQ e calcular o
  cashback.
- `docker-compose.yml`: Arquivo de configuração do Docker Compose, que permite a execução de todos os componentes
  necessários para o projeto, incluindo o RabbitMQ, o MySQL e as aplicações.
- `postman_collection.json`: Collection do Postman contendo as requisições para testar a API Rest.
- `README.md`: Este arquivo.

## Configuração e Execução

Para executar o projeto, siga as etapas abaixo:

1. Certifique-se de ter o Docker e o Docker Compose instalados em sua máquina.
2. Clone este repositório em sua máquina local.
3. Navegue até o diretório raiz do repositório.
4. Execute o comando `docker-compose up -d` para iniciar o ambiente com o RabbitMQ e o MySQL.
5. Aguarde até que todos os serviços estejam em execução.
6. Acesse cada diretório de aplicação (`api-rest-order/`, `listener-notification/` e `listener-cash
   back/`) e execute o comando `mvn clean install` para compilar as aplicações.
7. Inicie cada aplicação Java por meio dos comandos `java -jar <nome_do_arquivo.jar>`.
8. As aplicações estarão em execução e prontas para processar as requisições, produzir mensagens e realizar ações com
   base nas mensagens recebidas.

## Contribuição

Sinta-se à vontade para contribuir com este projeto enviando pull requests. Se tiver alguma sugestão, dúvida ou
problema, abra uma issue para discutirmos.

## Licença

Este projeto está licenciado sob a [MIT License](https://opensource.org/licenses/MIT).