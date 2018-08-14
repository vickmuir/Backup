---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-10"

---
{:new_window: target="_blank"}


# Backup do EVault - Perguntas mais frequentes

**Quais tipos de aplicativos podem ser submetidos a backup com o EVault?**

O EVault pode ser usado para fazer backup de vários aplicativos. No entanto,
o {{site.data.keyword.BluSoftlayer_full}} oferece agentes de software para alguns dos sistemas de
software mais comuns que são submetidos a backup, que incluem:

- Bare Metal Restore
- Microsoft SQL
- Oracle

Os plug-ins que estão listados aqui são compatíveis apenas com servidores Windows. Cada agente está disponível como um complemento para o seu serviço EVault Backup. Para incluir um agente em seu serviço, entre em contato com um membro da equipe de Vendas hoje. 

<hr>

**Com que frequência os dados podem ser submetidos a backup com o EVault?**

É possível fazer backup dos dados com a frequência que desejar. No WebCC, os backups podem ser feitos
manualmente ou podem ser planejados como uma única instância ou para serem recorrentes. Os backups recorrentes podem
ser feitos diariamente, semanalmente, mensalmente ou em uma programação customizada e podem ser atualizados ou
cancelados a qualquer momento.

>**Nota**: backups altamente frequentes que são executados várias vezes por dia ou por hora podem fazer com que as tarefas de backup se tornem corrompidas. Essa distorção ocorre porque a área segura pode não ser capaz de remover os conjuntos de segurança antigos ou de concluir outras tarefas em segundo plano necessárias entre as execuções.

<hr>

**Como os esquemas de retenção funciona?**

O EVault permite a retenção de dados, dependendo de até quanto tempo você deseja recuperá-los. Os esquemas de
retenção **Diariamente** retêm os dados por
sete dias, enquanto que os esquemas **Semanalmente** retêm os dados por um mês e
os esquemas **Mensalmente** retêm os dados por um ano. No término de cada período, o conjunto de dados mais antigo é rotacionado e o primeiro "backup delta" que foi feito se torna o ponto de restauração mais antigo disponível. 

<hr>

**O que é Tecnologia Delta?**

O primeiro backup é um "valor inicial" (um backup completo) e o próximo backup e os subsequentes
são "deltas" (ou seja, somente mudanças), no entanto, eles são equivalentes a um
"backup completo" e ainda considerados como um. Ou seja, é possível restaurar todos ou quaisquer arquivos dele. Essa tecnologia permite que
"backups completos" sejam feitos em cada sessão, economizando, no entanto, enormes quantidades de espaço na
Área segura e diminuindo a quantia de tempo que cada backup subsequente leva para ser concluído.

<hr>

** Os Backups são seguros? **

Por padrão, toda a criptografia "over the wire" (OTW) é codificada com a criptografia AES de 256 bits. Também é possível optar por armazenar dados em formato
criptografado usando o AES de 256 bits. 

>**Nota**: lembre-se de sua senha de criptografia. Seus dados não podem ser
restaurados sem sua senha. Se você a perder, não será possível obter seus dados de volta. 

As proporções de compactação permitem compactação zero até uma compactação de proporções máximas que,
dependendo do tipo de arquivo, pode atingir de 20 a 30 por cento.

<hr>

**Quais informações são armazenadas com os Backups de estado do sistema?**

Os backups de estado do sistema incluem o banco de dados de registro de classe do COM +,
o registro, os arquivos de inicialização, os arquivos de sistema e o contador de desempenho, mas não se limitam a eles. Está tudo dependente de seu sistema. Arquivos de sistema variam por S.O. de sistema e service packs. Geralmente há milhares delas. O MS Windows fará uma lista dinâmica dessas DLLs quando você as incluir no backup. Ao incluir os arquivos do sistema, é possível fazer a recuperação no caso de arquivos de sistema corrompidos, de pacotes de serviço desinstalados acidentalmente ou se recuperar usando uma restauração bare metal. É possível retornar para o estado do backup sem precisar reinstalar o S.O. do kit de instalação e, em seguida, instalar cada pacote de serviços separadamente.

>**Nota**: nenhum arquivo de dados do usuário é incluído no backup de estado do Sistema. Uma tarefa de backup de estado do sistema deve ser configurada como uma tarefa independente. Não deve haver nenhuma outra origem de dados que esteja incluída na tarefa de backup de Estado do Sistema.

<hr>

**O que acontece ao abrir arquivos?**

Por padrão, o cliente de base tem uma tecnologia de última geração para manipular a maioria dos arquivos abertos que estão em execução no S.O.

<hr>

**Onde posso encontrar informações sobre precificação?**

Para obter mais informações, consulte [Armazenamento de backup](https://www.ibm.com/cloud/backup-and-restore){:new_window} e [EVault no IBM Cloud: precificação](https://www.ibm.com/cloud/evault/pricing){:new_window}.

<hr>

**Posso aumentar/diminuir minha capacidade do EVault sem comprometer meus backups?**

É possível aumentar ou diminuir o tamanho de seu EVault por meio do
[{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}. A modificação na capacidade do EVault não afeta a integridade dos dados que estão armazenados na área segura. Para obter mais informações, consulte [Expandindo a capacidade do EVault](expanding-evault-capacity.html).

<hr>

**O que acontece quando excedo a minha capacidade do EVault?**

Ainda é possível salvar e recuperar seus backups, mesmo que você tenha atingido o limite da capacidade que comprou anteriormente. Observe que você receberá uma cobrança extra para cada GB adicional usado.
