# desafio
systock desafio



#Instalação 

-Primeiramente estudei sobre o pentaho e a melhor forma de utilizar.
-Verifiquei tanto em docker e Máquina Física .

Utilizei o docker para acelerar o processo , onde executei em minha máquina linux (vm) própria , pois acredito que seja melhor utilizando linux.

-O docker não foi concluido com sucesso  visto que errei a versão correta para o PDI .
(erros no docker que são simples de ajustar) 
Utilizo porteiner para adm meu docker's.

--Após estudos fiz pela vm ( ubuntu 22.04) a instalação do PDI .
Ajustei o JAVA_ HOME onde o mesmo apontava para >/usr/lib/jvm/java-11-openjdk-amd64
Precisei ir ao repositório do PDI ( HITACHI) para realziar o wget 

	OPTEI o dir >/home/pdi ( sudo mkdir pdi )
 	 Onde está o Data-integration (/home/pdi/data-integration)
  	E executando "sh spoon.sh"

#Postgresql

Instalação tranquila , onde utlizou-se alguns links 


        -sudo sh -c 'echo "deb https://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list' -
       - wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
     -  sudo apt-get update-
      -  sudo apt-get  install postgresql-16-
      -  Instalado postgresql-16 -
configurado  para ambiente de teste e conectando com sucesso 

*Criando banco e realizando o script*

		CREATE DATABASE banco1:
		CREATE DATABASE banco2;

--Restaurando o .dmp 

		psql -U xxxxxx -d banco1 -f /home/xxxx/backup.a.dmp
		psql -U xxxxxx -d banco2 -f /home/xxxx/backup.b.dmp
-- Banco restaurado 


*PDI - INTEGRAÇÃO*

	NEW TRANSFORMATION
 --PESQUISAR TABLE INPUT E OUTPUT
	selecionar para realizar a integração 
	NÓ do banco1(INPUT) para o banco2(OUTPUT)
*ajustar no Banco1*

localhost
banco1
port=5432
user=xxxx
senha=xxxx

*Realziar um get select*
		SELECT ano,mes,status,valortotal from "public.consumos_a

*ajustar no Banco2*

localhost
banco2
port=5432
user=xxxx
senha=xxxx

--Selecionar *target shema*= Public / *target table* = consumos_b

#####
Após teste o mesmo constatou erros de tabelas , onde não havia  "valortotal" em consumos_b
Testando novamente após estudo sobre , realizou-se um DROP nessa tabela para passar na validação 
____________________________________________________________________________________________




OBS : O e-mail para o teste ficou no spam após 4 dias de  mensagem sobre o desafio  , onde consegui visualizar sábado , pensava que estva fora poís fiquei dois dias(segunda e terça) na caixa de spam esperando  

$
