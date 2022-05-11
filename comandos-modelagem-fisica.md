#Comandos SQL para modelagem física

##Criar banco de dados

CREATE DATABASE vendas_leonardo CHARACTER SET utf8mb4;

## Entrar no banco de dados criado
USE DATABASE vendas_leonardo;

CREATE TABLE fabricantes(
    id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(45) NOT NULL,
);

CREATE TABLE produtos (
    id INT NOT NULL AUTO_IMPLEMENT PRIMARY KEY,
    produto VARCHAR(45) NOT NULL,
    preco DECIMAL(8,2) NOT NULL,
    quantidade SMALLINT NULL,
    descricao TEXT(1000) NOT NULL,
    fabricantes_id INT NOT NULL
)

## Alterando a tabela para criar um relacionamento por meio da chave estrangeira
ALTER TABLE produtos
    ADD CONSTRAINT fk_produtos_fabricantes
    FOREIGN KEY(fabricante_id) REFERENCES fabricante(id)