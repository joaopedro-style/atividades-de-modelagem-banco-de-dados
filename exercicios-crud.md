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
    16.340.000.045,
    25.700.250.050,
    1
),
(
    180,
    'Após Thanos eliminar metade das criaturas vivas, os Vingadores têm de lidar com a perda de amigos e entes queridos',
    85.666.000.020,
    35.700.000.030,
    2
),
(
    120,
    'Soldado chega à casa da família Peterson e diz ser amigo do filho, morto em combate. Ele é acolhido por todos, mas uma série de mortes começa a acontecer e o rapaz mostra suas reais intenções',
    511.450.150.015,
    5.000.000,
    3
),
(
    240,
    'Em uma terra fantástica e única, um hobbit recebe de presente de seu tio um anel mágico e maligno que precisa ser destruído antes que caia nas mãos do mal',
    3.000.000,
    93.500.000.030,
    4
);
```
## UPDATE
```sql
UPDATE filmes SET titulo = 'O Senhor dos Anéis'
WHERE id = 4;
```
