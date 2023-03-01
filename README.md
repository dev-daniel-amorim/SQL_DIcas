# SQL dicas

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
Pegando data e hora do sistema

    select GETDATE()
