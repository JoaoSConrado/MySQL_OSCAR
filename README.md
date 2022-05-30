# E o Oscar vai para... ? #

Quantas vezes Natalie Portman foi indicada ao Oscar? 

R: 3 VEZES! <code>(SELECT name FROM oscar WHERE name LIKE '%Natalie Portman%')</code>

##

Quantos Oscars Natalie Portman ganhou?

R: 1 VEZ! <code>(SELECT * FROM `oscar` WHERE name LIKE '%Natalie Portman%')</code>

##

Amy Adams já ganhou algum Oscar?

R: ELA NUNCA GANHOU! <code>(SELECT * FROM `oscar` WHERE name LIKE '%Amy Adams%')</code>

##

Alguém já ganhou um Oscar e tem o seu primeiro nome?

R: NÃO! <code>(SELECT * FROM `oscar` WHERE name LIKE '%João%')</code>

##

Toy Story 3 ganhou um Oscar em quais anos?

R: SIM, EM 2010! <code>(SELECT name, year_film FROM oscar WHERE film LIKE '%Toy Story 3%' AND winner LIKE '%TRUE%')</code>

##

Quem tem mais Oscars: a categoria "Melhor Ator" ou "Melhor Filme"?

R: MELHOR ATOR - COM 872 RESULTADOS! <code>(SELECT category, COUNT(category) FROM oscar WHERE category LIKE '%ACTOR%' ) | (SELECT category, COUNT(category) FROM oscar WHERE category LIKE '%CINEMATOGRAPHY%')</code>

##

O primeiro Oscar para melhor Atriz foi para quem? Em que ano?

R: Janet Gaynor, EM 1928! <code>(SELECT name, year_ceremony FROM oscar WHERE category LIKE '%ACTRESS%' AND winner LIKE '%True%')</code>

##

Na categoria Winner, altere todos os valores com "True" para 1 e todos os valores "False" para 0.

R:  TRUE - <code>(UPDATE `oscar` SET `winner`='1' WHERE winner LIKE '%True%')</code>
    FALSE - <code>(UPDATE `oscar` SET `winner`='0' WHERE winner LIKE '%False%')</code>

##

Em qual edição do Oscar "Crash" ganhou o prêmio?

R: FOI NA EDIÇÃO 78! <code>(SELECT ceremony, winner, film, name FROM oscar WHERE film LIKE '%Crash%')</code>

##

Que filme merecia ganhar um Oscar e não ganhou?

R: Vingadores: Guerra Infinita! <code>(SELECT * FROM `oscar` WHERE film LIKE '%Avengers: Infinity War%')</code>

##

Bom... dê um Oscar para esse filme, então.

R: <code>(UPDATE `oscar` SET `winner`='1' WHERE film LIKE '%Avengers: Infinity War%';)</code>

##

O filme Central do Brasil aparece no Oscar?

R: NÃO! <code>(SELECT * FROM `oscar` WHERE film LIKE '%Central do Brasil%')</code>

##

Inclua no banco 7 filmes que nunca nem foram nomeados ao Oscar, mas que na sua opinião, merecem.

R:
1° <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('','2017',NULL,NULL,'MELHOR FILME','Patty Jenkins','MULHER MARAVILHA','1');</code>

2° <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('','2021',NULL,NULL,'MELHOR FILME','Jon Watts','Homem-Aranha: Sem Volta para Casa','1');</code>

3° <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('','2021',NULL,NULL,'MELHOR FILME','Sam Raimi','Doutor Estranho no Multiverso da Loucura','0');</code>

4° <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('','2022',NULL,NULL,'MELHOR FILME','Pierre Perifel','Os Caras Malvados','1');</code>

5° <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('','2022',NULL,NULL,'MELHOR FILME','Domee Shi','Red: Crescer é uma Fera','1');</code>

6° <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('','2022',NULL,NULL,'MELHOR FILME','Matt Reeves','The Batman','0');</code>

7° <code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('','2021',NULL,NULL,'MELHOR FILME','Andy Serkis','Venom: Tempo de Carnificina','0');</code>

##

Crie uma nova categoria de premiação. Qualquer prêmio que você queira dar. Agora vamos dar esses prêmios aos filmes que você cadastrou na questão acima.

R: <code>ALTER TABLE oscar ADD PRÊMIO varchar(225)
   UPDATE `oscar` SET `PRÊMIO`='BOLO DE CENOURA' WHERE category LIKE '%MELHOR FILME%'</code>

##

Qual foi o primeiro ano a ter um prêmio do Oscar?

R: FOI EM 1928! <code>SELECT * FROM `oscar` WHERE winner;</code>

##

Pensando no ano em que você nasceu: Qual foi o Oscar de melhor filme, Melhor Atriz e Melhor Diretor?

R: MELHOR FILME (Conrad L. Hall) - <code>SELECT * FROM `oscar` WHERE year_ceremony LIKE '%2003%' AND category LIKE'%CINEMATOGRAPHY%';</code>

   MELHOR ATRIZ (Nicole Kidman) - <code>SELECT * FROM `oscar` WHERE year_ceremony LIKE '%2003%' AND category LIKE'%ACTRESS%';</code>

   MELHOR DIRETOR (Roman Polanski) - <code>SELECT * FROM `oscar` WHERE year_ceremony LIKE '%2003%' AND category LIKE'%DIRECTING%';</code>

##

Agora procure 7 atrizes que não sejam americanas, europeias ou brasileiras.  Vamos cadastrá-los no nosso banco, mas eles ainda não ganharam o Oscar. Só foram nomeados.

R:
<code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`, `PRÊMIO`) VALUES ('','2021','2022','','ACTRESS','Cate Blanchett','Não Olhe Para Cima','0','');</code>

<code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`, `PRÊMIO`) VALUES ('','2016','2022','','ACTRESS','Nicole Kidman','O Mestre dos Gênios','0','');</code>

<code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`, `PRÊMIO`) VALUES ('','2016','2022','','ACTRESS','Margot Robbie','Esquadrão Suicida','0','');</code>

<code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`, `PRÊMIO`) VALUES ('','2012','2022','','ACTRESS','Rebel Wilson','A Escolha Perfeita','0','');</code>

<code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`, `PRÊMIO`) VALUES ('','2018','2022','','ACTRESS','Ruby Rose','Megatubarão','0','');</code>

<code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`, `PRÊMIO`) VALUES ('','2018','2022','','ACTRESS','Toni Collette','Hereditário','0','');</code>

<code>INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`, `PRÊMIO`) VALUES ('','2010','2022','','ACTRESS','Mia Wasikowska','Alice no País das Maravilhas','0','');</code>


##

Utilizando o comando 'Alter Table', troque os tipos dos dados da coluna/campo "Winner" para Bit.

R: <code>ALTER TABLE oscar CHANGE winner bit INT(10);</code>




















