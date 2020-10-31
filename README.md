
# MongoDB | Compass CRUD

#Materiais e exercicios

## Introdução

Estamos de volta com nossas queries! :wink:

Aprendemos alguns operadores de consulta superúteis, que nos ajudam a fazer consultas muito melhores para recuperar os dados de que precisamos. Continuaremos usando o banco de dados **Crunchbase**.


## Requisitos

- Fork este repositório
- Clone este repositório


## Entregáveis

Uma vez que iremos consultar nosso banco de dados do Mongo Compass, você precisará copiar/colar o `query`,` projection`, `sort`,` skip` e `limit` que você inseriu no Mongo Compass. No arquivo `queries.md`, você encontrará as instruções sobre as consultas que você precisa fazer, e um campo para preencher as respostas.

### Exemplo

1. Este é um exemplo
  - ** `query` **: /*Você deve copiar/colar a consulta aqui*/
  - ** `projeção` **: /*Você deve copiar/colar a projeção aqui*/
  - ** `sort` **: /*Você deve copiar/colar a classificação aqui*/
  - ** `skip` **: /*Você deve copiar/colar o salto aqui*/
  - ** `limit` **: /*Você deve copiar/colar o limite aqui*/

## Instruções

### Iteração 1

Primeiro, precisamos importar o banco de dados que usaremos para o `lab`. Usaremos o banco de dados Crunchbase. Crunchbase é o principal destino para descobrir tendências do setor, investimentos e notícias sobre centenas de milhares de empresas em todo o mundo. De startups a Fortune 500s, a Crunchbase é reconhecida como a principal fonte de inteligência empresarial por milhões de usuários em todo o mundo.

O banco de dados contém mais de 18 mil documentos, sendo que cada um deles contém muitas informações sobre cada uma das empresas. Um documento se parece com o seguinte:

![image](https://user-images.githubusercontent.com/23629340/36494916-d6db1770-1733-11e8-903e-5119b3c1b688.png)

1. Você encontrará o arquivo `.zip` do Banco de Dados na pasta ** lab **.
2. Descompacte o arquivo
3. No terminal, importe o banco de dados para o Mongo usando o seguinte comando:
```bash
$ mongoimport --db companies --collection companies --file companies.json
```
4. Verifique no Mongo Compass se está tudo bem:

:::info >
Ao executar o `mongoimport`, você deve estar localizado na mesma pasta que o arquivo` companies.json`.
:::

![image](https://user-images.githubusercontent.com/23629340/36534191-1f1bc5ec-17c6-11e8-9463-4945679b98c0.png)


### Iteração 2

Você já sabe como funciona, então vamos começar a trabalhar:

1. Todas as empresas cujo nome corresponde a 'Babelgum'. Recupere apenas o campo `name`.
2. Todas as empresas com mais de 5.000 funcionários. Limite a pesquisa a 20 empresas e classifique-as por `number of employees`.
3. Todas as empresas fundadas entre 2000 e 2005, ambos os anos incluídos. Recupere apenas os campos `name` e` founded_year`.
4. Todas as empresas que tiveram um Valor de Avaliação superior a 100.000.000 e foram fundadas antes de 2010. Recupere apenas os campos `name` e `ipo`.
5. Todas as empresas que tenham menos de 1000 funcionários e tenham sido fundadas antes de 2005. Ordene-as pelo número de funcionários e limite a pesquisa a 10 empresas.
6. Todas as empresas que não incluem o campo `partners`.
7. Todas as empresas que possuem um tipo nulo de valor no campo `category_code`.
8. Todas as empresas que têm pelo menos 100 funcionários, mas menos de 1000. Recupere apenas os campos `name` e `number of employees`.
9. Ordene todas as empresas pelo preço de `ipo` de forma descendente.
10. Recupere as 10 empresas com mais funcionários, ordenado pelo `number of employees`
11. Todas as empresas constituídas no segundo semestre do ano. Limite sua pesquisa a 1000 empresas.
12. Todas as empresas fundadas antes de 2000 que tenham um valor de aquisição superior a 10.000.000
13. Todas as empresas adquiridas após 2015, ordenam pelo valor de aquisição e recuperam apenas os campos `name` e `acquisition`.
14. Ordene as empresas por seu `founded year`, recuperando apenas seu` name` e `founded year`.
15. Todas as empresas constituídas nos primeiros sete dias do mês, incluindo o sétimo. Classifique-os por seu `acquisition price` de forma descendente. Limite a pesquisa a 10 documentos.
16. Todas as empresas da «web» `category` com mais de 4000 empregados. Classifique-os pela quantidade de funcionários em ordem crescente.
17. Todas as empresas cujo valor de aquisição seja superior a 10.000.000 e a moeda seja 'EUR'.
18. Todas as empresas adquiridas no primeiro trimestre do ano. Limite a pesquisa a 10 empresas e recupere apenas os campos `name` e `acquisition`.
19. Todas as empresas que foram fundadas entre 2000 e 2010, mas não foram adquiridas antes de 2011.

Happy Coding! :heart:
