---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# Instalando o plug-in EVault Bare Metal Restore

O EVault BMR é uma solução de recuperação de desastre para o Microsoft Windows. É possível usar o BMR para restaurar seu servidor de um estado bare metal após a ocorrência de um desastre, como uma falha de sistema operacional ou de hardware. Com o EVault BMR, é possível restaurar rapidamente a imagem do sistema de um local seguro gerenciado pelo {{site.data.keyword.BluSoftlayer_full}}.

**Nota**: o BMR é um produto do Microsoft Windows somente em servidores físicos. Ele
não está disponível para servidores virtuais. Distribuições de Bare Metal Restores para Linux não
são suportadas. O BMR é suportado somente pelo EVault Agent 8.30 ou versões anteriores. (30 de junho de 2018).

**Recursos fornecidos**

- Restaure seu sistema para um momento selecionado.
- Restaure seu sistema por meio de backups de imagem ou baseados em arquivo.
- Restaure seu sistema por meio de backups que estão armazenados no EVault.
- Uma transação de recuperação apta para ativação que pode ser usada para restaurar seus dados sem um sistema inicializável.

## Solicitando o plug-in

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Clique em **Armazenamento** > **Backup**.
3. Selecione sua conta do EVault e clique em **Pedir plug-ins**.
4. Selecione **Plug-in do EVault - BMR (Bare Metal Restore)** e clique em **Continuar**.
5. Insira seu Código promocional, se você tiver um, e clique em **Recalcular**.
6. Os encargos atualizados são exibidos. Revise seu pedido.
7. Marque a caixa para indicar que você leu e aceitou os Contratos de Prestação de Serviços de Terceiros. 
8. Clique em **Fazer pedido**.

## Fazendo download do guia do usuário

Conecte-se à rede do {{site.data.keyword.BluSoftlayer_full}} com o {{site.data.keyword.BluVPN}} para que seja possível fazer download
do EVault System Restore v8.3 - Guia do Usuário.pdf por meio da [Documentação do
EVault transferível por download](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Perguntas Mais Frequentes

**Posso mover de um disco único para uma matriz RAID?**

Sim, isso funciona. No entanto, é necessário selecionar um dispositivo de grande capacidade devido à diminuição de tamanho causada pela matriz RAID.

**O que acontece quando a imagem é restaurada para um disco maior do que o volume original?**

Se você restaurar a imagem para um disco maior que o volume original, o espaço restante será
desalocado. Por exemplo, quando você tem uma unidade de 500 GB e restaura os dados para um disco de 1 TB, você acaba com 500 GB de espaço em disco desalocado. Com o Windows 2008, é possível usar o utilitário de disco integrado para aumentar a partição primária. No entanto, não há capacidade integrada semelhante no Windows 2003, portanto, deve-se alocar o espaço de outra maneira.

**O BMR pode ser usado para backup regular?**

O backup de BMR não é uma imagem de disco, mas um sistema de backup de imagem de volume do sistema. O sistema não se destina a ser usado para backups regulares, mas em conjunto com eles.  

**O BMR pode ser usado para Backups de Banco de Dados?**

Os backups de banco de dados devem ser feitos separadamente com os métodos normais de backup do EVault. O BMR não substitui a necessidade de plug-ins do SQL ou do Oracle. Embora o BMR use a tecnologia VSS para fazer backup de arquivos abertos, nem sempre é possível garantir que os arquivos de backup sejam consistentes com a transação. A recomendação para esses tipos de aplicativos especializados é que você crie duas tarefas de backup: uma para fazer backup dos arquivos binários do S.O. e do aplicativo e outra para dados do aplicativo. Há uma nota para esse efeito no final do guia do usuário do BMR.

**Quais tipos de tarefas de restauração podem ser executados com o BMR?**

É possível fazer uma restauração do sistema inteiro ou selecionar arquivos individuais do
backup para a restauração. A tarefa de backup de BMR pode substituir sua tarefa de backup de arquivos atual. O processo de restauração é feito dentro do S.O., exatamente como uma tarefa de backup tradicional.

**O BMR tem recursos de Backup de arquivo aberto?**

O BMR tem recursos de backup de arquivo aberto. No entanto, o BMR não substitui a necessidade de
plug-ins do SQL ou do Oracle. Clique [aqui](evault-mssql-plugin.html) para obter as
instruções de instalação do plug-in do MSSQL.

**Que quantias de espaço em disco e de tempo são necessárias para uma restauração de BMR?**

Um backup feito por meio de uma instalação padrão usa aproximadamente 6 GB. Essa restauração dura cerca de 15 minutos em uma porta de 1 GB. Esse processo também é afetado pela velocidade da porta privada. Se você precisar de backups/restaurações mais rápidos, poderá ser necessário um aumento da velocidade da porta.
