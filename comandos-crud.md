# Comandos para operações CRUD no Banco de Dados

## Resumo

- C -> **C**reate   -> **INSERT**:inserir dados/registros na tabela
- R -> **R**ead     -> **SELECT**:consultar /ler dados/registros na tabela
- U -> **U**pdate   -> **UPDATE**:atualizar dados/registros na tabela
- D -> **D**elete   -> **DELETE**:excluir dados/registros na tabela

---

## INSERT (Fabricantes)

```sql
INSERT INTO fabricantes (nome) VALUES('Asus');
INSERT INTO fabricantes (nome) VALUES('Dell');
INSERT INTO fabricantes (nome) VALUES('Apple');

INSERT INTO fabricantes (nome) VALUES('LG'),('Samsung'),('Brastemp');
```

## SELECT (Fabricantes)

```sql
SELECT * FROM fabricantes;
```

---

## INSERT (Produtos)

```sql
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)
VALUES(
    'Ultrabook',
    'Equipamento de última geração cheio de recursos, e etc e tal...',
    3999.45,
    7,
    2  -- id do fabricante Dell
 );

 INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)
 VALUES(
    'Tablet Android',
    'Tablet com a versão 16 do sistema operacinal Android, possui tela de 10
    polegadas e armazenamento de 128 GB. Estou sem ideias do que escrever aqui.',
    900,
    12,
    5  -- samsung
 );

 INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)
 VALUES(
    'Geladeira',
    'Refrigerador frost-free com acesso à internet',
    5000,
    12,
    6  -- Brastemp
 ),
 (
    'iPhone 18 Pro Max Ferradão',
    'Smartphone Apple cheio das frescuras e caro pra caramba...coisa de rico...',
    9666.66,
    3,
    3  -- Apple
 ),
 (
    'iPad Mini',
    'Tablet Apple com tela retina display e bla bla bla e mó bunitinha',
    4999.12,
    5,
    3  -- Apple
 );
```
# Comandos do exercício 03

## INSERT (Fabricantes)
```sql
INSERT INTO fabricantes (nome) VALUES('Positivo'),('Microsoft');
```

## INSERT (Produtos)
```sql
INSERT INTO produtos(nome, descricao,preco, quantidade, fabricante_id)
VALUES(
    'Xbox Series S',
    'Um video game de velocidade e desempenho de última geração',
    1997.00,
    5,
    8
),
(
    'Notebook Motion',
    'Notbook da intel Dual Core 4GB de RAM, 128GB SSD e Tela 14,1 polegadas',
    1213.65,
    8,
    7
);
```