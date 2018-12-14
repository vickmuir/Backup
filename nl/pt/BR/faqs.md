---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:faq: data-hd-content-type='faq'}


# FAQ

## Pode-se fazer backup de que tipo de aplicativos?
{: faq}

O {{site.data.keyword.backup_full}} pode ser usado para fazer backup de vários aplicativos. No entanto,
o {{site.data.keyword.BluSoftlayer_full}} oferece agentes de software para alguns dos sistemas de
software mais comuns que são submetidos a backup, que incluem:

- Bare Metal Restore
- Microsoft Exchange
- Microsoft SQL
- Oracle

Os plug-ins listados aqui são compatíveis apenas com servidores Windows, com exceção do plug-in do Oracle. Cada
agente está disponível como um complemento para o serviço de backup. Para incluir um agente em seu serviço, entre em contato com um membro da equipe de Vendas hoje.

<hr>

## Com que frequência os dados podem ser submetidos a backup?
{: faq}

No WebCC, os backups podem ser feitos manualmente ou podem ser planejados como uma única instância ou como recorrentes. Os backups recorrentes podem
ser feitos diariamente, semanalmente, mensalmente ou em uma programação customizada e podem ser atualizados ou
cancelados a qualquer momento.

Backups altamente frequentes que são executados várias vezes por dia ou por hora podem fazer com que as tarefas de
backup sejam corrompidas. Essa distorção ocorre porque a área segura de backup não tem tempo suficiente para executar as
tarefas de manutenção em segundo plano necessárias. As tarefas de backup têm precedência sobre as tarefas de
manutenção. Portanto, em caso de backups altamente frequentes, a área segura continua executando as tarefas de backup e
aumenta o número de conjuntos de segurança.
{:note}

<hr>

## Como os esquemas de retenção funciona?
{: faq}

O {{site.data.keyword.backup_notm}} permite a retenção de dados, dependendo de quanto tempo você deseja
retroceder. Os esquemas de
retenção **Diariamente** retêm os dados por
sete dias, enquanto que os esquemas **Semanalmente** retêm os dados por um mês e
os esquemas **Mensalmente** retêm os dados por um ano. No término de cada período, o conjunto de dados mais antigo é rotacionado e o primeiro "backup delta" que foi feito se torna o ponto de restauração mais antigo disponível.

É possível modificar os esquemas de retenção padrão e criar esquemas de retenção customizados. No entanto, é
altamente recomendável usar as retenções padrão como um ponto de início. Ao criar um novo esquema de retenção ou
modificar uma retenção existente, certifique-se de que a opção Arquivamento esteja desmarcada. O arquivamento não é
suportado.
{:tip}

<hr>

## O que é Tecnologia Delta?
{: faq}

O primeiro backup é um "valor inicial" (um backup completo) e o próximo backup e os subsequentes
são "deltas" (ou seja, somente mudanças), no entanto, eles são equivalentes a um
"backup completo" e ainda considerados como um. Ou seja, é possível restaurar todos ou quaisquer arquivos dele. Essa tecnologia permite que
"backups completos" sejam feitos em cada sessão, economizando, no entanto, enormes quantidades de espaço na
Área segura e diminuindo a quantia de tempo que cada backup subsequente leva para ser concluído.

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
o registro, os arquivos de inicialização, os arquivos de sistema e o contador de desempenho, mas não se limitam a eles. Está tudo dependente de seu sistema. Arquivos de sistema variam por S.O. de sistema e service packs. Geralmente há milhares delas. O MS Windows fará uma lista dinâmica dessas DLLs quando você as incluir no backup. Ao incluir os arquivos do sistema, é possível fazer a recuperação no caso de arquivos de sistema corrompidos, de pacotes de serviço desinstalados acidentalmente ou se recuperar usando uma restauração bare metal. É possível retornar para o estado do backup sem precisar reinstalar o S.O. do kit de instalação e, em seguida, instalar cada pacote de serviços separadamente.

Nenhum arquivo de dados do usuário está incluído no backup de estado do sistema. Uma tarefa de backup de estado do sistema deve ser configurada como uma tarefa independente.
Não deve haver nenhuma outra origem de dados incluída na tarefa de backup de estado do sistema
{:important}

<hr>

## O que acontece abrir arquivos?
{: faq}

Por padrão, o cliente de base tem uma tecnologia de última geração para manipular a maioria dos arquivos abertos que estão em execução no S.O.

<hr>

## Onde localizo as informações sobre precificação?
{: faq}

Para obter mais informações, consulte
[Armazenamento de backup](https://www.ibm.com/cloud/backup-and-restore){:new_window} e
[{{site.data.keyword.backup_notm}} no IBM Cloud: precificação](https://www.ibm.com/cloud/evault/pricing){:new_window}.

<hr>

## A capacidade do {{site.data.keyword.backup_notm}} pode ser aumentada ou diminuída sem comprometer os
backups?
{: faq}

É possível aumentar ou diminuir o tamanho da área segura por meio do [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
A modificação da capacidade não afeta a integridade dos dados que estão armazenados na área segura. Para obter mais
informações, consulte [Expandindo a capacidade](expanding-capacity.html).

<hr>

## O que acontece quando a capacidade do {{site.data.keyword.backup_notm}} é excedida?
{: faq}

Ainda é possível salvar e recuperar seus backups, mesmo que você tenha atingido o limite da capacidade que comprou anteriormente. No entanto, observe que vai haver um encargo extra para cada GB adicional usado na instrução de faturamento.

<hr>

## Como posso configurar as notificações no WebCC para saber se meus backups falham?
{: faq}

As notificações podem ser configuradas na guia Avançado. Siga as instruções que podem ser localizadas em **Links Rápidos**, no WebCC.
