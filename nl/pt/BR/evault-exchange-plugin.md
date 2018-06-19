---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# Instalando o plug-in EVault Exchange

O plug-in do Exchange é instalado com o Windows Agent no host. Pelo portal do WebCC é possível configurar tarefas, fazer backup de banco de dados Oracle para uma área segura remota e restaurar banco de dados Oracle. 
O plug-in do Oracle se integra à arquitetura existente.

## Recursos fornecidos

- Capacidade para fazer backup e restaurar bancos de dados do Microsoft Exchange.

## Solicite o plug-in

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Clique em **Storage** > **Backup**.
3. Selecione a sua conta do EVault e clique em **Pedir plug-ins**.
4. Selecione **Plug-in do EVault - Exchange** e clique em
**Continuar**.
5. Insira o seu Código promocional se você tiver um e clique em **Recalcular**.
6. Os encargos atualizados são exibidos. Revise seu pedido.
7. Marque as caixas para indicar que você leu o Contrato de Prestação de Serviços Principal e aceite os Termos de Software de Terceiro. 
8. Clique em **Fazer pedido**.

## Instale o plug-in Exchange

O plug-in do Exchange é instalado durante a instalação do Windows Agent de 64 bits. O plug-in pode ser
instalado durante a instalação do agente ou pode ser instalado posteriormente executando novamente a instalação
com a seleção Modificar.

**Nota**: antes de instalar o plug-in para o seu servidor Microsoft Windows, pare ambos os serviços EVault em `services.msc`.  

1. Navegue para a pasta `c:\installs\evault` e execute o arquivo .exe com o
número de revisão maior.
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
o {{site.data.keyword.BluVPN}} para que seja possível fazer download do EVault Agent v8.0 para
o Microsoft Windows (64 bits) - Exchange Plug-Guide.pdf por meio da
[Documentação do EVault
transferível por download](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}. Este guia descreve como fazer backup e restaurar bancos de
dados do Microsoft Exchange utilizando o plug-in do Exchange. Este guia também descreve como compartilhar um
conjunto de segurança de backup do DR para que seja possível restaurar caixas de correio, mensagens ou
outros objetos específicos para um arquivo .pst utilizando o aplicativo Granular Restore for
Microsoft Exchange.


