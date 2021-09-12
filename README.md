## OPERAÇÕES BÁSICAS NO ELASTIC 

Demonstração da prática da implantação do CRUD básico no ambiente Elastic por meio do Kibana. Essa prática é uma demonstração básica dos comandos aplicados no Elastic.

---

O Elasticsearch oferece por padrão uma API REST que recebe requisições HTTP: POST, PUT, DELETE e GET.

| OPERAÇÃO 	| DESCRIÇÃO                                                                      	|
|----------	|--------------------------------------------------------------------------------	|
| POST     	| Permite a indexação de um documento como um objeto JSON no corpo da requisição 	|
| PUT      	| Permite criar ou reindexar um documento inteiro                                	|
| DELETE   	| Permite deletar um documento ou um índice                                      	|
| GET      	| Retorna um JSON com todos os documentos do índice                              	|



📢  QUESTÃO 1: Criar o índice produto e inserir os seguintes documentos:

- [x] _id: 1, "nome": "mouse", "qtd": 50, "descricao": "com fio USB, compatível com Windows, Mac e Linux"
- [x] _id: 2, "nome": "hd", "qtd": 20, "descricao": "Interface USB 2.0, 500GB, Sistema: Windows 10, Windows 8, Windows 7 "
- [x] _id: 3, "nome": "memória ram", "qtd": 10, "descricao": "8GB, DDR4"
- [x] _id: 4, "nome": "cpu", "qtd": 15, "descricao": "i5, 2.5Ghz"

```
POST produto/_doc/4
{
  "nome": "cpu", 
  "qtd": 15, 
  "descricao": "i5, 2.5Ghz"
}

POST produto/_doc/3
{
  "nome": "memória ram", 
  "qtd": 10, 
  "descricao": "8GB, DDR4"
}

POST produto/_doc/2
{
  "nome": "hd", 
  "qtd": 20, 
  "descricao": "Interface USB 2.0, 500GB, Sistema: Windows 10, Windows 8, Windows 7 "
}

POST produto/_doc/1
{
  "nome": "mouse", 
  "qtd": 50, 
  "descricao": "com fio USB, compatível com Windows, Mac e Linux"
}

```

📢  QUESTÃO 2: Verificar se existe o documento com  id 3
 
 Para verificarmos se existe o documento com o _id:3, vamos consultar com o comando ``` HEAD produto/_doc/3 ```, e como é possível observarmos, tivemos um retorno positivo.
 
![Imagem questão 2](https://github.com/gacarvalho/crud-basico-elastic/blob/main/images/exercicio_elastic_2.png?raw=true)

Agora, vamos consultar um documento que não foi criado.

![Imagem questão 2](https://raw.githubusercontent.com/gacarvalho/crud-basico-elastic/main/images/exercicio_elastic_3.png)

📢  QUESTÃO 3: Alterar o valor do atributo qtd para 30 do documento com id 3

Quando criamos o documento _id:3, as informações que passamos foi:

```
POST produto/_doc/3
{
  "nome": "memória ram", 
  "qtd": 10, 
  "descricao": "8GB, DDR4"
}
```
E a questão está pedindo para atualizarmos o ```"qtd":10``` para ```"qtd":30```:

```
POST produto/_update/3
{
  "doc": {
    "qtd":30
  }
}
```

![Imagem questão 3](https://raw.githubusercontent.com/gacarvalho/crud-basico-elastic/main/images/exercicio_elastic_4.png)

📢  QUESTÃO 4: Buscar o documento com id 3

Agora vamos buscar o documento com o _id: 3

```
GET produto/_doc/3
```

E tivemos o retorno:

```
{
  "_index" : "produto",
  "_type" : "_doc",
  "_id" : "3",
  "_version" : 4,
  "_seq_no" : 12,
  "_primary_term" : 2,
  "found" : true,
  "_source" : {
    "nome" : "memória ram",
    "qtd" : 30,
    "descricao" : "8GB, DDR4"
  }
}
```

![Imagem questão 4](https://raw.githubusercontent.com/gacarvalho/crud-basico-elastic/main/images/exercicio_elastic_5.png)

📢  QUESTÃO 5: Deletar o documento com id 4

Agora na questão 5, vamos deletar o documento _id: 4

```
DELETE produto/_doc/4
```

![Imagem questão 5](https://raw.githubusercontent.com/gacarvalho/crud-basico-elastic/main/images/exercicio_elastic_6.png)

📢  QUESTÃO 6: Contar quantos documentos tem o índice produto

Para finalizarmos o primeiro passo, vamos contar o número de registros 
```
GET produto/_count
```

![Imagem questão 6](https://raw.githubusercontent.com/gacarvalho/crud-basico-elastic/main/images/exercicio_elastic_7.png)
