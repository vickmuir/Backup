---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud backup, EVault, Carbonite, backup, backup frequency, backup types, backup retention scheme, plugins, delta technology, open files, pricing

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:faq: data-hd-content-type='faq'}


# FAQ
{: #faqs}

## Pode-se fazer backup de que tipo de aplicativos?
{: faq}

O {{site.data.keyword.backup_full}} pode ser usado para fazer backup de vários aplicativos. O {{site.data.keyword.BluSoftlayer_full}} também oferece agentes de software para alguns dos sistemas de software mais comuns submetidos a backup, que incluem

- [Bare Metal Restore](/docs/infrastructure/Backup?topic=Backup-BMRplugin)
- [Microsoft Exchange](/docs/infrastructure/Backup?topic=Backup-Exchangeplugin)
- [Microsoft SQL](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin#MSSQLplugin)
- [Oracle](/docs/infrastructure/Backup?topic=Backup-Oracleplugin#Oracleplugin)
- [VMware VRA](/docs/infrastructure/Backup?topic=Backup-VRA#VRA)

Os plug-ins que estão listados aqui são compatíveis apenas com servidores Windows, exceto os plug-ins Oracle ou VMware. Cada agente está disponível como um complemento para seu serviço de backup gratuitamente.

<hr>

## Com que frequência podemos fazer backup dos dados?
{: faq}

No portal do {{site.data.keyword.backup_notm}}, os backups podem ser feitos manualmente, podem ser planejados como uma única instância ou podem ser recorrentes. Os backups recorrentes podem
ser feitos diariamente, semanalmente, mensalmente ou em uma programação customizada e podem ser atualizados ou
cancelados a qualquer momento.

Backups altamente frequentes que são executados várias vezes por dia ou por hora podem fazer com que as tarefas de
backup sejam corrompidas. Essa distorção ocorre porque a área segura de backup não tem tempo suficiente para executar as
tarefas de manutenção em segundo plano necessárias. As tarefas de backup têm precedência sobre as tarefas de
manutenção. Portanto, quando os backups são feitos com alta frequência, a área segura continua a executar as tarefas de backup e fazer com que os conjuntos de segurança cresçam.
{:note}

<hr>

## Como os esquemas de retenção funciona?
{: faq}

O {{site.data.keyword.backup_notm}} permite a retenção de dados, dependendo de quanto tempo você deseja
retroceder. Os esquemas de
retenção **Diariamente** retêm os dados por
sete dias, enquanto que os esquemas **Semanalmente** retêm os dados por um mês e
os esquemas **Mensalmente** retêm os dados por um ano. No término de cada período, o conjunto de dados mais antigo é rotacionado e o primeiro "backup delta" que foi feito se torna o ponto de restauração mais antigo disponível.

É possível modificar os esquemas de retenção padrão e criar esquemas de retenção customizados. No entanto, a IBM recomenda o uso das retenções padrão como um ponto de início. Ao criar um novo esquema de retenção ou modificar uma retenção existente, certifique-se de que a opção Arquivamento não esteja selecionada. O arquivamento não é
suportado.
{:tip}

<hr>

## O que é Tecnologia Delta?
{: faq}

O primeiro backup é um "valor inicial" (um backup completo) e o próximo backup e os subsequentes
são "deltas" (ou seja, somente mudanças), no entanto, eles são equivalentes a um
"backup completo" e ainda considerados como um. Ou seja, é possível restaurar todos ou quaisquer arquivos dele. Com essa tecnologia, "backups completos" são criados em cada sessão, mas economiza uma enorme quantia de espaço na área segura e diminui o período de tempo usado para a conclusão de cada backup subsequente.

<hr>

## Os backups são seguros?
{: faq}

Por padrão, toda a criptografia "over the wire" (OTW) é codificada com a criptografia AES de 256 bits. Também é possível optar por armazenar dados em formato
criptografado usando o AES de 256 bits.

Lembre-se de sua senha de criptografia. Seus dados não podem ser
restaurados sem sua senha. Se você a perder, não será possível obter seus dados de volta.
{:important}

As proporções de compactação permitem compactação zero até uma compactação de proporções máximas que,
dependendo do tipo de arquivo, pode atingir de 20 a 30 por cento.

<hr>

## Quais informações são armazenadas com backups de estado do sistema?
{: faq}

Os backups de estado do sistema incluem o banco de dados de registro de classe do COM +,
o registro, os arquivos de inicialização, os arquivos de sistema e o contador de desempenho, mas não se limitam a eles. Está tudo dependente de seu sistema. Arquivos de sistema variam por S.O. de sistema e service packs. Geralmente há milhares delas. O MS Windows fará uma lista dinâmica dessas DLLs quando você as incluir no backup. Ao incluir os arquivos de sistema, é possível fazer a recuperação de arquivos de sistema corrompidos ou no caso de remoção acidental de alguns pacotes de serviço ou se desejar recuperar-se com uma restauração bare metal. É possível retornar para o estado do backup sem precisar reinstalar o S.O. do kit de instalação e, em seguida, instalar cada pacote de serviços separadamente.

Nenhum arquivo de dados do usuário está incluído no backup de estado do sistema. Uma tarefa de backup de estado do sistema deve ser configurada como uma tarefa independente. Não deve haver nenhuma outra origem de dados incluída na tarefa de backup de estado do sistema
{:important}

<hr>

## O que acontece abrir arquivos?
{: faq}

Por padrão, o cliente de base tem uma tecnologia de última geração para manipular a maioria dos arquivos abertos que estão em execução no S.O.

<hr>

## Onde localizo as informações sobre precificação?
{: faq}

Para obter mais informações, consulte [Armazenamento de backup ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/cloud/backup-and-restore){:new_window} e [EVault no IBM Cloud: precificação ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/cloud/backup/pricing){:new_window}.

<hr>

## A capacidade do {{site.data.keyword.backup_notm}} pode ser aumentada ou diminuída sem comprometer os
backups?
{: faq}

É possível aumentar ou diminuir o tamanho de sua área segura por meio do [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}. A modificação da capacidade não afeta a integridade dos dados que estão armazenados na área segura. Para obter mais
informações, consulte [Expandindo a capacidade](/docs/infrastructure/Backup?topic=Backup-expandcapacity#expandcapacity).

<hr>

## O que acontece quando a capacidade do {{site.data.keyword.backup_notm}} é excedida?
{: faq}

Ainda é possível salvar e recuperar seus backups, mesmo que você tenha atingido o limite da capacidade que comprou anteriormente. No entanto, você receberá um encargo extra para cada GB adicional usado no próximo extrato de faturamento.

<hr>

## Como posso configurar notificações no portal do {{site.data.keyword.backup_notm}} que possam me alertar sobre a falha de um backup?
{: faq}

As notificações podem ser configuradas na guia Avançado. Siga as instruções que podem ser localizadas em **Links rápidos** no portal do {{site.data.keyword.backup_notm}}.

<hr>

## Ao usarmos o plug-in BMR, é possível passar de um único disco para uma matriz RAID?

Sim, isso funciona. No entanto, é necessário selecionar um dispositivo de grande capacidade devido à diminuição de tamanho causada pela matriz RAID.

<hr>

## Ao usarmos o plug-in BMR, o que acontece quando a imagem é restaurada para um disco maior do que o volume original?
{: faq}

Se você restaurar a imagem para um disco maior que o volume original, o espaço restante será
desalocado. Por exemplo, quando você tiver uma unidade de 500 GB e restaurar seus dados para um disco de 1 TB,
você ficará com 500 GB de espaço em disco desalocado. Com o Windows 2008, é possível usar o utilitário de disco integrado para aumentar a partição primária. No entanto, o Windows 2003 não tem um recurso integrado semelhante, portanto, deve-se alocar o espaço de outra maneira.

<hr>

## O BMR pode ser usado para backup regular?
{: faq}

O backup de BMR não é uma imagem de disco, mas um sistema de backup de imagem de volume do sistema. O sistema não se destina a ser usado para backups regulares, mas em conjunto com eles.  

<hr>

##A BMR pode ser usada para backups de banco de dados?
{: faq}

Os backups de banco de dados devem ser feitos separadamente com os métodos normais do {{site.data.keyword.backup_notm}}. O BMR não substitui a necessidade de plug-ins do SQL ou do Oracle. Embora o BMR use a tecnologia VSS para fazer backup de arquivos abertos, nem sempre é possível garantir que os arquivos de backup sejam consistentes com a transação. A recomendação para esses tipos de aplicativos especializados é que você crie duas tarefas de backup: uma para fazer backup dos arquivos binários do S.O. e do aplicativo e outra para dados do aplicativo.

<hr>

## Que tipo de tarefas de restauração podem ser executadas com o BMR?

É possível fazer uma restauração do sistema inteiro ou selecionar arquivos individuais do
backup para a restauração. A tarefa de backup de BMR pode substituir sua tarefa de backup de arquivos atual. O processo de restauração é feito dentro do S.O., exatamente como uma tarefa de backup tradicional.

<hr>

## O BMR tem recursos de backup de arquivo aberto?
{: faq}

O BMR tem recursos de backup de arquivo aberto. No entanto, o BMR não substitui a necessidade de
plug-ins do SQL ou do Oracle. Clique [aqui](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin) para obter as
instruções de instalação do plug-in do MSSQL.

<hr>

## Que quantias de espaço em disco e de tempo são necessárias para uma restauração de BMR?
{: faq}

Um backup feito por meio de uma instalação padrão usa aproximadamente 6 GB. Essa restauração leva cerca de 15
minutos em uma porta de 1 GB. Esse processo também é afetado pela velocidade da porta privada. Se você precisar de backups e restauração mais rápidos, um aumento na velocidade da porta poderá ser necessário.

<hr>

## O que o VSS (Serviço de Cópia de Sombra de Volume) faz?
{: faq}

A versão atual do plug-in SQL Server usa o VSS (Serviço de Cópia de Sombra de Volume) para concluir os backups. Usando o VSS, o plug-in SQL Server faz efetivamente o backup dos bancos de dados SQL, mesmo os bancos de dados SQL que estendem volumes. Os backups podem ser concluídos enquanto os aplicativos continuam a gravar em um volume. O plug-in SQL Server fornece consistência de dados dentro e entre bancos de dados. O VSS permite que múltiplos backups sejam executados ao mesmo tempo.

<hr>

## A versão de 32 bits do EVault para Windows 8 ainda é suportada?
{: faq}

Não. A versão de 32 bits do agente de software de backup foi desativada junto com o Windows Server 2008 Standard e Datacenter Editions em março de 2017.
