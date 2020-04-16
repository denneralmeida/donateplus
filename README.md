
API - Aplicação DOE Mais - Microservices

Exemplo de uma aplicação em Spring Boot e Eureka utilizando microserviços

## Construído com:

- [Spring Boot](https://spring.io/projects/spring-boot) - Responsável por criar o microserviço e realizar o seu processamento e persistência.
- [Maven](https://maven.apache.org/) - Ferramenta de build automático.
- [Junit](https://junit.org/junit5/) - Ferramenta utilizar para criação dos testes unitários
- [Mockito](https://site.mockito.org/) - Ferramenta utilizada para realizar mock de objetos referente a limitação de ambiente(dev,teste e produção).
- [Docker](https://www.docker.com/) - Ferramenta utilizada para simular o ambiente de testes de forma íntegra.
- [Insominia](https://insomnia.rest/) - Ferramenta utilizada para realizar testes de chamadas via rest.
- [Swagger](https://swagger.io/) - Ferramenta utilizada para documentação da API construída neste projeto.
- [Jenkins](https://jenkins.io/) - Ferramenta responsável pela execução da automatização de testes e integração contínua.
- [Eureka](https://jenkins.io/) - Service Discovery

## Arquitetura

- Montei o fluxograma abaixo para representar de maneira ilustrativa como foi aplicado cada tecnologia e como se relacionam.

<img src="img/archtecture.png">

## Service Discovery

- Responsável por facilitar a comunicação entre 1 ou mais microserviços. Os microserviços se registram no Eureka e passam a ser chamado pelos demais através de sua alias.
Este ponto ajuda bastante quando temos vários microserviços na solução e bem como mais de uma instância.

- No exemplo abaixo é possível identificar dois serviços registrados no Eureka. o donateplusapi e o payment, dado a explicação acima podemos imaginar um cenário onde tivéssemo
uma alto volume de requisições de pagamento por um período sazonal. Com a arquitetura proposta é possível duplicar o serviços de payment e registrar no Eukera realizando o
balance do volume de requisições.

<img src="img/eureka.png">

## Monitoramento

- Atualmente a ferramanta mais utilizada por grande empresas para monitoramento de microserviços é o Splunk. Neste caso aqui fiz a utilização de um projeto chamado 
Spring Admin. A sua configuração é bem simples e sua interface é bastante amigável.

- Visualização de Dashboard 

<img src="img/spring_admin.png">

- Detalhes de consumo e uso de memória

<img src="img/spring_admin2.png">

## Solução