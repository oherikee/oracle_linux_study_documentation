# Documentação do estudo de criação de servidores com Oracle Linux 9
Estes estudos tem como objetivo praticar a criação de servidores. O servidor que será o resultado destes estudos será utilizado para um futuro estudo de administração do banco de dados Oracle. Vale ressaltar que, as escolhas tomadas nem sempre serão as melhores corporativamente falando, mas sim para praticar todas as opções da melhor forma possível (isso será ressaltado também quando alguma escolha contraditória for tomada).
## Estabelecimento de uma VM
Para simular a criação de um servidor, uma máquina virtual foi criada. O aplicativo utilizado foi o Oracle VM VirtualBox.
- A imagem ISO para a instalação do sistema operacional foi baixada da Oracle eDelivery Cloud;
- Quase todas as configurações usadas foram as padrões, exeto por;
  - Rede: Aqui, o modo Bridge será utilizado, uma vez que todas as operações serão realizadas por meio de uma outra máquina, para simular todo o trabalho junto do servidor;
  - Capacidade de armazenamento: 50 GiB;
  - Núcleos de processamento: 4;
  - Memória RAM: 8 GiB.
## Instalação do sistema operacional Oracle Linux 9
A maioria das opções serão as padrões, exceto por alguns:
- Partições do disco:
  - 10 GiB serão dedicados para SWAP;
  - 1 GiB será dedicada para o Boot;
  - 39 GiB serão dedicados para o armazenamento em si ("/"). Como é apenas para estudo, tudo será salvo em uma única partição.
- Sistema:
  - Das ferramentas adicionais disponibilizadas para a instalação, apenas três são pertinentes, sendo elas:
    - Ferramentas de sistema, uma vez que precisamos de ferramentas gerais para a gestão e configuraçaõ dos sistemas;
    - Ferramentas de desenvolvimento, é o básico para o ambiente;
    - Ferramentas de desempenho, para realizar diagnósticos de performance de sistemas, facilitar troubleshooting, etc.
- Demais configurações:
  - As demais configurações foram mantidas nas opções padrões.
## Configuração do servidor
### Configuração de permissões de acesso ao servidor
Primeiramente, foi necessário configurar o login root para permitir o acesso por meio de uma máquina externa (lembrando, isso é apenas para estudo, em uma situação corporativa, o usuário root não seria liberado para um acesso externo ao servidor):
- Primeiramente, foi necessário conferir se o "openssh-server" está presente no sistema (utilizando o comando "dnf list installed | grep ssh"), no caso, não estava;
- Foi realizada a instalação do "openssh-server";
- Então, se fez necessário editar o arquivo "/etc/ssh/sshd.config" (no caso, o comando utilizado foi o "nano", mas o "vi" também funciona normalmente). As linhas editadas foram:
  - PermitRootLogin: valor alterado para "yes";
  - PasswordAuthentication: valor alterado para "yes".
- Com essas alterações, o login por meio de uma máquina externa já é possível. Para o estudo, duas máquinas serão utilizadas, uma com o sistema operacional Linux Ubuntu, e outro com Windows 11:
  - No caso do Linux, o acesso foi feito diretamente pelo terminal com o comando "ssh [user]@[IP do servidor] -p [Porta do servidor]";
  - No caso do Windows 11, o MobaXTerm foi usado (tendo Putty como uma segunda opção).
### Configuração do Grid Infraesctructure 21c
Para o Grid, quatro discos serão criados, cada um com 5 GiB de armazenamento. Como o aplicativo utilizado para a configuração da VM é o VirtualBox, então três discos VDI(Imagem virtual). Então, foi realizada a partição dos discos utilizando o comando "fdisk". Abaixo, as opções tomadas no formulário do fdisk:
- O tipo de partição selecionado foi o primário;
- O numero da partição, e os setores foram utilizados os valores padrões, uma vez que o disco inteiro será usado para a partição.
### Configuração do SELinux
No documento "/etc/selinux/config", a linha "SELINUX" teve seu valor alterado para "PERMISSIVE".
### Configuração dos hosts
No documento "/etc/hosts", foi adicionada a linha contendo o IP da VM que usaremos para servidor, e o nome do mesmo. Para testar se as configurações estão de acordo, o ip foi pingado, e retornou sucesso.
### Configuração dos pacotes de Kernel
Para facilitar a configuração, e como o objetivo do servidor (além de aplicar o aprendizado) é de hospedar um banco de dados Oracle para estudo, utilizaremos o pacote "oracle_database_preinstall_19c", e para o ambiente gráfico o "tigervnc", "xterm" e o "xorg".
