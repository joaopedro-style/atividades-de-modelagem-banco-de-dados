# Exercício 04 Expermentando comandos CRUD

## INSERT (Generos, Filmes, Detalhes)

```sql
INSERT INTO generos (nome) VALUES('Terror');
INSERT INTO generos (nome) VALUES('ação');
INSERT INTO generos (nome) VALUES('suspense');
INSERT INTO generos (nome) VALUES('fantasia');

INSERT INTO filmes (titulo, lancamento, genero_id)
VALUES(
    'Resident evil vingança',
    '2017-05-27',
    1
),
(
    'Vingadores ultimato',
    '2019-04-22',
    2
),
(
    'O hóspede',
    '2014-09-17',
    3
),
(
    'O Senhor dos Anéis',
    '1955-10-20',
    4
);

INSERT INTO detalhes (duracao, sinopse, bilheteria, orcamento, filme_id)
VALUES(
    120,
    'Um inimigo sem escrúpulos planeja uma vingança brutal e libera um vírus mortal',
    16340000.45,
    25700250.50,
    1
),
(
    180,
    'Após Thanos eliminar metade das criaturas vivas, os Vingadores têm de lidar com a perda de amigos e entes queridos',
    85666000.20,
    35700000.30,
    2
),
(
    120,
    'Soldado chega à casa da família Peterson e diz ser amigo do filho, morto em combate. Ele é acolhido por todos, mas uma série de mortes começa a acontecer e o rapaz mostra suas reais intenções',
    511450150.15,
    500000.00,
    3
),
(
    240,
    'Em uma terra fantástica e única, um hobbit recebe de presente de seu tio um anel mágico e maligno que precisa ser destruído antes que caia nas mãos do mal',
    300000.00,
    935000.00,
    4
);
```
## UPDATE

```sql
UPDATE filmes SET titulo = 'O Senhor dos Anéis'
WHERE id = 4;
```

## SELECT

```sql
SELECT * FROM filmes;
SELECT titulo, lancamento FROM filmes;
SELECT sinopse, filme_id FROM detalhes;
```

## DELETE

```sql
DELETE FROM filmes WHERE id = 3;
```
## Operações e funções de geração

```sql
SELECT filmes.titulo AS Filme, generos.nome AS Genero FROM filmes JOIN generos ON filmes.genero_id = generos.id;

SELECT filmes.titulo AS Filme, detalhes.sinopse AS Sinopse FROM detalhes JOIN filmes ON detalhes.filme_id = filmes.id;

SELECT
    filmes.titulo AS Filme,
    generos.nome AS Genero,
    detalhes.sinopse As Sinopse
FROM filmes INNER JOIN generos    


```
