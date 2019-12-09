# API em node-js-sqlite
Simples API em NodeJS Rest API com CRUD e conexão com SQlite.
Using SQLite database

## Como instalar
```sh
$ git clone https://github.com/macielsousadasilva/simple_api_on_node_js.git
$ cd simple_api_on_node_js
$ npm install 
$ npm run dev
```

O servidor estara rodando por padrão na porta 8050

------------

## Como usar

### POST
* **Adicionar produtos:**
```
http://localhost:8050/api/product
```
Corpo do JSON a ser enviado:
```javascript
{
	"name": "Nome do produto",
	"description": "Descrição do produto",
	"price": 2.00,
	"currency": "BRL" 
}
```
ou um array de produtos:
```javascript
[
	{...},{...}
]
```

---------------------------------------------

### PUT
* **Atualiza os produtos:**
```
http://localhost:8050/api/product
```
Corpo do JSON a ser enviado: **O ID é o único OBRIGATÓRIO**
```javascript
{
	"id": "1",
	"name": "Nome do produto",
	"description": "Descrição do produto",
	"price": 2.00,
	"currency": "BRL" 
}
```
ou um array de produtos:
```javascript
[
	{...},{...}
]
```

---------------------------------------------

### DELETE
* **Deletando um produto:**
```
http://localhost:8050/api/product
```
Corpo do JSON a ser enviado: **O ID é o único OBRIGATÓRIO**
```javascript
{
	"id": "1",
	"name": "Nome do Produto",
	"description": "Descrição do produto",
	"price": 2.00,
	"currency": "BRL" 
}
```
ou um array de produtos:
```javascript
[
	{...},{...}
]
```

---------------------------------------------

### GET
* **Buscando produtos por ID:**
```
http://localhost:8050/api/product/id/$id
```
Exemplo: http://localhost:8050/api/product/id/15
_____

* **Visualizar todos os produtos:**
```
http://localhost:8050/api/product/
```
______

* **Carregar produtos por qualquer atributo e valor:** 
```
http://localhost:8050/api/product/$attribute/$name
```
example: 
- http://localhost:8050/api/product/price/24
- http://localhost:8050/api/product/name/Suntone
$attribute = ['name', 'price', 'currency', 'description']
(Se esses valores não forem verificados, se ouver parâmetros errados retornarão um erro no banco de dados.)
_____

* **Carregar todos os produtos classificados por atributo** 
```
http://localhost:8050/api/product/sort/$attribute
```
Exemplo: 
- http://localhost:8050/api/product/sort/price
- http://localhost:8050/api/product/sort/name

$attribute = ['name', 'price', 'currency', 'description']
(Se os valores não forem verificados, ou ouver parâmetros errados retornarão um erro de banco de dados)
____

* **Carregar produtos classificando ASC ou DESC por qualquer atributo:**
```
http://localhost:8050/api/product/sort/$direction/$attribute
```
Exemplo: 
- http://localhost:8050/api/product/sort/asc/price
- http://localhost:8050/api/product/sort/desc/price

$attribute = ['name', 'price', 'currency', 'description']*
$direction [ASC or DESC]C]*
(a direção(ASC-DESC) é verificada e, quando errado, retornará um erro 401)
_____


## SQLite database
O banco de dados já está preenchido com 30 valores aleatórios de https://www.mockaroo.com/
