# Documentação do estudo de criação de servidores com Oracle Linux 9
Estes estudos tem como objetivo praticar a criação de servidores. O servidor que será o resultado destes estudos será utilizado para um futuro estudo de administração do banco de dados Oracle. Vale ressaltar que, as escolhas tomadas nem sempre serão as melhores corporativamente falando, mas sim para praticar todas as opções da melhor forma possível(isso será ressaltado também quando alguma escolha contraditória for tomada).
## Estabelecimento de uma VM
Para simular a criação de um servidor, uma máquina virtual foi criada. O aplicativo utilizado foi o Oracle VM VirtualBox.
- A imagem ISO para a instalação do sistema operacional foi baixada da Oracle eDelivery Cloud;
- Quase todas as configurações usadas foram as padrões, exeto por;
  - Rede: Aqui, o modo Bridge será utilizado, uma vez que todas as operações serão realizadas por meio de uma outra máquina, para simular todo o trabalho junto do servidor;
  - Capacidade de armazenamento: 50 GiB;
  - Núcleos de processamento: 4;
  - Memória RAM: 8 GiB.
## Instalação do sistema operacional Oracle Linux 9
