---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Introdução aos serviços do {{site.data.keyword.backup_notm}}
{: #GettingStarted}

Os backups asseguram que seus dados sejam armazenados com segurança fora de seu dispositivo e protegidos se eles forem perdidos. O {{site.data.keyword.backup_full}} é um sistema de backup automatizado baseado em agente gerenciado por meio do utilitário de gerenciamento baseado em navegador do portal do {{site.data.keyword.backup_notm}}. O {{site.data.keyword.backup_notm}} fornece aos usuários um método para fazer backup de dados entre servidores em um ou mais data centers na rede do {{site.data.keyword.BluSoftlayer_full}}. Os administradores podem configurar backups para seguir uma programação diária, semanal ou customizada que é destinada a sistemas integrais, diretórios específicos ou mesmo arquivos individuais. Os plug-ins extras asseguram a compatibilidade com software como o Microsoft Exchange e o Microsoft SQL, outros tipos de software de terceiros e permitem que os usuários concluam um Bare Metal Restore, quando necessário.

## Solicitando o {{site.data.keyword.backup_notm}}

É possível comprar o serviço do {{site.data.keyword.backup_notm}} de duas maneiras.

- [Comprar backups ao solicitar um servidor](#purchasingwithserver).
- [Comprar backups como um upgrade](#purchasingasupgrade).

Para obter mais informações sobre precificação, consulte [Armazenamento do {{site.data.keyword.backup_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/cloud/backup-and-restore){:new_window} e [{{site.data.keyword.backup_notm}} on IBM Cloud ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.ibm.com/cloud/evault/pricing){:new_window}.

### Comprando o {{site.data.keyword.backup_notm}} ao solicitar um servidor
{: #purchasingwithserver}

1. Efetue login no [catálogo do IBM Cloud ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/catalog/){:new_window} ou no [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}
2. Solicite um servidor bare metal mensal. Para obter mais informações sobre a solicitação de servidores bare metal, consulte [Construindo servidores bare metal customizados](https://{DomainName}/docs/bare-metal/baremetal-provision.html){:new_window}.
   1. Selecione a opção Quantidade, Faturamento. Insira os nomes do host e de domínio. É possível escolher qualquer nome de host e domínio que desejar.

      O serviço do {{site.data.keyword.backup_notm}} não está disponível quando você solicita um servidor faturado por hora. No entanto, o serviço pode ser incluído posteriormente como um upgrade.
      {:tip}
   2. Selecione o local.
   3. Selecione Configuração do servidor e Tipo de imagem do S.O. Também é possível escolher múltiplos complementos.
   4. Na seção **Discos de armazenamento**, clique em **Complementos** e selecione **{{site.data.keyword.backup_notm}}**. Escolha a opção que corresponde ao que você precisa.
   5. Em **Interface de rede**, selecione a Velocidade da porta de uplink e quaisquer complementos que desejar.
3. À direita, revise o resumo do pedido.
4. Depois de ter revisado os termos e as condições, marque a caixa **Eu li e concordo com os Contratos de Prestação de Serviços de terceiro**.
5. Clique em  ** Provisão **. Você é redirecionado para uma tela com seu número de ordem de fornecimento. É possível imprimir a tela porque ela também é seu recibo de ordem de fornecimento.

   Também é possível salvar esse pedido sem comprar clicando em **Salvar como cotação**.
   {:tip}

Uma série de e-mails é enviada para seu administrador: confirmação da ordem de fornecimento, aprovação e processamento da ordem de fornecimento e Fornecimento concluído. O e-mail de Fornecimento concluído inclui um link para a página *Detalhes do dispositivo*, que é possível acessar depois de efetuar login no {{site.data.keyword.cloud_notm}}. Também é possível registrar-se diretamente no {{site.data.keyword.slportal}}.

#### Confirmando a compra do {{site.data.keyword.backup_notm}}
1. No [console do {{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}/){:new_window}, clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.</br>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}.
2. Clique em **Dispositivo** > **Lista de dispositivos**.
2. Localize o novo servidor que você solicitou.
  - Se você vir um ícone de relógio ao lado da URL, será necessário aguardar para continuar com a confirmação de compra do {{site.data.keyword.backup_notm}}. É possível atualizar a página para ver um status atualizado em seu novo servidor. Quando o ícone de relógio não estiver mais presente, será possível continuar com as próximas etapas para confirmar a compra do serviço do {{site.data.keyword.backup_notm}}
  - Quando o ícone de relógio não estiver mais sendo exibido para seu servidor, clique no link (a URL do servidor) para acessar a página **Detalhes**.
3. Clique na guia **Armazenamento** para exibir as informações do {{site.data.keyword.backup_notm}}.
4. Inspecione a seção do {{site.data.keyword.backup_notm}} e verifique se o tamanho que foi selecionado durante o processo de compra é exibido.

### Comprando o {{site.data.keyword.backup_notm}} como um upgrade
{: #purchasingasupgrade}

#### Selecione um servidor no qual instalar o {{site.data.keyword.backup_notm}}

1. Efetue login no console do [{{site.data.keyword.cloud_notm}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://{DomainName}){:new_window} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.</br>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}.
2. Selecione **Dispositivos** > **Lista de dispositivos** no menu principal. Localize o dispositivo no qual você deseja incluir o serviço de backup.
3. Clique em Nome do dispositivo para acessar a página **Detalhes do dispositivo**.

#### Incluindo (comprando) o serviço do {{site.data.keyword.backup_notm}}
1. Clique na guia **Armazenamento** e role para baixo para localizar a seção do {{site.data.keyword.backup_notm}}.
2. Clique no link **Incluir**.
3. Na janela, selecione um local e selecione um tamanho.
4. Selecione o tipo de Pagamento e clique em **Continuar**
5. Insira o **Código promocional**, se você tiver um, e clique em **Recalcular**.
6. Revise seu pedido e clique no link para ler os termos e condições.
7. Clique na caixa de seleção, caso você concorde com os termos e condições.
7. Clique em **Fazer pedido**.

#### Confirmando a compra de upgrade do {{site.data.keyword.backup_notm}}
1. Atualize a página **Detalhes do dispositivo** e assegure-se de que a guia **Armazenamento** esteja selecionada.
2. Inspecione a seção do {{site.data.keyword.backup_notm}} e verifique se o tamanho que foi selecionado durante o processo de compra é exibido.

   Se o tamanho do armazenamento de backup continuar a mostrar uma capacidade de zero, uma segunda atualização de página poderá ser necessária.
   {:tip}

## Acessando e visualizando os detalhes de armazenamento do {{site.data.keyword.backup_notm}}

Os detalhes de armazenamento de seu serviço podem ser visualizados no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}/){:new_window} e no {{site.data.keyword.slportal}} a qualquer momento. Os detalhes que podem ser visualizados incluem a senha, o endereço de armazenamento e o uso que estão associados ao serviço do {{site.data.keyword.backup_notm}} selecionado.

1. Efetue login no [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}){:new_window} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.</br>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}.
2. Clique em **Armazenamento** e selecione **Backup** na lista.
2. Clique em qualquer lugar na linha da área segura da qual deseja visualizar os detalhes de armazenamento. Nessa visualização, a Senha não está visível.
3. Clique na caixa de seleção **Mostrar** ao lado do campo **Senha** para visualizar a senha para o serviço do {{site.data.keyword.backup_notm}} selecionado.

As mudanças que são feitas na senha do {{site.data.keyword.backup_notm}} dentro do {{site.data.keyword.slportal}} são feitas no próprio serviço. Para reconfigurar sua senha, siga as etapas em [Mudando a senha do serviço de backup](/docs/infrastructure/Backup?topic=Backup-changePassword).
{:important}

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

O portal do {{site.data.keyword.backup_notm}} é usado para interagir com qualquer serviço do {{site.data.keyword.backup_notm}} oferecido pelo {{site.data.keyword.BluSoftlayer_full}}. O portal do {{site.data.keyword.backup_notm}} é um cliente baseado em navegador que é executado na rede privada do {{site.data.keyword.BluSoftlayer_full}} e permite o controle total de qualquer serviço {{site.data.keyword.backup_notm}}, incluindo configuração e restaurações.

1. Acesse a rede privada por meio de VPN.

   O portal do {{site.data.keyword.backup_notm}} não pode ser acessado por meio da rede pública. Uma conexão VPN deve ser estabelecida primeiro.
   {:important}
2. Acesse a tela de armazenamento de Backup no [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}.
3. Clique em qualquer lugar na linha do serviço {{site.data.keyword.backup_notm}} que você deseja ver para expandir a visualização.
4. Clique em **Login do portal do {{site.data.keyword.backup_notm}}** para iniciar o cliente do portal em seu navegador.

## Configurando o agente de Backup e o planejamento de backup

Depois de ter solicitado o {{site.data.keyword.backup_notm}} e o agente estiver instalado no servidor, será possível iniciar a criação de backups dos dados. Siga estas etapas para configurar seu agente e o planejamento de retenção e iniciar sua primeira tarefa de backup.

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
frequentes](faqs.html).
      {:tip}
5. Execute o agente e inicie um backup.
   1. Clique em **Todos os agentes** e, em seguida, selecione o agente que você configurou.
   2. Clique em **Executar backup**.
   3. Confirme o Destino e selecione um esquema de retenção.
   4. Clique em **Iniciar Backup**. É possível visualizar os detalhes de backups enquanto o processo está em execução.
   5. Quando o backup estiver concluído, clique em **Fechar**.

Para obter mais informações, consulte [Configurando o backup em nível de arquivo simples no Linux](/docs/infrastructure/Backup?topic=Backup-configureLinuxBackup).
{:tip}

## Obtendo ajuda on-line

Os sistemas de portal do {{site.data.keyword.backup_notm}} são totalmente documentados e o suporte para o aplicativo está acessível no portal do {{site.data.keyword.backup_notm}}. Clique no ponto de interrogação branco em um círculo azul que está localizado no canto superior direito para obter **Ajuda**. Clique em qualquer artigo ou tópico na barra de navegação no lado esquerdo para visualizar mais informações.
