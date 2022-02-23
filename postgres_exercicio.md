# Exercícios

Com um terminal aberto conectado ao banco (com o comando `bash connect-database`), execute as seguintes consultas:

1. Busque produtos quaisquer, limitados a 5;
    - Resultado esperado
        
        ```
         id |          nome          | preco  
        ----+------------------------+--------
          1 | Televisão 43"          | 139997
          2 | Televisão 55"          | 250000
          3 | Notebook Entrada       | 200000
          4 | Notebook Intermediário | 350000
          5 | Notebook Topo de Linha | 600000
        (5 rows)
        ```
        
2. Busque clientes quaisquer da loja, limitados a 3;
    - Resultado esperado
        
        ```
         id |          nome          |     cpf     
        ----+------------------------+-------------
          1 | Allana Fidalgo Moreira | 12345678900
          2 | Benício Freire Sampaio | 98765432100
          3 | Orlando Pequeno Jesus  | 10293847560
        (3 rows)
        ```
        
3. Busque o produto com nome `Televisão 43"`;
    - Resultado esperado
        
        ```
         id |     nome      | preco  
        ----+---------------+--------
          1 | Televisão 43" | 139997
        (1 row)
        ```
        
4. Adicione um novo produto chamado `Macbook Pro 13"` com preço R$ 17.000,00;
    - Resultado esperado
        
        ```
        INSERT 0 1
        ```
        
5. `Orlando Pequeno Jesus` fez barraco na loja e agora está banido. Remova-o da lista de clientes;
    - Resultado esperado
        
        ```
        DELETE 1
        ```
        
6. O dólar subiu mais uma vez e o preço do produto `Pelúcia Strange Planet com Gatinho` agora é R$ 80,00. Atualize no banco;
    - Resultado esperado
        
        ```
        UPDATE 1
        ```
        
7. A alta do dólar também afetou o preço do Violão Lava ME 2. Altere seu preço para R$ 9800,00. Atualize o banco.
    - Resultado esperado
        
        ```
        UPDATE 1
        ```
        
8. Lucca Santarém Branco usou o CPF de um laranja. Modifique seu CPF para o valor correto: `04652651298`;
    - Resultado esperado
        
        ```
        UPDATE 1
        ```
        
9. Chico Buarque de Holanda comprou o produto `Violão Lava ME 2`. Adicione esse registro de compra na tabela `compra`;
    - Resultado esperado
        
        ```
        INSERT 0 1
        ```
        
10. Olga Cascais Fortunato comprou dois `Celular Topo de Linha`. Adicione os registros de compra na tabela `compra`;
    - Resultado esperado
        
        ```
        INSERT 0 1
        INSERT 0 1
        # ou
        INSERT 0 2
        ```
        
11. Martinha Lima Zambujal devolveu o produto `Fone Topo de Linha`. Remova este registro da tabela `compra`;
    - Resultado esperado
        
        ```
        DELETE 1
        ```
        
12. Busque todos os produtos ordenados pelo preço, de forma crescente. Para este item, procure por `sql order by`;
    - Resultado esperado
        
        ```
         id |                nome                |  preco  
        ----+------------------------------------+---------
         12 | Fone Entrada                       |    2000
          9 | Pelúcia Strange Planet com Gatinho |    8000
         13 | Fone Intermediário                 |   20000
         14 | Fone Topo de Linha                 |   80000
          6 | Celular Entrada                    |   80000
          1 | Televisão 43"                      |  139997
          7 | Celular Intermediário              |  160000
          3 | Notebook Entrada                   |  200000
          2 | Televisão 55"                      |  250000
          8 | Celular Topo de Linha              |  340000
          4 | Notebook Intermediário             |  350000
         11 | Bicicleta Elétrica                 |  370000
          5 | Notebook Topo de Linha             |  600000
         10 | Violão Lava ME 2                   |  980000
         15 | Macbook Pro 13"                    | 1700000
        (15 rows)
        ```
        
13. Busque os 3 produtos mais baratos;
    - Resultado esperado
        
        ```
         id |                nome                | preco 
        ----+------------------------------------+-------
         12 | Fone Entrada                       |  2000
          9 | Pelúcia Strange Planet com Gatinho |  8000
         13 | Fone Intermediário                 | 20000
        (3 rows)
        ```
        
14. Busque o produto com o maior preço;
    - Resultado esperado
        
        ```
         id |      nome       |  preco  
        ----+-----------------+---------
         15 | Macbook Pro 13" | 1700000
        (1 row)
        ```
        
15. Busque o produto com o segundo menor preço. Para este item, procure por `sql offset`.
    - Resultado esperado
        
        ```
         id |                nome                | preco 
        ----+------------------------------------+-------
          9 | Pelúcia Strange Planet com Gatinho |  8000
        (1 row)
        ```
        

# Desafios

1. Busque todos os produtos com `Televisão` no nome. Para fazer isso, procure por `sql like operator`;
    - Resultado esperado
        
        ```
         id |     nome      | preco  
        ----+---------------+--------
          1 | Televisão 43" | 139997
          2 | Televisão 55" | 250000
        (2 rows)
        ```
        
2. Busque todos os produtos com preço menor que R$1000,00. Para fazer isso, procure por `sql comparison operators`;
    - Resultado esperado
        
        ```
         id |                nome                | preco 
        ----+------------------------------------+-------
          6 | Celular Entrada                    | 80000
         12 | Fone Entrada                       |  2000
         13 | Fone Intermediário                 | 20000
         14 | Fone Topo de Linha                 | 80000
          9 | Pelúcia Strange Planet com Gatinho |  8000
        (5 rows)
        ```
        
3. Busque todos os produtos com `Celular` no nome e preço menor que R$2000,00. Para isso, utilize o operador `like` do item anterior e procure por `sql logical operators`;
    - Resultado esperado
        
        ```
        id |         nome          | preco  
        ----+-----------------------+--------
          6 | Celular Entrada       |  80000
          7 | Celular Intermediário | 160000
        (2 rows)
        ```
        
4. (Desafio²) Busque todos os clientes que não fizeram uma compra. Para isso, procure por `sql not in` e `sql subquery`.
    - Resultado esperado
        
        ```
         id |          nome           |     cpf     
        ----+-------------------------+-------------
          5 | Martinha Lima Zambujal  | 11992288445
         10 | Patrícia Toste Prudente | 19847457596
          9 | Lucca Santarém Branco   | 4652651298
        (3 rows)
        ```
        
5. (Desafio²) Busque todos os produtos comprados por `Benício Freire Sampaio`. Para isso, procure por `sql in` e `sql subquery`;
    - Resultado esperado


Respostas
	<ul>
		select * from produtos limit 5;
		select * from clientes limit 3;
		select * from produtos where nome='Televisão 43"';
		insert into produtos (nome, preco) values ('Macbook Pro 13"', 1700000);
		delete from clientes where nome='Orlando Pequeno Jesus';
		update produtos set preco=8000 where nome='Pelúcia Strange Planet com Gatinho';
		update produtos set preco=980000 where nome='Violão Lava ME 2';
		update clientes set cpf='04652651298' where nome='Lucca Santarém Branco';
		insert into compras (id_cliente, id_produto) values ((select id from clientes where nome='Chico Buarque de Holanda'), (select id from produtos where nome='Violão Lava ME 2'));
		insert into compras (id_cliente, id_produto) values ((select id from clientes where nome='Olga Cascais Fortunato'), (select id from produtos where nome='Celular Topo de Linha')), ((select id from clientes where nome='Olga Cascais Fortunato'), (select id from produtos where nome='Celular Topo de Linha'));
		delete from compras where id_cliente=(select id from clientes where nome='Martinha Lima Zambujal') and id_produto=(select id from produtos where nome='Fone Topo de Linha');
		select * from produtos order by preco;
		select * from produtos order by preco limit 3;
		select * from produtos order by preco desc limit 1;
		select * from produtos order by preco limit 1 offset 1;

	</ul>

	# Desafios

	<ul>
		select * from produtos where nome like 'Televisão%';
		select * from produtos where preco<100000;
		select * from produtos where nome like 'Celular%' and preco<200000;
		select * from clientes where id not in (select id_cliente from compras);
		select * from produtos where id in (select id_produto from compras where id_cliente=(select id from clientes where nome='Benício Freire Sampaio'));
	</ul>











