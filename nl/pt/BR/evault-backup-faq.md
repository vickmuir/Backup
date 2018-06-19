---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# -backup do EVault perguntas mais frequentes

## De que tipo de aplicativos posso fazer backup com o EVault?

O EVault permite backups de vários aplicativos. No entanto,
o {{site.data.keyword.BluSoftlayer_full}} oferece agentes de software para alguns dos sistemas de
software mais comuns que são submetidos a backup, que incluem:

- Bare Metal Restore
- Microsoft SQL
- Oracle

Cada agente está disponível como um complemento para o seu serviço EVault Backup. Para incluir um
agente em seu serviço, entre em contato com um membro de nossa equipe de Vendas hoje. Observe que os plug-ins
que estão listados aqui são compatíveis somente com servidores Windows. 

## Com que frequência posso fazer backup de meus dados com o EVault Backup?

É possível fazer backup dos dados com a frequência que desejar. No WebCC, os backups podem ser feitos
manualmente ou podem ser planejados como uma única instância ou para serem recorrentes. Os backups recorrentes podem
ser feitos diariamente, semanalmente, mensalmente ou em uma programação customizada e podem ser atualizados ou
cancelados a qualquer momento.

**Nota**: backups altamente frequentes que são executados várias vezes por dia ou por
hora podem fazer com que as tarefas de backup se tornem corrompidas. Isso ocorre porque a área segura pode não
ser capaz de remover os conjuntos de segurança antigos ou de executar outras tarefas em segundo plano
necessárias.

## Como os esquemas de retenção funciona?

O EVault permite a retenção de dados, dependendo de até quanto tempo você deseja recuperá-los. Os esquemas de
retenção **Diariamente** retêm os dados por
sete dias, enquanto que os esquemas **Semanalmente** retêm os dados por um mês e
os esquemas **Mensalmente** retêm os dados por um ano. No término de cada período, o
conjunto de dados mais antigo é descartado e o primeiro "backup delta" que foi feito se torna o ponto
de restauração mais antigo disponível. 

## O que é Tecnologia Delta?

O primeiro backup é um "valor inicial" (um backup completo) e o próximo backup e os subsequentes
são "deltas" (ou seja, somente mudanças), no entanto, eles são equivalentes a um
"backup completo" e ainda considerados como um. Ou seja, é possível restaurar todos ou quaisquer arquivos dele. Essa tecnologia permite que
"backups completos" sejam feitos em cada sessão, economizando, no entanto, enormes quantidades de espaço na
Área segura e diminuindo a quantia de tempo que cada backup subsequente leva para ser concluído.

## Meus backups estão seguros?

Por padrão, toda a criptografia "over the wire" (OTW) é codificada com a criptografia AES de 256 bits.
Também é possível optar por armazenar dados em formato criptografado usando o AES 256 bits. 

**Nota**: você deverá se lembrar da sua senha de criptografia. Seus dados não podem ser
restaurados sem sua senha. Se você perder sua senha, não será possível recuperar seus dados. 

As proporções de compactação permitem compactação zero até uma compactação de proporções máximas que,
dependendo do tipo de arquivo, pode atingir de 20 a 30 por cento.


## Quais informações são armazenadas com backups de estado do sistema?

Os backups de estado do sistema incluem o banco de dados de registro de classe do COM +,
o registro, os arquivos de inicialização, os arquivos de sistema e o contador de desempenho, mas não se limitam a eles. Está tudo dependente de seu sistema. Arquivos de sistema variam por S.O. de sistema e service packs. Geralmente há milhares delas. O MS Windows fará uma lista dinâmica dessas DLLs quando você as incluir no backup. A inclusão dos arquivos do sistema permite que você recupere arquivos de sistema corrompidos e alguns pacotes de serviço acidentalmente desinstalados ou recupere com uma restauração bare metal. Ela permite retornar ao estado do backup sem precisar reinstalar o S.O. por meio do kit de instalação e, em seguida, instalar cada pacote de serviço separadamente.

**Nota**: nenhum arquivo de dados do usuário é incluído no backup de estado do
sistema. Uma tarefa de backup de estado do sistema deve ser configurada como uma tarefa independente. Nenhuma
outra origem de dados deverá ser incluída na tarefa de backup de Estado do Sistema.

## O que acontece abrir arquivos?

Por padrão, o cliente base tem uma tecnologia de última geração para manipular a maioria dos arquivos
abertos em execução no S.O. Em casos raros, caso os backups falhem devido a limitações de arquivos abertos,
existem plug-ins secundários que podem ser comprados para uma melhor manipulação de arquivos abertos. 
Geralmente, o plug-in de arquivo aberto não é necessário, a menos que ocorram erros em seus backups de arquivos
abertos, caso em que é possível solicitar os plug-ins.
