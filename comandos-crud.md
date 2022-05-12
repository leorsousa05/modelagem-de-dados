# Comandos CRUD SQL



## Resumo da sigla

- C -> CREATE (INSERT, inserir dados)

- R -> READ (SELECT, leitura de dados)

- U -> UPDATE (UPDATE, atualizar dados)

- D -> DELETE (DELETE, exluir dados)



## INSERT

INSERT INTO fabricantes(nome) VALUES ('Asus');

INSERT INTO fabricantes(nome) VALUES ('Dell');

INSERT INTO fabricantes(nome) VALUES ('Apple');

INSERT INTO fabricantes(nome) VALUES ('LG');



INSERT INTO fabricantes(nome)

VALUES('Samsumg'), ('Microsoft'), ('Brastemp');

##Produtos

INSERT INTO produtos(produto, preco, quantidade, descricao, fabricantes_id)
VALUES('TV Led', 2000, 5, 'TV de última geração', 5)

INSERT INTO produtos(produto, preco, quantidade, descricao, fabricantes_id)
VALUES('iPHONE XYZ', 5500.79, 8, 'Smartphone caro pra caramba', 3)

INSERT INTO produtos(produto, preco, quantidade, descricao, fabricantes_id) VALUES
(
    'Geladeira',
    1500,
    10,
    'Refrigerador Frost-free com acesso à Internet das Coisas e bla bla bla',
    7 -- Brastemp
),
(
    'iPad Mini',
    5000,
    8,
    'Tablet Apple com tela retina display de 4k, memória interna de 64GB, acesso ao iCloud.',
    3 -- Apple
),
(
    'Xbox',
    2500,
    6,
    'Console de última geração com acesso aos melhores jogos e bla bla',
    6 -- Microsoft
),
(
    'Ultrabook',
    4500.68,
    12,
    'Equipamento com processador AMD Ryzen5, 12GB de RAM, placa de vídeo RTX',
    1 -- Asus
),
(
    'Headset',
    120,
    9,
    'Fone de ouvido USB com alta qualidade',
    6 -- Microsoft
),
(
    'Tablet Android',
    4999,
    3,
    'Tablet com a versão 12 do sistema operacional da Google, possui tela de 10 polegadas e armazenamento de 64GB.',
    5 -- Samsung
);

## SELECT

SELECT produto FROM produtos;
SELECT preco FROM produtos;

SELECT produto, preco FROM produtos 
WHERE preco < 3000 AND preco > 2000;

SELECT produto, preco FROM produtos 
WHERE fabricantes_id = 3 OR fabricantes_id = 1;

SELECT produto, descricao FROM produtos ORDER BY produto; -- CRESCENTE 

SELECT produto, descricao FROM produtos ORDER BY produto DESC; -- DECRESCENTE

SELECT
    produtos.nome AS Produtos,
    fabricante.nome AS Fabricantes,
    produtos.preco AS Preço,
    produtos.quantidade AS Quantidade,
FROM produtos INNER JOIN fabricantes
ON produtos.fabricantes_id = fabricantes.id


--INNER JOIN: comando que permite juntar duas ou mais tabelas

--ON: comando para indicar a maeira como as tabelas são juntadas
-- AS: comando que permite dar um apelido para as colunas

## UPDATE
UPDATE fabricantes SET nome = 'LG do Brasil
WHERE id = 4;

## DELETE
DELETE FROM produtos WHERE id = 5;