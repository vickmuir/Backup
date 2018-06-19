---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-04"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Terminologia de restauração e do EVault Backup 

## Tecnologia Delta:
O primeiro Backup é um "valor inicial" (um Backup completo) e o próximo backup e os subsequentes são
"deltas" (ou seja, somente mudanças), no entanto, eles são equivalentes a um “backup
completo” e ainda considerados como um. Ou seja, é possível restaurar todos ou quaisquer arquivos dele. Essa tecnologia permite que
"Backups completos" sejam feitos em cada sessão, economizando, no entanto, enormes quantidades de espaço na
Área segura e diminuindo a quantia de tempo que cada backup subsequente leva para ser concluído.

## Esquemas de Retenção: 
O EVault permite a retenção de dados, dependendo de até quanto tempo você deseja recuperá-los. Os esquemas de
retenção Diariamente retêm os dados por 7 dias, enquanto que Semanalmente retém os dados por 1 mês e
Mensalmente retém os dados por 1 ano. No término de cada período, o conjunto de dados mais antigo é descartado e o
primeiro delta feito se torna o ponto de restauração mais antigo disponível. 

## Compactação: 
O EVault oferece 6 tipos de soluções de criptografia para seus dados: DES de 56 bits, Blowfish de 56 bits,
Triple DES de 112 bits, Blowfish de 128 bits, AES de 128 bits e AES de 256 bits. As proporções de compactação
permitem compactação zero até uma compactação de proporções máximas que, dependendo do tipo de arquivo, pode
atingir de 20% to 30%. 
## Criptografia:
Por padrão, toda a criptografia "over the wire" (OTW) é codificada com a criptografia AES de 128 bits.
Se você quer que os dados sejam armazenados em um formato criptografado, há várias opções como parte do
processo de backup. Observe que, se você perder a senha, NÃO será possível recuperar seus dados. 

## Backups especiais: 
Os backups de estado do sistema incluem o banco de dados de registro de classe do COM +,
o registro, os arquivos de inicialização, os arquivos de sistema e o contador de desempenho, todos
dependentes de seu sistema, mas não se limitam a eles. Arquivos de sistema variam por S.O. de sistema e service packs. Geralmente há milhares delas. O MS Windows fará uma lista dinâmica dessas DLLs quando você as incluir no backup. A inclusão dos arquivos do sistema permite que você recupere arquivos de sistema corrompidos e alguns pacotes de serviço acidentalmente desinstalados ou recupere com uma restauração bare metal. Ela permite retornar ao estado do backup sem precisar reinstalar o S.O. por meio do kit de instalação e, em seguida, instalar cada pacote de serviço separadamente. 

## Arquivos Abertos: 
Por padrão, o cliente base tem uma tecnologia de última geração para manipular a maioria dos arquivos
abertos em execução no S.O. Em casos raros, caso os backups falhem devido a limitações de arquivos abertos,
existem plug-ins secundários que podem ser comprados para uma melhor manipulação de arquivos abertos. A regra
básica é que o plug-in de arquivo aberto não é necessário, a menos que ocorram erros em seus backups de
arquivos abertos, caso em que é possível solicitar os plug-ins.
