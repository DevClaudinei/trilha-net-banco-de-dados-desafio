## Scripts SQL

### -- Script SQL 01

SELECT 
	Nome, Ano
	FROM Filmes;

### -- Script SQL 02

SELECT
	Nome, Ano, Duracao
	FROM Filmes 
	ORDER BY Ano;

### -- Script SQL 03

SELECT 
	Nome, Ano, Duracao
	FROM Filmes
	WHERE NOME='De Volta para o Futuro';

### -- Script SQL 04

SELECT 
	Nome, Ano, Duracao
	FROM Filmes
	WHERE Ano=1997;

### -- Script SQL 05

SELECT 
	Nome, Ano, Duracao
	FROM Filmes
	WHERE Ano>2000;

### -- Script SQL 06

SELECT 
	Nome, Ano, Duracao
	FROM Filmes
	WHERE Duracao > 100 and Duracao < 150
	ORDER BY Duracao;

### -- Script SQL 07

SELECT
    ROW_NUMBER() OVER (ORDER BY Ano) AS Id,
    Ano,
    COUNT(*) AS Quantidade
	FROM Filmes
	GROUP BY Ano
	ORDER BY Quantidade Desc;

### -- Script SQL 08

SELECT * FROM Atores WHERE Genero = 'M';

### -- Script SQL 09

SELECT * FROM Atores WHERE Genero = 'F' ORDER BY PrimeiroNome;

### -- Script SQL 10

SELECT
	F.Nome AS NomeFilme,
	G.Genero AS NomeGenero
	FROM FilmesGenero FG
	JOIN FILMES F ON FG.IdFilme = F.Id
	JOIN Generos G ON FG.IdGenero = G.Id;

### -- Script SQL 11

SELECT
	F.Nome AS NomeFilme,
	G.Genero AS NomeGenero
	FROM FilmesGenero FG
	JOIN FILMES F ON FG.IdFilme = F.Id
	JOIN Generos G ON FG.IdGenero = G.Id
	WHERE G.Genero = 'Mistério';

### -- Script SQL 12

SELECT
	F.Nome AS Nome,
	A.PrimeiroNome AS PrimeiroNome,
	A.UltimoNome AS UltimoNome,
	Papel
	FROM ElencoFilme EF	
	JOIN FILMES F ON EF.IdFilme = F.Id
	JOIN Atores A ON EF.IdAtor = A.Id;

