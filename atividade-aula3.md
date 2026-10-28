Relatório da aula 03

1. Identificação
A prática teve como conteúdo interfaces e endereçamento de rede no Ubuntu Server 26.04, utilizando o VirtualBox para configurar e testar a conexão de rede da máquina virtual.

2. Objetivo
O objetivo da aula foi aprender a identificar endereços IP, máscaras de sub-rede, endereços MAC, gateway e DNS, além de testar a conectividade e entender a diferença entre os modos NAT e Bridge.

3. Ambiente utilizado
Foi utilizado um computador com Windows, o VirtualBox e uma máquina virtual com Ubuntu Server 26.04. Foram estudados os modos de rede NAT e Placa em Ponte (Bridge).

4. Procedimentos realizados
Foram utilizados os comandos ip addr show, ip link e ip route para verificar as interfaces de rede, os endereços IP, os endereços MAC e as rotas configuradas.
Também foram realizados testes de conectividade com o comando ping, utilizando endereços locais, o gateway, um endereço IP externo e um nome de domínio. Foi utilizado o traceroute para observar o caminho percorrido pelos pacotes na rede.
Depois, foi apresentada a configuração de rede em modo Bridge no VirtualBox, permitindo comparar esse modo com o NAT e, por fim, foi utilizado o comando ipconfig /all no Windows para consultar as informações de rede do computador físico.

5. Testes e resultados
Os testes tiveram como finalidade verificar a comunicação da máquina virtual com a rede local e com a internet.

No modo NAT, a máquina virtual utiliza uma rede gerenciada pelo VirtualBox. No modo Bridge, a máquina virtual recebeu um endereço IP da mesma rede do computador físico, facilitando o acesso a partir de outros dispositivos.

6. Conclusão
A aula permitiu conhecer melhor as interfaces de rede do Linux e compreender a função dos endereços IP, MAC, gateway e DNS. Também foi possível estudar as diferenças entre NAT e Bridge e entender como os comandos ping e traceroute ajudam a verificar e diagnosticar problemas de conectividade.
