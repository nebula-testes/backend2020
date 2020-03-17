# Teste Backend Dev (estágio)

## Descrição
Bem-vindo ao processo seletivo da Nébula Sistemas. Primeiramente, desejamos boa sorte e esperamos que você se divirta programando o que for proposto. Estamos ansiosos para te conhecer!

A Nébula Sistemas é uma software house localizada em Betim – MG, que atende o ramo de food service há 9 anos, entregando software como serviço (SaaS), promovendo a transformação tecnológica em bares, restaurantes, cantinas escolares e até mesmo eventos.

O teste a seguir servirá para avaliar sua capacidade básica de codificar uma solução simples e objetiva, utilizando as tecnologias que são usadas diariamente pela equipe de desenvolvimento. Sem mais delongas... bora codar!

## Aplicação

O objetivo é reproduir um cenário muito parecido com o que é vivido no cotidiano da Nébula. Nesse repo, existe uma API já pronta com alguns endpoints implementados e funcionando, bem como endpoints defeituosos.

Seu papel será identificar os endpoints defeituosos e consertá-los, além de criar novos de acordo com a tabela no fim dessa seção:

### Contexto
Você foi contratado pela Offline Disco, uma empresa de discos de vinil raros, para poder criar o backend de uma aplicação web que disponibilizará os recursos necessários para construção do frontend.

O banco de dados já foi modelado pelo DBA e agora cabe à você dar vida à aplicação através das regras de negócio.

O grande problema, porém, foi essa empresa já ter contratado um programador que, por irresponsabilidade, enrolou com prazos e não entregou todas suas tarefas prontas, algumas faltam implementar, outras foram implementadas e algumas estão implementadas, mas incorretamente.

### Endpoints

Os endpoints abaixo devem ser seguir o padrão RESTful.

| Verbo HTTP    | Descrição     | Resultado esperado  |
| :------------ |:-------------| :-----|
| [GET]         | Obter uma lista de todos os discos |  Status 200|
| [GET]         | Obter uma lista com todos os discos de rock dos anos 80|   Status 200    |
| [POST]        | Criar um novo disco              | Status 201      |
| [PUT]         | Alterar informações de um artista já cadastrado               | Status 200 |
| [DELETE]       | Excluir uma faixa de um disco               | Status 200 |

---

Todos os retornos devem ser um json com a seguinte estrutura:

``` json
 {
     "Code": "<codigo-do-erro>",
     "Message": "<mensagem-sucesso|mensagem-de-erro>",
     "Data": [{}]
 }
```

### Modelos de cada endpoint

#### Obter a lista de todos os discos
``` json
[GET] > /api/albums

response:
status-code: 200
{
    "Code": "get-resource",
    "Message": "Resource fetched successfully",
    "Data": [   
        {
            "Id": "",
            "Name": "",
            "Year": 0,
            "Style": "",
            "# of Songs": 0,
            "Artist": {
                "Id": 0,
                "Name":"",
                "Country": "",
                "BirthDate": ""
            }
        }
    ]
}
```

#### Obter uma lista com todos os discos de rock dos anos 80
``` json
[GET] > /api/albums/rock/80

response:
status-code: 200
{
    "Code": "get-resource",
    "Message": "Resource fetched successfully",
    "Data": [
        {
            "Id": "",
            "Name": "",
            "Year": 0,
            "Style": "",
            "# of Songs": 0,
            "Artist": {
                "Id": 0,
                "Name":"",
                "Country": "",
                "BirthDate": ""
            }
        }
    ]
}
```

#### Criar um novo disco
``` json
[POST] > /api/albums

body:
{
    "Id": "",
    "Name": "",
    "Year": 0,
    "Style": "",
    "# of Songs": 0,
    "ArtistId": 0
}

response: 
status-code: 201
{
    "Code": "create-resource",
    "Message": "Resource created successfully",
    "Data": [
        {
            "Id": "",
            "Name": "",
            "Year": 0,
            "Style": "",
            "# of Songs": 0,
            "Artist": {
                "Id": 0,
                "Name":"",
                "Country": "",
                "BirthDate": ""
            }
        }
    ]
}
```

#### Alterar informações de um artista já cadastrado
``` json
[PUT] > /api/artist/{id}

body:
{
    "Id": 0,
    "Name":"",
    "Country": "",
    "BirthDate": ""
}

status-code: 200
{
    "Code": "update-resource",
    "Message": "Resource updated successfully",
    "Data": [
        {
            "Id": 0,
            "Name":"",
            "Country": "",
            "BirthDate": ""
        }
    ]
}
```

#### Excluir uma faixa de um disco
``` json
[DELETE] > /api/albums/song/{id}

status-code: 200
response: {
    "Code": "delete-resource",
    "Message": "Resource deleted successfully",
    "Data": {}
}
```

### Arquitetura

A API foi elaborada com base na arquitetura MVC(Model, View, Controller), utilizando Entity Framework Core como ORM, implementando também o padrão de repositórios.

> Parece muita coisa? Keep calm =] 

Não serão cobrados conhecimentos aprofundados sobre arquitetura e como tudo funciona por debaixo dos panos. Nesse primeiro contato, basta fazer funcionar. 

Boas práticas como: seguir um style guide para C# e Clean Code serão vistas com ótimos olhos.

## Deploy

Para entregar seu código, basta fazer um fork desse repo, criar uma branch com seu nome completo e realizar um pull request. 

Será feita uma análise da aplicação e o resultado será enviado para o e-mail que iniciou o contato, ou seja, o email que enviou o currículo.