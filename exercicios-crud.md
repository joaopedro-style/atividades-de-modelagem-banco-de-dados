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
    'O hóspede',
    '1955-10-20',
    4
);

INSERT INTO detalhes (duracao, sinopse, bilheteria, orcamento, filme_id)
VALUES(
    120,
    'Um inimigo sem escrúpulos planeja uma vingança brutal e libera um vírus mortal.',
    16.340.000.45,
),
```