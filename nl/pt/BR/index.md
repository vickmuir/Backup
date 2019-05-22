---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-28"

keywords: IBM Cloud backup, EVault, Carbonite, IBM Cloud backup, Enterprise backup

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Provisionando o {{site.data.keyword.backup_notm}}
{: #ordering}

É possível comprar o serviço do {{site.data.keyword.backup_notm}} de duas maneiras.

- [Comprar backups ao solicitar um servidor](#purchasingwithserver).
- [Comprar backups como um upgrade](#purchasingasupgrade).

Para obter mais informações sobre precificação, consulte [Armazenamento do {{site.data.keyword.backup_notm}}](https://www.ibm.com/cloud/backup-and-restore){: external} e [{{site.data.keyword.backup_notm}} no IBM Cloud](https://www.ibm.com/cloud/backup/pricing){: external}.

## Comprando o {{site.data.keyword.backup_notm}} ao solicitar um servidor
{: #purchasingwithserver}

1. Efetue login no [catálogo do IBM Cloud](https://{DomainName}/catalog){: external} ou no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}
2. Solicite um servidor bare metal mensal. Para obter mais informações sobre a solicitação de servidores bare metal, consulte [Construindo servidores bare metal customizados](/docs/bare-metal?topic=bare-metal-ordering-baremetal-server#ordering-baremetal-server){: external}.
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

### Confirmando a compra do {{site.data.keyword.backup_notm}}
1. No [console do {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external}, clique no ícone de **Menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.</br>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}.
2. Clique em **Dispositivo** > **Lista de dispositivos**.
2. Localize o novo servidor que você solicitou.
  - Se você vir um ícone de relógio ao lado da URL, será necessário aguardar para continuar com a confirmação de compra do {{site.data.keyword.backup_notm}}. É possível atualizar a página para ver um status atualizado em seu novo servidor. Quando o ícone de relógio não estiver mais presente, será possível continuar com as próximas etapas para confirmar a compra do serviço do {{site.data.keyword.backup_notm}}
  - Quando o ícone de relógio não estiver mais sendo exibido para seu servidor, clique no link (a URL do servidor) para acessar a página **Detalhes**.
3. Clique na guia **Armazenamento** para exibir as informações do {{site.data.keyword.backup_notm}}.
4. Inspecione a seção do {{site.data.keyword.backup_notm}} e verifique se o tamanho que foi selecionado durante o processo de compra é exibido.

## Comprando o {{site.data.keyword.backup_notm}} como um upgrade
{: #purchasingasupgrade}

### Selecione um servidor no qual instalar o {{site.data.keyword.backup_notm}}

1. Efetue login no console do [{{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} e clique no ícone de **menu** na parte superior esquerda. Selecione **Infraestrutura clássica**.</br>
   Como alternativa, é possível efetuar login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}.
2. Selecione **Dispositivos** > **Lista de dispositivos** no menu principal. Localize o dispositivo no qual você deseja incluir o serviço de backup.
3. Clique em Nome do dispositivo para acessar a página **Detalhes do dispositivo**.

### Incluindo (comprando) o serviço do {{site.data.keyword.backup_notm}}
1. Clique na guia **Armazenamento** e role para baixo para localizar a seção do {{site.data.keyword.backup_notm}}.
2. Clique no link **Incluir**.
3. Na janela, selecione um local e selecione um tamanho.
4. Selecione o tipo de Pagamento e clique em **Continuar**
5. Insira o **Código promocional**, se você tiver um, e clique em **Recalcular**.
6. Revise seu pedido e clique no link para ler os termos e condições.
7. Clique na caixa de seleção, caso você concorde com os termos e condições.
7. Clique em **Fazer pedido**.

### Confirmando a compra de upgrade do {{site.data.keyword.backup_notm}}
1. Atualize a página **Detalhes do dispositivo** e assegure-se de que a guia **Armazenamento** esteja selecionada.
2. Inspecione a seção do {{site.data.keyword.backup_notm}} e verifique se o tamanho que foi selecionado durante o processo de compra é exibido.

   Se o tamanho do armazenamento de backup continuar a mostrar uma capacidade de zero, uma segunda atualização de página poderá ser necessária.
   {:tip}

Quando estiver pronto, vá em frente e instale o agente de software no servidor e configure seu planejamento de backup no portal do {{site.data.keyword.backup_notm}}. Para obter mais informações, veja o [Tutorial de introdução](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
