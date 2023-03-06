# SQL dicas (Minhas anotações SQL)

## Conversão de dados com CAST
CAST converte dados de qualquer tipo para um tipo de dados especificado;

EX 1: Converter o INT 128 para um VARCHAR e concatenar com o texto:

    -- 'O numero é " + CAST(128 AS VARCHAR)

EX 2: Converter um valor TEXTO em dados datetime:

    -- SELECT CAST('2017-08-25' AS datetime);
    
## Conversão de dados com CONVERT
CONVERT assim como CAST converte dados para um tipo especificado.

EX 1: Converter um valor TEXTO em dados datetime:

    -- SELECT CONVERT(datetime, '2017-08-25');
    
## Tratalhando com datas
Pegando data/hora do sistema

    select GETDATE() -- DATA E HORA COMPLETA
    SELECT DATEPART(DW, GETDATE()) -- DIA DA SEMANA 1, 2, 3..
    SELECT DATENAME(DW, GETDATE()) -- DIA DA SEMANA 'SEGUNDA', 'TERÇA'...
    
Adicionando 2 dias ou 2 meses ou 2 anos a uma data de uma tabela compras

    UPDATE compras as c
    SET c.DATA = DATEADD(D,M,Y? valor_do_incremento, c.DATA) 
    
Na tabela VENDAS, separand a data da coluna DATA em outras colunas de MES e ANO

    SELECT MONTH(DATA) AS MES, YEAR(DATA) AS ANO
    FROM VENDAS


## Cláusula EXISTS
O exists verifica se existe algum resultado para a subquery informada, caso TRUE irá executar a query principal que está solicitando a verificação, caso FALSE a query não será executada. Exemplo:

    SELECT JOGADORES
    FROM PARTIDA
    WHERE EXISTS(SELECT *
                FROM JOGO
                WHERE BOLA = 1)
                
No exemplo acima fazemos uma analogia a um jogo onde pedimos para selecionar todos JOGADORES da PARTIDA mas só se EXISTIR na tabela JOGO uma bola igual a 1, caso exista os jogadores serão selecionados, caso contrario nenhum jogador sera selecionado.
