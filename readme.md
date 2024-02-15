# Documentação Oracle Linux 8 para um DB Oracle
Este repositório foi criado com o intuito de hospedar um banco de dados, e aplicar estudos sobre boas práticas utilizando de ferramentas recomendadas pela própria Oracle, ou por sua comunidade (Oracle Communities, Reddit, LinkedIn, etc.).
## Introdução
O objetivo principal deste estudo, é aplicar estudos direcionados ao banco de dados Oracle, junto de aplicar conhecimentos posteriores de outros bancos do qual já trabalhei (PostgreSQL, MySQL e SQL Server). Além destes, o estabelecimento do servidor também será um estudo aparte, reforçando ainda mais o conhecimento da aplicação de banco de dados em OSs baseados em Linux (no caso, será utiliado o Oracle Linux 8.6 para a criação do servidor).
Uma prática que foi adotada durante todo o processo, é de nunca manipular o servidor por meio do mesmo, e sim com acessos externos, sendo um destes à partir do OS Ubuntu, utilizando apenas o terminal, visando reforçar o conhecimento sobre SSH, para conexões e suas configurações, SFTP para a trasnferência de arquivos, e qualquer outra ferramenta necessária, sem o uso de uma interface de apoio. Além deste, também será utilizado um OS Windows 11, com o objetivo de aprender mais sobre as funções do Putty e do MobaXTerm, tanto para a conexão ao servidor e a gestão dos usuários para o acesso, como também para a transferência de arquivo por meio dos mesmos.
Todas as boas práticas, e ferramentas de apoio serão abordadas de uma forma aprofundada no documento ["passo-a-passo.md"](https://github.com/oherikee/oracle_linux_9/blob/main/passo-a-passo.md), onde os meios serão explicados junto de seus motivos.
> [!Important]
> Vale ressaltar que o objetivo principal do estudo é a adminsitração de banco de dados Oracle em um OS Linux. A criação do servidor e todo o resto também é muito importante, mas serão estudadas em outro momento com o foco nestes pontos (quando o estudo for realizado, uma documentação será feita para o mesmo, seu link será disponibilizado aqui).
