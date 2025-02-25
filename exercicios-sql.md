## Criando o banco de dados do exercício de sql

```sql
CREATE DATABASE catalogo_de_filmes CHARACTER SET utf8mb4;
```

### Criando a tabela de Generos

```sql
CREATE TABLE generos(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(45) NOT NULL
);
```

```sql
-- alterei o nome da tabela
ALTER TABLE genero RENAME TO generos;
```

```sql
-- alterei o nome genero para nome
ALTER TABLE generos CHANGE genero nome VARCHAR(45) NOT NULL;
```

```sql
-- alterei o VARCHAR para 200
ALTER TABLE filmes MODIFY COLUMN titulo VARCHAR(200) NOT NULL;
```

### Criando a tabela de filmes

```sql
CREATE TABLE filmes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    titulo VARCHAR(200) NOT NULL,
    lancamento DATE NOT NULL,
    genero_id INT NOT NULL
);
```

### Criando a tabela detalhes

```sql
CREATE TABLE detalhes(
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    duracao INT NOT NULL,
    sinopse TEXT(1000) NOT NULL,
    bilheteria DECIMAL(16,2) NULL,
    orcamento DECIMAL(16,2) NULL,
    filme_id INT NOT NULL
);
```

### Criando relacionamento entre as tabelas

```sql
ALTER TABLE detalhes
    ADD CONSTRAINT fk_detalhes_do_filmes
    FOREIGN KEY (filme_id) REFERENCES filmes(id);
```

```sql
ALTER TABLE filmes
    ADD CONSTRAINT fk_filmes_generos
    FOREIGN KEY (genero_id) REFERENCES generos(id);
```