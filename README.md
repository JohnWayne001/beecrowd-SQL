# Beecrowd SQL
[Clique aqui para abrir o Notion com a resolução das atividades](https://second-mole-a02.notion.site/Atividade-SQL-BeeCrowd-2567d0b5a75280ee857ffd2e1c5d558e?source=copy_link)
## 📖 Sobre
Este repositório contém minhas soluções para problemas de SQL do Beecrowd. Os exercícios abrangem desde consultas básicas até problemas avançados de banco de dados. Essa atividade foi feita para aprimorar os conhecimentos em SQL através de exercícios no site Beecrowd.
## Atividade Nível 01
### Atividade 2603
Problema: A empresa fará um evento comemorando os 20 anos de mercado, e para isso faremos uma grande comemoração na cidade de Porto Alegre. Queremos também convidar todos os nossos clientes que estão cadastrados nessa cidade.

O seu trabalho é nos passar os nomes e os endereços dos clientes que moram em 'Porto Alegre', para entregar os convites pessoalmente.

<img width="515" height="708" alt="Image" src="https://github.com/user-attachments/assets/dff70f6e-8876-49e8-8bed-a29ae189ed38" />

Código usado:

``` sql
SELECT 
    name,
    street
FROM 
    customers
WHERE 
    city = 'Porto Alegre';
```
--------------------------------------------------------------
### Atividade 2607
Problema: Todos os meses a empresa pede um relatório das cidades que os fornecedores estão cadastrados. Dessa vez não vai ser diferente, faça uma consulta no Banco de Dados que retorne todas as cidades dos fornecedores, mas em ordem alfabética.

OBS: Você não deve mostrar cidades repetidas.

<img width="515" height="537" alt="Image" src="https://github.com/user-attachments/assets/fc706b9b-c27c-49d3-a9f2-5c92b19a0ac7" />

Código usado:

``` sql
SELECT
a.city AS city
FROM
providers AS a
ORDER BY a.city ASC;
```
--------------------------------------------------------------
### Atividade 2608
Problema: O setor financeiro da nossa empresa, está querendo saber os menores e maiores valores dos produtos, que vendemos.

Para isso exiba somente o maior e o menor preço da tabela produtos.

<img width="515" height="573" alt="Image" src="https://github.com/user-attachments/assets/01534c84-60bc-4efe-bc30-19fb351c4965" />

Código usado:

``` sql
SELECT
max(price) AS price,
min(price) AS price
FROM
products;
```
--------------------------------------------------------------
### Atividade 2615
Problema: A locadora tem objetivos de criar várias franquias espalhadas pelo Brasil. Para isso queremos saber em quais cidades nossos clientes moram.

Para você nos ajudar selecione o nome de todas as cidades onde a locadora tem clientes. Mas por favor, não repita o nome da cidade.

<img width="515" height="578" alt="Image" src="https://github.com/user-attachments/assets/11dd661b-2212-4caa-8de4-d095406c120f" />

Código usado:

``` sql
SELECT
a.city AS city
FROM
customers AS a
ORDER BY
street;
```
--------------------------------------------------------------
### Atividade 2746
Problema: Os vírus estão evoluindo, porém uma nova pesquisa tem provado que trocando algumas proteínas a vacina se torna imbatível. A proteína H1 (Hemaglutinina) quando é substituída pela proteína X (Xenomorphina) tem efeitos interessantes no combate de quase todas as doenças virais. Alguns conspiracionistas dizem que após a descoberta dessa vacina algumas criaturas de 3 metros de altura foram vistas perto do laboratório, mas claro, isso é mentira.

Portanto você deve substituir todo caractere 'H1' ( Hemaglutinina ) por 'X' ( Xenomorphina ).

<img width="515" height="535" alt="Image" src="https://github.com/user-attachments/assets/a795ff8b-5142-4797-ad23-0ce685fd4977" />

Código usado:

``` sql
SELECT
  REPLACE(name, 'H1', 'X') AS name
FROM
  virus;
```
## Atividade Nível 02
### Atividade 2604
Problema: O setor financeiro da empresa precisa de um relatório que mostre o código e o nome dos produtos cujo preço são menores que 10 ou maiores que 100.

<img width="515" height="631" alt="Image" src="https://github.com/user-attachments/assets/423b5dce-caa5-41d2-97eb-072de6c87887" />

Código usado: 

``` sql
SELECT
  a.id,
  a.name
FROM
  products AS a
WHERE
  price < 10 OR price > 100;
```
--------------------------------------------------------------
### Atividade 2613
Problema: Antigamente a locadora fez um evento em que vários filmes estavam em promoção, queremos saber que filmes eram esses.

Seu trabalho para nós ajudar é selecionar o ID e o nome dos filmes cujo preço for menor que 2.00.

<img width="515" height="725" alt="Image" src="https://github.com/user-attachments/assets/91875c60-5577-4cda-bd3e-f8f7785b7758" />

Código usado:

``` sql
SELECT
  id,
  name
FROM
  movies
WHERE
  id_prices = (
        SELECT
          id
        FROM
          prices
        WHERE value < 2
);
```
## Atividade Nível 03
### Atividade 2610
Problema: Na empresa que você trabalha está sendo feito um levantamento sobre os valores dos produtos que são comercializados.

Para ajudar o setor que está fazendo esse levantamento você deve calcular e exibir o valor médio do preço dos produtos.

OBS: Mostrar o valor com dois números após o ponto.

<img width="515" height="521" alt="Image" src="https://github.com/user-attachments/assets/c2044177-7884-4611-9075-2fc12516d70f" />

Código usado:

``` sql
SELECT
  ROUND(AVG(price),2) AS price
FROM
  products AS a;
```
--------------------------------------------------------------
### Atividade 2606
Problema: Quando os dados foram migrados de Banco de Dados, houve um pequeno mal-entendido por parte do antigo DBA.

Seu chefe precisa que você exiba o código e o nome dos produtos, cuja categoria inicie com 'super'.

<img width="515" height="631" alt="Image" src="https://github.com/user-attachments/assets/444d7bcc-ffe4-40ca-919e-0f22c19b7086" />

Código usado:

``` sql
SELECT
  p.id,
  p.name
FROM
  products AS p
JOIN
  categories AS c ON p.id_categories = c.id
WHERE
  c.name LIKE 'super%';
```
## Atividade Nível 04
### Atividade 2611
Problema: Uma Vídeo locadora contratou seus serviços para catalogar os filmes dela. Eles precisam que você selecione o código e o nome dos filmes cuja descrição do gênero seja 'Action'.

<img width="515" height="664" alt="Image" src="https://github.com/user-attachments/assets/74148c05-f86b-4a65-a129-05e326de3e6b" />

Código usado:

``` sql
SELECT
  m.id,
  m.name
FROM
  movies AS m
JOIN
  genres AS g
    ON
      m.id_gemres = g.id
WHERE
  g.description = 'Action';
```
