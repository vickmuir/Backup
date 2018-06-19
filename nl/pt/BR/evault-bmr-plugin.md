---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# Instalando o plug-in do EVault Bare Metal Restore

O EVault BMR é uma solução de recuperação de desastre para o Microsoft Windows que permite restaurar
completamente seu servidor de um estado bare metal quando um desastre ocorre, como uma falha do sistema
operacional ou no hardware. Esse sistema permite que você restaure rapidamente a imagem do
sistema por meio de um local seguro que seja gerenciado pelo
{{site.data.keyword.BluSoftlayer_full}}.

**Nota**: o BMR é um produto do Microsoft Windows somente em servidores físicos. Ele
não está disponível para servidores virtuais. Distribuições de Bare Metal Restores para Linux não
são suportadas. O BMR é suportado somente pelo EVault Agent 8.30 ou inferior. (30 de junho de 2018).

## Recursos fornecidos

- Restaure seu sistema para um momento selecionado.
- Restaure seu sistema por meio de backups de imagem ou baseados em arquivo.
- Restaure seu sistema por meio de backups que estão armazenados no EVault.
- Uma transação de recuperação inicializável que permitirá a restauração de seus dados sem um sistema
inicializável.

## Solicite o plug-in

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Clique em **Storage** > **Backup**.
3. Selecione a sua conta do EVault e clique em **Pedir plug-ins**.
4. Selecione **Plug-in do EVault - BMR (Bare Metal Restore)** e clique em
**Continuar**.
5. Insira o seu Código promocional se você tiver um e clique em **Recalcular**.
6. Os encargos atualizados são exibidos. Revise seu pedido.
7. Marque as caixas para indicar que você leu o Contrato de Prestação de Serviços Principal e aceite os Termos de Software de Terceiro.
8. Clique em **Fazer pedido**.

## Guia do Usuário

Conecte-se à rede do {{site.data.keyword.BluSoftlayer_full}} com
o {{site.data.keyword.BluVPN}} para que seja possível fazer download do EVault System Restore v8.3 -
User Guide.pdf por meio da
[Documentação do
EVault transferível por download](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Perguntas Mais Frequentes

### Posso migrar de um disco único para uma matriz RAID?

Sim, vai funcionar. No entanto, é necessário selecionar um dispositivo de grande capacidade devido à
diminuição de tamanho que a matriz RAID causará.

### O que acontecerá se eu restaurar a imagem para um disco maior que o volume original?

Se você restaurar a imagem para um disco maior que o volume original, o espaço restante será
desalocado. Portanto, por exemplo, se você tiver uma unidade de 500 GB e restaurar seus dados para um disco de
1 TB, haverá 500 GB de espaço em disco desalocado. Com o Windows 2008, é possível usar o utilitário de disco
nativo para aumentar a partição primária. No entanto, no Windows 2003, não há um recurso nativo para isso,
portanto, a alocação do espaço é recomendada.

### Posso usar o BMR para meu backup regular?

Isso não é uma imagem de disco, mas um sistema de backup de imagem do volume do sistema. Esse sistema
não é destinado a ser usado para backups regulares, mas sim junto com eles.  

### Posso usar o BMR para meus backups de banco de dados?

Os backups de banco de dados devem ser feitos separadamente com os métodos normais do EVault Backup.
O BMR não substitui a necessidade de plug-ins do SQL ou do Oracle. Embora o BMR use a tecnologia VSS para
fazer backup de arquivos abertos, não podemos sempre garantir que os arquivos de backup estarão
consistentes com a transação. A recomendação para esses tipos de aplicativos especializados é a criação
de duas tarefas de backup: uma para backup do S.O. e de arquivos binários do aplicativo e outra para dados do
aplicativo. Há uma nota sobre isso mais no final do guia do usuário de BMR.

### Que tipo de tarefas de restauração é possível executar com o BMR?

É possível fazer uma restauração do sistema inteiro ou selecionar arquivos individuais do
backup para a restauração. Isso significa que essa tarefa pode substituir sua tarefa de backup de arquivos
atual. O processo de restauração pode ser feito dentro do S.O., tal como uma tarefa de backup tradicional.

### O BMR tem recursos de backup de arquivo aberto?

O BMR tem recursos de backup de arquivo aberto. No entanto, o BMR não substitui a necessidade de
plug-ins do SQL ou do Oracle. Clique [aqui](evault-mssql-plugin.html) para obter as
instruções de instalação do plug-in do MSSQL.

### Que quantias de espaço em disco e de tempo são necessárias para uma restauração de BMR?

Um backup feito de uma instalação padrão ocupa cerca de 6 GB. Tal restauração leva em torno de 15
minutos em uma porta de 1 GB. Esse processo também é afetado pela velocidade da porta privada. Se você
precisar de backups/restaurações mais rápidas, poderá ser necessário aumentar a velocidade da porta.
