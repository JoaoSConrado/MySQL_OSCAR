# E o Oscar vai para... ? #

Quantas vezes Natalie Portman foi indicada ao Oscar? 

R: 3 VEZES! (SELECT name FROM oscar WHERE name LIKE '%Natalie Portman%')

##

Quantos Oscars Natalie Portman ganhou?

R: 1 VEZ! (SELECT * FROM `oscar` WHERE name LIKE '%Natalie Portman%')

##

Amy Adams já ganhou algum Oscar?

R: ELA NUNCA GANHOU! (SELECT * FROM `oscar` WHERE name LIKE '%Amy Adams%')

##

Alguém já ganhou um Oscar e tem o seu primeiro nome?

R: NÃO! (SELECT * FROM `oscar` WHERE name LIKE '%João%')

##

Toy Story 3 ganhou um Oscar em quais anos?

R: SIM, EM 2010! (SELECT name, year_film FROM oscar WHERE film LIKE '%Toy Story 3%' AND winner LIKE '%TRUE%')

##

Quem tem mais Oscars: a categoria "Melhor Ator" ou "Melhor Filme"?

R: MELHOR ATOR - COM 872 RESULTADOS! (SELECT category, COUNT(category) FROM oscar WHERE category LIKE '%ACTOR%' ) | (SELECT category, COUNT(category) FROM oscar WHERE category LIKE '%CINEMATOGRAPHY%')

##

O primeiro Oscar para melhor Atriz foi para quem? Em que ano?

R: Janet Gaynor, EM 1928! (SELECT name, year_ceremony FROM oscar WHERE category LIKE '%ACTRESS%' AND winner LIKE '%True%')

##

Na categoria Winner, altere todos os valores com "True" para 1 e todos os valores "False" para 0.

R:  TRUE - (UPDATE `oscar` SET `winner`='1' WHERE winner LIKE '%True%')
    FALSE - (UPDATE `oscar` SET `winner`='0' WHERE winner LIKE '%False%')

##

Em qual edição do Oscar "Crash" ganhou o prêmio?

R: FOI NA EDIÇÃO 78! (SELECT ceremony, winner, film, name FROM oscar WHERE film LIKE '%Crash%')

##

Que filme merecia ganhar um Oscar e não ganhou?

R: Vingadores: Guerra Infinita! (SELECT * FROM `oscar` WHERE film LIKE '%Avengers: Infinity War%')

##

Bom... dê um Oscar para esse filme, então.

R: (UPDATE `oscar` SET `winner`='1' WHERE film LIKE '%Avengers: Infinity War%';)

##

O filme Central do Brasil aparece no Oscar?

R: NÃO! (SELECT * FROM `oscar` WHERE film LIKE '%Central do Brasil%')

##

Inclua no banco 7 filmes que nunca nem foram nomeados ao Oscar, mas que na sua opinião, merecem.

R:
1° INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('','2017',NULL,NULL,'MELHOR FILME','Patty Jenkins','MULHER MARAVILHA','1');

2° INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('','2021',NULL,NULL,'MELHOR FILME','Jon Watts','Homem-Aranha: Sem Volta para Casa','1');

3° INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('','2021',NULL,NULL,'MELHOR FILME','Sam Raimi','Doutor Estranho no Multiverso da Loucura','0');

4° INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('','2022',NULL,NULL,'MELHOR FILME','Pierre Perifel','Os Caras Malvados','1');

5° INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('','2022',NULL,NULL,'MELHOR FILME','Domee Shi','Red: Crescer é uma Fera','1');

6° INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('','2022',NULL,NULL,'MELHOR FILME','Matt Reeves','The Batman','0');

7° INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`) VALUES ('','2021',NULL,NULL,'MELHOR FILME','Andy Serkis','Venom: Tempo de Carnificina','0');

##

Crie uma nova categoria de premiação. Qualquer prêmio que você queira dar. Agora vamos dar esses prêmios aos filmes que você cadastrou na questão acima.

R: ALTER TABLE oscar ADD PRÊMIO varchar(225)
   UPDATE `oscar` SET `PRÊMIO`='BOLO DE CENOURA' WHERE category LIKE '%MELHOR FILME%'

##

Qual foi o primeiro ano a ter um prêmio do Oscar?

R: FOI EM 1928! SELECT * FROM `oscar` WHERE winner; 

##

Pensando no ano em que você nasceu: Qual foi o Oscar de melhor filme, Melhor Atriz e Melhor Diretor?

R: MELHOR FILME (Conrad L. Hall) - SELECT * FROM `oscar` WHERE year_ceremony LIKE '%2003%' AND category LIKE'%CINEMATOGRAPHY%';

   MELHOR ATRIZ (Nicole Kidman) - SELECT * FROM `oscar` WHERE year_ceremony LIKE '%2003%' AND category LIKE'%ACTRESS%';

   MELHOR DIRETOR (Roman Polanski) - SELECT * FROM `oscar` WHERE year_ceremony LIKE '%2003%' AND category LIKE'%DIRECTING%';

##

Agora procure 7 atrizes que não sejam americanas, europeias ou brasileiras.  Vamos cadastrá-los no nosso banco, mas eles ainda não ganharam o Oscar. Só foram nomeados.

R:
INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`, `PRÊMIO`) VALUES ('','2021','2022','','ACTRESS','Cate Blanchett','Não Olhe Para Cima','0','');

INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`, `PRÊMIO`) VALUES ('','2016','2022','','ACTRESS','Nicole Kidman','O Mestre dos Gênios','0','');

INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`, `PRÊMIO`) VALUES ('','2016','2022','','ACTRESS','Margot Robbie','Esquadrão Suicida','0','');

INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`, `PRÊMIO`) VALUES ('','2012','2022','','ACTRESS','Rebel Wilson','A Escolha Perfeita','0','');

INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`, `PRÊMIO`) VALUES ('','2018','2022','','ACTRESS','Ruby Rose','Megatubarão','0','');

INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`, `PRÊMIO`) VALUES ('','2018','2022','','ACTRESS','Toni Collette','Hereditário','0','');

INSERT INTO `oscar`(`id`, `year_film`, `year_ceremony`, `ceremony`, `category`, `name`, `film`, `winner`, `PRÊMIO`) VALUES ('','2010','2022','','ACTRESS','Mia Wasikowska','Alice no País das Maravilhas','0','');


##

Utilizando o comando 'Alter Table', troque os tipos dos dados da coluna/campo "Winner" para Bit.

R: ALTER TABLE oscar CHANGE winner bit INT(10);




















