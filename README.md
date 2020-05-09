# BDudemy
Install on windows:

Install on linux:

Curso de Banco de Dados completo, sem mistérios

Banco de dados sempre foi meu principal erro e que fez de desistir de programar. 

BD foi executado a partir de um virtual box com linux ubuntu. Baixamos o mysql, brmodelo(serve para desenhar os relacionamentos), notepad++(serve para digitar os comandos antes de executa-los no terminal).
O banco de dados armazena as informações dos requisitos dos usuários. Saber a plataforma que será construído o BD.
Sempre saber sobre o escopo e os requisitos solicitados pelo cliente, inclusive dar opnião.

AD e DBA ---- OLTP
BI ---- OLAP (olhar o que aconteceu)
Data Science --- (prever resultados)
Machine Learn -- Melhorar resultados

Comandos e Atatlhos:

BRMODELO: quando adicionar os atributos apertar ctrl+o para organizar em relação a entidade

Acessar o mysql que já está instalado: 
mysql -u root -p

Criar database
CREATE DATABASE NOME;

ENTRA NO BD(APENAS MYSQL)
USE NOME;

CRIAR UMA TABELA:

CREATE TABLE NOME(
  ATRIBUTO1 TYPE(U1),
  ATRIBUTO2 TYPE(U2),
  .
  .
  .
  ATRIBUTON TYPE(UN)
  );
  
  TYPES:
  CHAR(TAMANHO FIXO)  VARCHAR(VARIA A QUANTIDADE DEPENDENDO DO TAMANHO ALOCADO, MAS É MENOS EFICIENTE)
  
  FLOAT(REAL) FLOAT(TOTAL,CASASDECIMAIS) i INT(X) => X NO MÁXIMO 11, MAS ELE NÃO CONSEGUE CHEGAR ATÉ 999999999 PRECISA OLHAR O RANGE 
  DOS TYPES NO MANUAL DE REFERÊNCIA
  
  BOOP(APPS)  | TEXT
  
  DOIS MÉTODOS PARA INSERIR AS LINHAS(TUPLAS) NAS TABELAS:
  
  1)
  INSERT INTO NOMEDATABELA VALUES('VALOR1','VALOR2','VALOR3', 'VALOR4',...,'VALORN');
  
  2)
  INSERT INTO NOMEDATABELA(ATRIBUTO1,ATRIBUTO2,ATRIBUTO3,...,ATRIBUTO4) VALUES('','','','',...,''); => LEMBRANDO NOME_DO_AUTOR
  ----------------------------------------------------
  EXEMPLO UTILIZADO NO CURSO:
  CREATE TABLE LIVROS(
	NOME_DO_LIVRO VARCHAR(30),
	NOME_DO_AUTOR VARCHAR(30),
	SEXO_DO_AUTOR CHAR(1),
	NUMERO_DE_PAGINAS INT(4),
	NOME_DA_EDITORA VARCHAR(30),
	VALOR_DO_LIVRO FLOAT(6,2),
	ESTADO_UF_DA_EDITORA CHAR(2),
	ANO_PUBLICACAO INT(4)
	);

INSERT INTO LIVROS(NOME_DO_LIVRO,NOME_DO_AUTOR,SEXO_DO_AUTOR,NUMERO_DE_PAGINAS,NOME_DA_EDITORA,VALOR_DO_LIVRO,ESTADO_UF_DA_EDITORA,ANO_PUBLICACAO) VALUES('O poder da mente','Clara Mafra','F',120,'Continental',56.58,'SP',2017);
-------------------------------------
  
  SELECT
  
  LEMBRAR QUE SELCT É UMA PROJEÇÃO ELE IRÁ PROJETAR O QUE QUEREMOS MESMO QUE NÃO EXISTA UM ATRIBUTO ELE IRÁ PROJETAR.
  
  SHOW TABLES; (SÓ EXISTE NO MYSQL)(SERVE COMO PONTEIRO)
  SELECT * FROM NOMETABELA => MOSTRA TODA A TABELA, NÃO UTILIZAR ISSO QUANDO NÃO SE TEM CERTEZA SE A DB É MUITO GRANDE
  
  SELECT NOW(); MOSTRA A HORA
  SELECT NOW() AS DATA_HORA, 'DENI' AS PROFESSOR => MESMO QUE NÃO EXISTA ISSO NA TABELA ELE IRÁ MOSTRAR A HORA,DATA NA COLUNA DATA_HORA(MESMO QUE NÃO EXISTA) E ME COLOCAR COMO PROFESSOR
  
  SELECT ATRIBUTO1, ATRIBUTO2 AS NOMETABELA; PROJETA ESSES ATRIBUTOS E NÃO PRECISAM ESTAR NESSA SEQUÊNCIA
  
  FILTRO
  
  SELECT ATRIBUTO1, ATRIBUTO2,...ATRIBUTON FROM NOME DA TABELA
  WHERE ATRIBUTOX='';
  
  QUANDO TIVERMOS ALGO VALOR QUE QUEREMOS PROCURAR NO MEIO DA PALAVRA UTILIZAREMOS:
  WHERE ATRIBUTO LIKE '%OQUEQUEREMOS'   qowqhOQUEQUEREMOS OQUEQUEREMOSooeiws(OQUEQUEREMOS%) qwdwqdOQUEQUEREMOSqidnoidnqo(%OQUEQUEREMOS%)
  
  like não é bom utilizar demora demais e perde performace.
  
  lembrar podemos utilizar or and e not(mostra o complemento do que estamos analisando)
