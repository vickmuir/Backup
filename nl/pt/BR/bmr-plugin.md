---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Instalando o plug-in de restauração bare metal

A BMR é uma solução de recuperação de desastre para o Microsoft Windows. É possível usar o BMR para restaurar seu servidor de um estado bare metal após a ocorrência de um desastre, como uma falha de sistema operacional ou de hardware.
Com a BMR, é possível restaurar rapidamente a imagem do sistema de uma localização segura e
protegida gerenciada pelo {{site.data.keyword.BluSoftlayer_full}}.

A BMR é um produto apenas para Microsoft Windows em servidores físicos. Ele
não está disponível para servidores virtuais. Distribuições de Bare Metal Restores para Linux não
são suportadas. A BMR é suportada apenas pelo Backup Agent 8.30 ou versões anteriores. (30 de junho de 2018).
{:important}

**Recursos fornecidos**

- Restaure seu sistema para um momento selecionado.
- Restaure seu sistema por meio de backups de imagem ou baseados em arquivo.
- Restaure seu sistema por meio de backups armazenados no IBM Cloud Backup.
- Uma transação de recuperação apta para ativação que pode ser usada para restaurar seus dados sem um sistema inicializável.
.
## Solicitando o plug-in

1. Efetue login no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} e clique no ícone **Menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.

   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Clique em **Armazenamento** > **Backup** para exibir os servidores com o serviço de backup.
3. Selecione a sua conta e clique em **Solicitar plug-ins**.
4. Selecione o **Plug-in do {{site.data.keyword.backup_notm}} - BMR (restauração bare-metal)** e clique em **Continuar**.
5. Insira seu Código promocional, se você tiver um, e clique em **Recalcular**.
6. Os encargos atualizados são exibidos. Revise seu pedido.
7. Marque a caixa para indicar que você leu e aceitou os Contratos de Prestação de Serviços de Terceiros.
8. Clique em **Fazer pedido**.

## Fazendo download do guia do usuário

Conecte-se à rede do {{site.data.keyword.BluSoftlayer_full}} com a {{site.data.keyword.BluVPN}} para que seja possível acessar e fazer download do guia do usuário por meio da [Documentação do {{site.data.keyword.backup_notm}} que pode ser transferida por download ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Perguntas Mais Frequentes

**Posso mover de um disco único para uma matriz RAID?**

Sim, isso funciona. No entanto, é necessário selecionar um dispositivo de grande capacidade devido à diminuição de tamanho causada pela matriz RAID.

**O que acontece quando a imagem é restaurada para um disco maior do que o volume original?**

Se você restaurar a imagem para um disco maior que o volume original, o espaço restante será
desalocado. Por exemplo, quando você tiver uma unidade de 500 GB e restaurar seus dados para um disco de 1 TB,
você ficará com 500 GB de espaço em disco desalocado. Com o Windows 2008, é possível usar o utilitário de disco integrado para aumentar a partição primária. No entanto, não há capacidade integrada semelhante no Windows 2003, portanto, deve-se alocar o espaço de outra maneira.

**O BMR pode ser usado para backup regular?**

O backup de BMR não é uma imagem de disco, mas um sistema de backup de imagem de volume do sistema. O sistema não se destina a ser usado para backups regulares, mas em conjunto com eles.  

**O BMR pode ser usado para Backups de Banco de Dados?**

Os backups de banco de dados devem ser feitos separadamente com os métodos de backup normais do IBM Cloud. O BMR não substitui a necessidade de plug-ins do SQL ou do Oracle. Embora o BMR use a tecnologia VSS para fazer backup de arquivos abertos, nem sempre é possível garantir que os arquivos de backup sejam consistentes com a transação. A recomendação para esses tipos de aplicativos especializados é que você crie duas tarefas de backup: uma para fazer backup dos arquivos binários do S.O. e do aplicativo e outra para dados do aplicativo. Há uma nota para esse efeito no final do guia do usuário do BMR.

**Quais tipos de tarefas de restauração podem ser executados com o BMR?**

É possível fazer uma restauração do sistema inteiro ou selecionar arquivos individuais do
backup para a restauração. A tarefa de backup de BMR pode substituir sua tarefa de backup de arquivos atual. O processo de restauração é feito dentro do S.O., exatamente como uma tarefa de backup tradicional.

**O BMR tem recursos de Backup de arquivo aberto?**

O BMR tem recursos de backup de arquivo aberto. No entanto, o BMR não substitui a necessidade de
plug-ins do SQL ou do Oracle. Para obter mais informações sobre o plug-in do MSSQL, clique [aqui](mssql-plugin.html).

**Que quantias de espaço em disco e de tempo são necessárias para uma restauração de BMR?**

Um backup feito por meio de uma instalação padrão usa aproximadamente 6 GB. Essa restauração leva cerca de 15
minutos em uma porta de 1 GB. Esse processo também é afetado pela velocidade da porta privada. Se você precisar de
backups e restaurações mais rápidos, poderá ser necessário um aumento de velocidade da porta.
