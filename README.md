## CRUD BÁSICO NO ELASTIC 

Demonstração da prática da implantação do CRUD básico no ambiente Elastic por meio do Kibana. Essa prática é uma demonstração básica dos comandos aplicados no Elastic.

--

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

![Imagem questão 2](https://github.com/gacarvalho/crud-basico-elastic/blob/main/images/exercicio_elastic_2.png?raw=true)
![Imagem questão 2](https://raw.githubusercontent.com/gacarvalho/crud-basico-elastic/main/images/exercicio_elastic_3.png)

📢  QUESTÃO 3: Alterar o valor do atributo qtd para 30 do documento com id 3

![Imagem questão 3](https://raw.githubusercontent.com/gacarvalho/crud-basico-elastic/main/images/exercicio_elastic_4.png)

📢  QUESTÃO 4: Buscar o documento com id 1

![Imagem questão 4](https://raw.githubusercontent.com/gacarvalho/crud-basico-elastic/main/images/exercicio_elastic_5.png)

📢  QUESTÃO 5: Deletar o documento com id 4

![Imagem questão 5](https://raw.githubusercontent.com/gacarvalho/crud-basico-elastic/main/images/exercicio_elastic_6.png)

📢  QUESTÃO 6: Contar quantos documentos tem o índice produto

![Imagem questão 6](https://raw.githubusercontent.com/gacarvalho/crud-basico-elastic/main/images/exercicio_elastic_7.png)
