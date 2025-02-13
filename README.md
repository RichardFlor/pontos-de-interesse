<h2 align="center">
  Desafio Backend: Pontos de Interesse - Receptor GPS
</h2>


Resolução do desafio proposto pelo repositorio Backend Brasil, confira detalhes [neste link](https://github.com/backend-br/desafios/blob/master/points-of-interest/PROBLEM.md).


## Tecnologias
 
- [Spring Boot](https://spring.io/projects/spring-boot)
- [Spring Data JPA](https://spring.io/projects/spring-data-jpa)
- [H2 Database](https://www.baeldung.com/spring-boot-h2-database)


## Como Executar

- Clonar repositório git
- Construir o projeto:
```
$ ./mvnw clean package
```
- Executar a aplicação:
```
$ java -jar target/agregadorinvestimentos-0.0.1-SNAPSHOT.jar
```

A API poderá ser acessada em [localhost:8080](http://localhost:8080).


## API Endpoints


- Criar Pontos 
```
$ http POST :8080/points-of-interests
{
    "name": "Inicio",
    "x": 0,
    "y": 0
}
```

- Listar Pontos
```
$ http GET :8080/points-of-interests

{
    "content": [
        {
            "id": 1,
            "name": "Lanchonete",
            "x": 27,
            "y": 12
        },
        {
            "id": 2,
            "name": "Posto",
            "x": 31,
            "y": 18
        },
        {
            "id": 3,
            "name": "Joalheria",
            "x": 15,
            "y": 12
        },
        {
            "id": 4,
            "name": "Floricultura",
            "x": 19,
            "y": 21
        },
        {
            "id": 5,
            "name": "Pub",
            "x": 12,
            "y": 8
        },
        {
            "id": 6,
            "name": "Supermercado",
            "x": 23,
            "y": 6
        },
        {
            "id": 7,
            "name": "Churrascaria",
            "x": 28,
            "y": 2
        },
        {
            "id": 8,
            "name": "Inicio",
            "x": 0,
            "y": 0
        }
    ],
    "pageable": {
        "pageNumber": 0,
        "pageSize": 10,
        "sort": {
            "empty": true,
            "sorted": false,
            "unsorted": true
        },
        "offset": 0,
        "paged": true,
        "unpaged": false
    },
    "last": true,
    "totalPages": 1,
    "totalElements": 8,
    "size": 10,
    "number": 0,
    "sort": {
        "empty": true,
        "sorted": false,
        "unsorted": true
    },
    "numberOfElements": 8,
    "first": true,
    "empty": false
}
```

- Listar Pontos de Interesse proximos a mim
```
$ http GET :8080/near-me?x=20&y=10&dmax=10

 {
        "id": 1,
        "name": "Lanchonete",
        "x": 27,
        "y": 12
    },
    {
        "id": 3,
        "name": "Joalheria",
        "x": 15,
        "y": 12
    },
    {
        "id": 5,
        "name": "Pub",
        "x": 12,
        "y": 8
    },
    {
        "id": 6,
        "name": "Supermercado",
        "x": 23,
        "y": 6
    }
```
