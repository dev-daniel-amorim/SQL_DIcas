# SQL dicas

## Conversão de dados CAST
CAST converte dados de qualquer tipo para um tipo de dados especificado;

EX 1: Converter o INT 128 para um VARCHAR e concatenar com o texto:

    -- 'O numero é " + CAST(128 AS VARCHAR)

ex 2: Converter um valor TEXTO em dados datetime:

    -- SELECT CAST('2017-08-25' AS datetime);
