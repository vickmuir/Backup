---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# Instalando o plug-in EVault Oracle

O plug-in do Oracle é instalado com o Windows Agent no host do banco de dados Oracle. Pelo portal do WebCC é possível configurar tarefas, fazer backup de banco de dados Oracle para uma área segura remota e restaurar banco de dados Oracle. 
O plug-in do Oracle se integra à arquitetura existente.

## Recursos fornecidos

- Suporte para backup e recuperação de banco de dados Oracle.
- O plug-in do Oracle fornece backups não RMAN e baseados em ARCHIVELOG de
instâncias de banco de dados on-line inteiras. Todos os espaços de tabela e arquivos de parâmetros da instância
não provisórios são submetidos a backup automaticamente. A Oracle Corporation recomenda que os backups ocorram
em períodos de baixa atividade do banco de dados.
- Os bancos de dados completos e parciais são restaurados por meio de mecanismos de recuperação
normais do Oracle gerenciados pelo usuário.

## Solicite o plug-in

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Clique em **Storage** > **Backup**.
3. Selecione a sua conta do EVault e clique em **Pedir plug-ins**.
4. Selecione **Plug-in do EVault - Oracle** e clique em
**Continuar**.
5. Insira o seu Código promocional se você tiver um e clique em **Recalcular**.
6. Os encargos atualizados são exibidos. Revise seu pedido.
7. Marque as caixas para indicar que você leu o Contrato de Prestação de Serviços Principal e aceite os Termos de Software de Terceiro. 
8. Clique em **Fazer pedido**.

## Instale o plug-in do Oracle

O plug-in do Oracle para Windows é instalado com o Windows Agent de 32 ou 64 bits.
Para instalar o plug-in do Oracle para Windows, execute o kit de instalação do agente. O plug-in do Oracle
aparece como uma opção na página **Configuração customizada**.

**Nota**: antes de instalar o plug-in para o seu servidor Microsoft Windows, pare ambos os serviços EVault em `services.msc`.  

1. Navegue para a pasta `c:\installs\evault` e execute o arquivo .exe com o número de
revisão maior.
2. Na tela de linguagem clique em **OK**
3. Na tela de boas-vindas, clique em **Avançar**
4. Selecione **Modificar instalação** e clique em **Avançar**.
5. Selecione **Manter inalterado** e clique em **Avançar**.
6. Na tela de configuração customizada, selecione cada plug-in que você comprou e selecione **Esse recurso será instalado em...** e, em seguida, clique em **Avançar**.
7. Selecione o botão de opções **Manter o meu registro atual** e clique em **Avançar**.
8. Clique em **Instalar**.
9. Após instalado, verifique se ambos os serviços estão ativados e em execução.
10. Se o WebCC for capaz de acessar (visualizar) os bancos de dados, então a instalação foi bem-sucedida. 

## Guia do Usuário

Conecte-se à rede do {{site.data.keyword.BluSoftlayer_full}} com
o {{site.data.keyword.BluVPN}} para que seja possível fazer download do EVault Agent v8.0 for Microsoft
Windows - Oracle Plug Guide.pdf por meio da
[Documentação do EVault
transferível por download](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Perguntas Mais Frequentes

### Quais são as limitações do plug-in do Oracle?
- Somente bancos de dados locais de instância única e baseados em disco são submetidos a backup.
- Clusters de Banco de Dados não são submetidos a backup.
- Dispositivos brutos não são submetidos a backup.
- Bancos de dados remotos não são submetidos a backup.
- O banco de dados deve ser executado no modo ARCHIVELOG e o usuário sob o qual o backup está
configurado deve ter privilégios SYSDBA.
- As senhas do banco de dados são criptografadas para melhor segurança sobre os métodos baseados em
script.
