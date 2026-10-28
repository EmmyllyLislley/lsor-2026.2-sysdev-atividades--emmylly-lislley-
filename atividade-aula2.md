Caderno de respostas aula 02

1. Criação dos usuários
Comandos utilizados para criar os quatro usuários:
sudo adduser fulano
sudo adduser cicrano
sudo adduser beltrano
sudo adduser novato

Para verificar os usuários criados:
tail -n 4 /etc/passwd

Os usuários fulano, cicrano, beltrano e novato devem aparecer no arquivo de usuários do sistema.


2. Criação do grupo devs
Criar o grupo:
sudo groupadd devs

Adicionar os usuários ao grupo:
sudo usermod -aG devs fulano
sudo usermod -aG devs cicrano
sudo usermod -aG devs beltrano

Verificar os membros:
grep '^devs:' /etc/group

Fulano, cicrano e beltrano pertencem ao grupo devs. O usuário novato não pertence a esse grupo.


3. Criação do diretório compartilhado
Criar a pasta do projeto:
sudo mkdir -p /srv/projeto

Verificar as permissões iniciais:
ls -ld /srv/projeto

Inicialmente, a pasta pertence ao usuário root e ao grupo root.


4. Alteração do dono e do grupo
Executar os comandos:
sudo chown administrador /srv/projeto
sudo chgrp devs /srv/projeto

Verificar:
ls -ld /srv/projeto

O dono será administrador e o grupo associado será devs.


5. Configuração das permissões
Aplicar a permissão 770:
sudo chmod 770 /srv/projeto

Verificar:
ls -ld /srv/projeto

Resposta esperada:
drwxrwx--- administrador devs /srv/projeto
O dono e os membros do grupo podem ler, escrever e acessar o diretório. Os demais usuários não possuem permissões de acesso.


6. Criação e configuração do arquivo
Criar o arquivo:
echo "Especificacao tecnica do roteador de borda" | sudo tee /srv/projeto/config_redes.txt

Definir o dono e o grupo:
sudo chown administrador:devs /srv/projeto/config_redes.txt

Aplicar as permissões:
sudo chmod 660 /srv/projeto/config_redes.txt

Verificar:
ls -l /srv/projeto/config_redes.txt

O dono e os membros do grupo devs podem ler e modificar o arquivo. Os demais usuários não possuem acesso.


7. Teste com o usuário fulano
Alternar para o usuário:
su - fulano

Acessar o diretório:
cd /srv/projeto
ls -l

Adicionar um comentário ao arquivo:
echo "Revisado por Fulano" >> config_redes.txt
cat config_redes.txt

O usuário fulano consegue acessar o diretório e modificar o arquivo porque pertence ao grupo devs.

Retornar ao administrador:
exit


8. Teste com o usuário novato
Alternar para o usuário:
su - novato

Tentar acessar o diretório:
cd /srv/projeto

Tentar listar os arquivos:
ls -l /srv/projeto

O sistema apresenta a mensagem Permission denied, pois o usuário novato não pertence ao grupo devs e não possui permissões para acessar o diretório.

Retornar ao administrador:
exit


9. Exercício de fixação: grupo financeiro
a) Criar o grupo financeiro:
sudo groupadd financeiro

b) Adicionar cicrano e beltrano ao grupo:
sudo usermod -aG financeiro cicrano
sudo usermod -aG financeiro beltrano

c) Criar o diretório financeiro:
sudo mkdir -p /srv/financeiro

d) Definir o dono e o grupo:
sudo chown administrador:financeiro /srv/financeiro

e) Configurar as permissões:
sudo chmod 770 /srv/financeiro

f) Criar um arquivo de teste:
sudo touch /srv/financeiro/relatorio.txt
sudo chown administrador:financeiro /srv/financeiro/relatorio.txt
sudo chmod 660 /srv/financeiro/relatorio.txt

g) Testar o acesso: o usuário cicrano deve conseguir acessar o diretório e modificar o relatório, enquanto fulano e novato devem receber Permission denied.


10. Conclusão
Nesta aula, foram estudados os comandos de criação de usuários e grupos, alteração de proprietário e grupo de arquivos e configuração de permissões no Linux. Os testes demonstram como as permissões ajudam a controlar o acesso aos diretórios e arquivos, garantindo que somente os usuários autorizados possam consultar ou modificar informações.
