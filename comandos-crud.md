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
INSERT INTO produtos(nome, descricao, preco, quantidade, fabricante_id)
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

---

## Select (Produtos)

```sql
-- Lendo TODAS as colunas de TODOS os registros
SELECT * FROM produtos;

-- Lendo somente nome e preco de todos os registros
SELECT nome, preco FROM produtos;
SELECT preco, nome FROM produtos;

-- Mostrar nome, preco e quantidade SOMENTE dos produtos que custam abaixo de 5000
SELECT nome, preco, quantidade FROM produtos
WHERE preco < 5000;

-- Mini-exercício: mostre o nome e descrição somente dos produtos da Apple

SELECT nome, descricao FROM produtos
WHERE fabricante_id = 3;
```

### Operadores Lógicos: E, OU e NÃO

#### E (AND)

```sql
-- Exibir nome e preco dos produtos que custam entre 2000 e 6000
SELECT nome, preco FROM produtos
WHERE preco >= 2000 AND preco <= 6000;
```

#### OU (OR)

```sql
-- Mini-exercício: exibir nome, descricao dos produtos da Apple e da samsung
SELECT nome, descricao FROM produtos
WHERE fabricante_id = 3 OR fabricante_id = 5;

-- Versão usando a função SQL IN()
SELECT nome, descricao FROM produtos
WHERE fabricante_id IN(3, 5);
```

#### NÃO (NOT)

```sql
-- Nome, descricao e preço de todos os produtos EXCETO da Positivo
SELECT nome, descricao, preco FROM produtos
WHERE NOT fabricante_id = 8;

-- Verão usando operador relacional de "diferença/diferente"
SELECT nome, descricao, preco FROM produtos
WHERE fabricante_id !=8;
```

---

## UPDATE (Fabricantes e produtos)

**☠️ PERIGO! 🚨**

**SEMPRE USE** a cláusula `WHERE` em seu comando `UPDATE` especificando uma ou mais condições para a atualização.

```sql
UPDATE fabricantes SET nome = 'Asus do Brasil'
WHERE id = 1;

-- Mini-exerício: Alterar a quantiade para 10 dos produtos que custam abaixo de 2000 exceto da Microsoft.
UPDATE produtos SET quantidade = 10
WHERE preco < 2000 AND fabricante_id !=8;
```

---

## DELETE (Fabricantes e Produtos)

**☠️ PERIGO! 🚨**

**SEMPRE USE** a cláusula `WHERE` em seu comando `DELETE` especificando uma ou mais condições para a atualização.

```sql
DELETE FROM fabricantes WHERE id = 4;
DELETE FROM fabricantes WHERE id = 1;
DELETE FROM produtos WHERE id = 4;
DELETE FROM fabricantes WHERE id = 3;
```

---

## SELECT: outras formas de uso

### Classificação/Ordenação

```sql
-- DESC: ordena em ordem decrescente
-- ASC: ordena em ordem crescente (padrão)
SELECT nome, preco FROM produtos ORDER BY nome;
SELECT nome, preco FROM produtos ORDER BY preco;
SELECT nome, preco FROM produtos ORDER BY preco DESC;

SELECT nome, preco, quantidade FROM produtos
WHERE fabricante_id = 5 ORDER BY quantidade;
```