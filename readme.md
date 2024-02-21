# Documentação - Estudo sobre a Administração de Banco de Dados Oracle.
Este repositório foi criado com o intuito de documentar o estudo da criação do servidor Oracle Linux 8.6 responsável por hospedar um banco de dados e aplicar estudos sobre boas práticas na administração do mesmo, utilizando de ferramentas, métodos e padrões recomendados pela própria Oracle, ou por sua comunidade (Oracle Communities, Reddit, LinkedIn, etc.).
## Introdução
O objetivo principal deste estudo, é aplicar estudos direcionados ao banco de dados Oracle, junto dos conhecimentos adquiridos anteriormente de outros bancos do qual já trabalhei (PostgreSQL, MySQL e SQL Server). Além destes, o estabelecimento do servidor também será um estudo à parte, reforçando ainda mais o conhecimento da aplicação de banco de dados em OSs baseados em Linux (no caso, será utilizado o Oracle Linux 8.6 para a criação do servidor).
Uma prática que foi adotada durante todo o processo, é de nunca manipular o servidor diretamente por meio do mesmo, e sim com acessos externos, sendo um destes à partir do OS Ubuntu, utilizando apenas o terminal, visando reforçar o conhecimento sobre SSH, para conexões e suas configurações, SFTP para a transferência de arquivos, e qualquer outra ferramenta necessária, sem o uso de uma interface de apoio. Além deste, também será utilizado um OS Windows 11, com o objetivo de aprender mais sobre as funções do Putty e do MobaXTerm, tanto para a conexão ao servidor e a gestão dos usuários para o acesso, como também para a transferência de arquivo por meio dos mesmos.
Todas as boas práticas, e ferramentas de apoio serão abordadas de uma forma aprofundada no documento ["passo-a-passo.md"](https://github.com/oherikee/oracle_linux_9/blob/main/passo-a-passo.md).
> [!Important]
> Vale ressaltar que o objetivo principal do estudo é a adminsitração de banco de dados Oracle em um OS Linux. A criação do servidor para o DB também fará parte do estudo, porém, visando praticar o conhecimento de forma objetiva, o aprofundamento neste campo será realizado em outro momento (quando o estudo for realizado, uma documentação será feita para o mesmo, seu link será disponibilizado aqui).
## Ferramentas e Metodologias Utilizadas
Na escolha das ferramentas para a aplicação do estudo, sempre que possível a escolha foi feita dentre as disponibilizadas pela Oracle, visando praticar todo o conhecimento obtido através de artigos, documentações e cursos preparatórios:
- OS: Como sistema operacional foi escolhido o Oracle Linux 8;
- Metodologia de Arquitetura: Oracle Flexible Architecture (OFA);
- Gerenciamento de Recursos: Grid Infraestructure 21c;
- Banco de Dados: Oracle Database 19c.
