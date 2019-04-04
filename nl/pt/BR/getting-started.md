---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud backup, EVault, Carbonite, backup, getting started, setup, configure, run backup

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}
{:shortdesc: .shortdesc}

# Tutorial de Introdução
{: #getting-started}

Os backups asseguram que seus dados sejam armazenados com segurança fora de seu dispositivo e protegidos se eles forem perdidos. O {{site.data.keyword.backup_full}} é um sistema de backup automatizado baseado em agente gerenciado por meio do utilitário de gerenciamento baseado em navegador do portal do {{site.data.keyword.backup_notm}}. O {{site.data.keyword.backup_notm}} fornece aos usuários um método para fazer backup de dados entre servidores em um ou mais data centers na rede do {{site.data.keyword.BluSoftlayer_full}}. Os administradores podem configurar backups para seguir uma programação diária, semanal ou customizada que é destinada a sistemas integrais, diretórios específicos ou mesmo arquivos individuais. Os plug-ins extras asseguram a compatibilidade com softwares como o [Microsoft Exchange](/docs/infrastructure/Backup?topic=Backup-Exchangeplugin), o [Microsoft SQL](/docs/infrastructure/Backup?topic=Backup-MSSQLplugin), o [Oracle](/docs/infrastructure/Backup?topic=Backup-Oracleplugin#Oracleplugin) e o [VMware vSphere](/docs/infrastructure/Backup?topic=Backup-VRA) e permitem que os usuários concluam um [Bare Metal Restore](/docs/infrastructure/Backup?topic=Backup-BMRplugin#BMRplugin), quando necessário.
{:shortdesc}

## Antes de Iniciar
{: #prereqs}

Deve-se ter uma licença válida para usar o IBM Cloud Backup. É possível comprar o serviço do {{site.data.keyword.backup_notm}} de duas maneiras.

- [Comprar backups ao solicitar um servidor](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingwithserver).
- [Comprar backups como um upgrade](/docs/infrastructure/Backup?topic=Backup-ordering#purchasingasupgrade).

Para obter mais informações sobre pedidos e precificação, consulte [Provisionando o {{site.data.keyword.backup_notm}}](/docs/infrastructure/Backup?topic=Backup-ordering).

## Instalando o agente do {{site.data.keyword.backup_notm}}

O {{site.data.keyword.backup_notm}} Agent é suportado no S.O. a seguir.

**Windows**
 - Windows Server 2016
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - RHEL 7.x
 - RHEL 6.x
 - Ubuntu Linux 16,04
 - Ubuntu Linux 14,04

Siga as instruções apropriadas para o seu S.O.
- [Instalando o cliente de backup no Linux](/docs/infrastructure/Backup?topic=Backup-InstallinLinux)
- [Instalando o cliente de backup no Windows](/docs/infrastructure/Backup?topic=Backup-InstallinWindows)
- [Instalando o cliente de backup no Windows 2016](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016)

## Acessando o portal do {{site.data.keyword.backup_notm}} (anteriormente WebCC)
{: #accessingWebCC}

O portal do {{site.data.keyword.backup_notm}} é usado para interagir com qualquer serviço do {{site.data.keyword.backup_notm}} oferecido pelo {{site.data.keyword.BluSoftlayer_full}}. O portal do {{site.data.keyword.backup_notm}} é um cliente baseado em navegador que é executado na rede privada do {{site.data.keyword.BluSoftlayer_full}} e permite o controle total de qualquer serviço {{site.data.keyword.backup_notm}}, incluindo configuração e restaurações.

1. Acesse a rede privada por meio de VPN.

   O portal do {{site.data.keyword.backup_notm}} não pode ser acessado por meio da rede pública. Uma conexão VPN deve ser estabelecida primeiro.
   {:important}
2. Efetue login no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}){:new_window} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.<br/>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}.
2. Clique em **Armazenamento** > **Backup** para exibir os servidores com serviços de backup.
3. Selecione o servidor no qual os arquivos a serem submetidos a backup estão localizados. Clique na seta de expansão que aponta para a direita para revelar o link do portal do {{site.data.keyword.backup_notm}}.
4. Clique em **Login do portal do {{site.data.keyword.backup_notm}}** para iniciar o cliente do portal em seu navegador.

## Configurando o agente de Backup e o planejamento de backup

Depois de ter solicitado o {{site.data.keyword.backup_notm}} e o agente estiver instalado no servidor, será possível iniciar a criação de backups dos dados. Siga estas etapas para configurar seu planejamento de agente e retenção.

1. Efetue login no portal do {{site.data.keyword.backup_notm}}.
2. Clique em **Todos os Agentes**> **Agentes Configurado**.
3. Clique no link **Este é um novo agente que eu gostaria de configurar**. Percorra o processo e insira as informações a seguir:
   1. Configuração do agente - forneça a descrição do agente e clique em **Avançar**.
   2. Seleção de tipo de tarefa - insira o nome da tarefa, a descrição da tarefa e o tipo de origem de backup, clique em **Avançar**.
   3. Seleção - selecione diretórios e clique em **Incluir...**
   4. Opções-fornecer senhas
   5. Planejamento - clique em **Incluir** para criar um planejamento e clique em
**Avançar**.
   6. Selecione a área segura padrão, clique em **OK**.
   7. Clique em **Salvar**.
4. Crie um planejamento de retenção.
   1. Selecione **Editar** > **Configurações do Agente**.
   2. Clique em **Incluir**.
   3. Conclua os detalhes de retenção.
   4. Clique em **OK**.
   5. Clique em **Salvar**.

      Para obter mais informações sobre os esquemas de retenção, consulte as [Perguntas mais
frequentes](/docs/infrastructure/Backup?topic=Backup-faqs#faqs).
      {:tip}

## Executando sua primeira tarefa de backup

1. Efetue login no portal do {{site.data.keyword.backup_notm}}.
2. Clique em **Todos os agentes** e, em seguida, selecione o agente que você configurou.
3. Clique em **Executar backup**.
4. Confirme o Destino e selecione um esquema de retenção.
5. Clique em **Iniciar Backup**. É possível visualizar os detalhes de backups enquanto o processo está em execução.
6. Quando o backup estiver concluído, clique em **Fechar**.

Para obter mais informações, consulte [Configurando o backup em nível de arquivo simples no Linux](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup).
{:tip}

## Acessando e visualizando detalhes de armazenamento do {{site.data.keyword.backup_notm}} no Console

Os detalhes de armazenamento de seu serviço podem ser visualizados no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}){:new_window} e no {{site.data.keyword.slportal}} a qualquer momento. Os detalhes que podem ser visualizados incluem a senha, o endereço de armazenamento e o uso que estão associados ao serviço do {{site.data.keyword.backup_notm}} selecionado.

1. Efetue login no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}){:new_window} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.</br>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}.
2. Clique em **Armazenamento** e selecione **Backup** na lista.
2. Clique em qualquer lugar na linha da área segura da qual deseja visualizar os detalhes de armazenamento. Nessa visualização, a Senha não está visível.
3. Clique na caixa de seleção **Mostrar** ao lado do campo **Senha** para visualizar a senha para o serviço do {{site.data.keyword.backup_notm}} selecionado.

As mudanças que são feitas na senha do {{site.data.keyword.backup_notm}} dentro do {{site.data.keyword.slportal}} são feitas no próprio serviço. Para reconfigurar sua senha, siga as etapas em [Mudando a senha do serviço de backup](/docs/infrastructure/Backup?topic=Backup-changePassword).
{:important}

## Obtendo mais ajuda on-line

Os sistemas de portal do {{site.data.keyword.backup_notm}} são totalmente documentados e o suporte para o aplicativo está acessível no portal do {{site.data.keyword.backup_notm}}. Clique no ponto de interrogação branco em um círculo azul que está localizado no canto superior direito para obter **Ajuda**. Clique em qualquer artigo ou tópico na barra de navegação no lado esquerdo para visualizar mais informações.
