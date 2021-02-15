# Laravel / Vue.js - RESTful API + Frontend

Aplicação desenvolvida em PHP com Laravel/MySQL/Vue.

# Especificações

  - Laravel: 8.0
  - PHP: 7.4
  - MySQL: 10.4.17
  - Vue: 2.5

# Configuração

  - Atualizar as dependências com o "composer";
  - Configurar o arquivo ".env" com os dados do database;
  - Fazer o apontamento da pasta "public/" da aplicação no servidor (ou);
  - Rodar o comando "php artisan serve" para startar o aplicação.

# Migrations e dummy datas

A aplicação conta com migrations para auxiliar na configuração do database e dummy datas para testes. 

Processando **migrations**:
```sh
$ php artisan migrate
```
Processando **dummy data**:
```sh
$ php artisan db:seed
```

# Requisições

Exemplos da entidade **Nota**:

**_GET (Todos)**

- **URL:** /api/notepads/
- **Retorno:**
```json
{
    "data": {
        "id": 1,
        "title": "Quia corrupti doloribus optio est nulla.",
        "description": "Consequatur numquam est tempore fuga maxime omnis repudiandae. Quas aut quod mollitia minus. Quod vitae cumque tempore ab. Quas quae voluptatem eveniet praesentium."
    }
}
```

**_GET (Único por ID)**

- **URL:** /api/notepads/{notepad_id}
- **Retorno:**
```json
{
    "data": {
        "id": 1,
        "title": "Ut nihil voluptate sit fugit.",
        "description": "Impedit modi quo necessitatibus. Iure repellat maiores at inventore hic ab blanditiis. Aut consequatur tenetur alias ea aliquid quos."
    }
}
```

**_POST**

- **URL:** /api/notepads/
- **Restrições:** [campos = requeridos]
- **Body:**
```json
{
	"title": "Nota de compra",
	"description": "Essa nota é show!"
}
```
- **Retorno:**
```json
{
    "id": 26,
    "title": "Nota de teste",
    "description": "Essa nota é show!"
}
```

**_PUT**

- **URL:** /api/notepads/{notepad_id}
- **Body:**
```json
{
	"description": "Alterando descrição da nota!"
}
```
- **Retorno:**
```json
{
    "id": 26,
    "title": "Nota de teste",
    "description": "Alterando descrição da nota!"
}
```

**_DELETE**

- **URL:** /api/notepads/{notepad_id}
- **Retorno:**
```json
204 No Content
```