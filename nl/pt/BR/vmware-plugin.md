---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Instalando o vSphere Recovery Agent
{: #VRA}

O vSphere Recovery Agent (VRA) é um aplicativo do Windows, que pode fazer backup e restaurar VMDKs de até 10 TB. É possível instalar o vSphere Recovery Agent em uma máquina física ou virtual que tenha acesso à rede local ao vCenter que deseja proteger. Para obter melhor desempenho, instale o VRA em uma máquina que esteja na mesma sub-rede que o vCenter. Para distribuir a carga de trabalho, até cinco VRAs podem proteger as VMs conectadas a um único vCenter.

Em um cluster estendido vSAN, cada VM tem um site preferencial. Idealmente, um VRA local é instalado em cada site que faz backup das VMs preferenciais desse site. Se uma VM for movida para um site diferente (devido a manutenção ou falhas), o desempenho de backup poderá ser degradado, mas permanecer aceitável.


## Pedindo o plug-in
{: #orderingVRAPlugin}

O {{site.data.keyword.cloud_notm}} fornece o vSphere Recovery Agent (VRA) livre de encargos. Se você tiver uma assinatura atual do {{site.data.keyword.backup_notm}}, poderá fazer download do plug-in no portal do {{site.data.keyword.backup_notm}}.

## Instalando o Plug-in
{: #installVRAPlugin}

Assegure-se de que o gerenciamento de energia esteja desativado no servidor no qual instalar o VRA.
{: important}

1. Faça download do kit de instalação em `http://downloads.service.softlayer.com/evault/`. Em seguida, dê um clique duplo no kit de instalação.
2. Na mensagem de confirmação, clique em **SIM**.
3. Na página de boas-vindas, clique em **Avançar**.
4. Na página Contrato de licença de usuário final, leia o contrato de licença. Se você concordar com os termos, clique em **Eu aceito os termos no Contrato de licença** e, em seguida, clique em **Avançar**.
5. Na página Pasta de destino, execute uma das ações a seguir.
   * Para instalar o VRA no local padrão, clique em **Avançar**.
   * Para instalar o VRA em outro local, clique em **Mudar**. Na caixa de diálogo Mudar pasta de destino, procure a nova pasta de instalação ou digite-a na caixa Nome da pasta. Clique em **OK**. Na página Pasta de destino, clique em **Avançar**.
6. Na Página Registrar agente com o portal, especifique as informações a seguir.
   * No campo **Endereço de rede**, digite `ev-webcc01.service.softlayer.com`.
   * No campo **Porta**, digite `8086`.
   * No campo **Nome do usuário**, digite o nome do usuário do {{site.data.keyword.backup_notm}} para gerenciar o VRA.
   * No campo **Senha**, digite a senha do usuário do {{site.data.keyword.backup_notm}} especificado.
7.	Clique em **Avançar**. Quando a instalação estiver concluída, clique em **Concluir**.

## Configurando o vSphere Recovery Agent
{: #configureVRA}

Após o VRA ser instalado, é necessário configurá-lo no portal do {{site.data.keyword.backup_notm}}.

1. Efetue login no portal do {{site.data.keyword.backup_notm}}. Para obter mais informações sobre como acessar o portal do {{site.data.keyword.backup_notm}}, consulte o [Tutorial de introdução](/docs/infrastructure/Backup?topic=Backup-getting-started#accessingWebCC).
2. Na guia Computadores, selecione o servidor que deseja fazer backup.
3. Configure suas informações da área segura.

   As informações da área segura podem ser configuradas de duas maneiras: **Automaticamente** ou **Manualmente**.<br/>Se o agente estiver sendo configurado pela primeira vez, ele poderá ser configurado usando a opção [Configuração automática](#VRAautoconfig).<br/>Se o computador foi registrado anteriormente com uma Área segura, a configuração automática não funcionará e a área segura precisará ser [configurada manualmente](#VRAmanualconfig).
   {: tip}

4. Defina as [Configurações do vCenter](#vCenterSettingsconfig)   

### Configurando a Área segura automaticamente
{: #VRAautoconfig}

Para definir as configurações da área segura automaticamente, clique em **Configurar automaticamente**. O Assistente de configuração é executado e define as configurações da Área segura para você. Quando estiver concluído, clique em **Acessar o agente** para verificar as informações na guia **Configurações da área segura**.
 

### Configurando a área segura manualmente
{: #VRAmanualconfig}

Para definir as configurações da área segura manualmente, clique em **Configurar manualmente**.   
1. Clique em **Configurações da área segura**.
2. Clique em **Incluir área segura**. A janela Configurações da área segura será exibida. Nas opções **Perfil da área segura**, selecione a área segura apropriada.
   Se o computador foi registrado anteriormente com uma área segura do {{site.data.keyword.backup_notm}}, todas as informações serão preenchidas automaticamente quando a Área segura for selecionada no Perfil da área segura.
   {:note}

3. Verifique todas as informações na página Configurações da área segura e clique em **Salvar**.
4. Ao salvar as configurações da área segura, as informações da área segura se tornarão visíveis na guia **Configurações da área segura**.


### Definindo configurações do vCenter Agent
{: #vCenterSettingsconfig}
Após o registro bem-sucedido da área segura, as Configurações do vCenter precisarão ser configuradas antes de poder criar e executar quaisquer tarefas de backup.

1. Clique na guia **Configurações do vCenter**
2. Forneça o endereço IP do vCenter, o nome de domínio e as credenciais para o vCenter que deseja proteger.
   O usuário deve ter acesso administrativo ao vCenter para executar essa tarefa com sucesso.
   {:note}

3. Desative o Change Block Tracking (CBT) removendo o visto. O CBT é um recurso do VMware que rastreia setores de disco mudados e melhora o desempenho de backups de VM e é ativado automaticamente pelo vSphere Agent.
4. Clique em **Testar conexão do vCenter**. Uma nova janela exibe os resultados. Se as informações de login fornecidas estiverem corretas, a mensagem “As credenciais do vCenter foram validadas com sucesso” será exibida.
5. Clique em  ** Salvar **  para salvar as configurações.

## Etapas Seguintes
{: #VRAnextteps}
1. [Configurar, planejar e executar uma tarefa de backup](/docs/infrastructure/Backup?topic=Backup-ConfigureVRA)
2. [Restaurar dados do vSphere](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore)

Conecte-se à rede do {{site.data.keyword.BluSoftlayer_full}} com o {{site.data.keyword.BluVPN}} para que seja possível acessar e fazer download do guia do usuário da [Documentação transferível por download do {{site.data.keyword.backup_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.
{:tip}
