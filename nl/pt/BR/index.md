---

copyright:
  years: 2014, 2018
lastupdated: "2018-09-12"

---
{:new_window: target="_blank"}

# Introdução aos serviços de Backup do EVault

Os backups asseguram que seus dados sejam armazenados com segurança fora de seu dispositivo e protegidos se eles forem perdidos. O backup do EVault é um sistema de backup baseado em agente automatizado que é gerenciado por meio do utilitário de gerenciamento baseado em navegador WebCC do EVault. O EVault fornece aos usuários um método para fazer backup de dados entre servidores em um ou mais data centers na Rede do {{site.data.keyword.BluSoftlayer_full}}. Os administradores podem configurar backups para seguir uma programação diária, semanal ou customizada que é destinada a sistemas integrais, diretórios específicos ou mesmo arquivos individuais. Os plug-ins extras asseguram a compatibilidade com software como o Microsoft Exchange e o Microsoft SQL, outros tipos de software de terceiros e permitem que os usuários concluam um Bare Metal Restore, quando necessário.

## Solicitando EVault 

É possível comprar o serviço de backup do EVault de duas maneiras.

- Comprar EVault quando você solicita um servidor
- Comprar EVault como um upgrade

Para obter informações sobre precificação, consulte [Armazenamento de backup](https://www.ibm.com/cloud/backup-and-restore){:new_window} e [EVault no IBM Cloud](https://www.ibm.com/cloud/evault/pricing){:new_window}.

### Comprando o EVault quando você solicita um servidor

1. Efetue login no [Catálogo do IBM Cloud](https://console.bluemix.net/catalog/){:new_window} ou no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Solicite um servidor bare metal mensal. É possível saber mais sobre como solicitar servidores bare metal
[aqui](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html){:new_window}.
3. Você é redirecionado para o portal de gerenciamento para concluir o pedido. <br/>
   >**Nota**: o serviço de backup do EVault não está disponível quando você está solicitando um servidor faturado por hora. No entanto, o serviço pode ser incluído posteriormente como um upgrade. 
4. Na seção **Complementos**, escolha uma das opções do EVault (exceto "Nenhuma").
6. Role para baixo e clique em **Incluir no pedido**.
7. Localize a seção Nomes de host e domínio e insira os nomes de host e de domínio. É possível escolher qualquer nome de host e domínio que desejar.
8. À direita, clique nos **Termos do serviço de nuvem** e nas caixas de seleção **Contrato de serviço de terceiro**.
9. Confirme ou insira suas informações de pagamento e clique em **Enviar pedido**. Você é redirecionado para uma tela com seu número de ordem de fornecimento. É possível imprimir a tela porque ela também é seu recibo de ordem de fornecimento. <br/>**Nota**: também é possível salvar esse pedido sem efetuar a compra clicando em
**Salvar como cotação**.

Uma série de e-mails é enviada para seu administrador: confirmação da ordem de fornecimento, aprovação e processamento da ordem de fornecimento e Fornecimento concluído. O e-mail de Fornecimento concluído inclui um link para a página *Detalhes do dispositivo*, que é possível acessar depois de efetuar login no {{site.data.keyword.cloud_notm}}. Também é possível registrar-se diretamente no {{site.data.keyword.slportal}}.

** Confirmando a compra do serviço do EVault **
1. No
[{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window},
selecione **Dispositivos** > **Lista de dispositivos** no menu principal. 
2. Localize o novo servidor que você solicitou.
  - Se houver um ícone de relógio ao lado da URL, será necessário esperar para continuar com a confirmação de compra do EVault. É possível atualizar a página para ver um status atualizado em seu novo
servidor. Quando o ícone de relógio não estiver mais sendo exibido, será possível continuar com as próximas etapas
para confirmar a compra do serviço EVault.
  - Quando o ícone de relógio não estiver mais sendo exibido para seu servidor, clique no link (a URL do
servidor) para acessar a página **Detalhes**. 
3. Clique na guia **Armazenamento** para exibir as informações do EVault.
4. Inspecione a seção EVault e verifique se o tamanho que foi selecionado durante o processo de compra do EVault é exibido ao lado do link do EVault.

### Comprando EVault como um upgrade

**Selecione um servidor no qual instalar o EVault**
1. Efetue login no [Catálogo do IBM Cloud](https://console.bluemix.net/catalog/){:new_window} ou no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Selecione **Dispositivos** > **Lista de dispositivos** no menu
principal. Localize o dispositivo para o qual você deseja incluir o serviço EVault.
3. Clique no Nome do dispositivo para acessar a página Detalhes do dispositivo.

**Incluindo (comprando) serviço do EVault**
1. Clique na guia **Armazenamento** e role para baixo para localizar a seção EVault.
2. Clique no link **Incluir**.
3. Na janela, selecione um local e selecione um tamanho.
4. Selecione o tipo de Pagamento e clique em **Continuar**
5. Insira o **Código promocional**, se você tiver um, e clique em **Recalcular**.
6. Revise seu pedido e clique no link para ler os termos e condições.
7. Clique na caixa de seleção, caso você concorde com os termos e condições.
7. Clique em **Fazer pedido**.

** Confirmando a compra de upgrade do EVault **
1. Atualize a página **Detalhes do dispositivo** e assegure-se de que a
guia **Armazenamento** esteja selecionada.
2. Inspecione a seção EVault e verifique se o tamanho que foi selecionado durante o processo de compra do EVault é exibido ao lado do link do EVault. <br /> **Nota**: se o tamanho de armazenamento do EVault continuar mostrando uma capacidade zero, uma segunda atualização de página poderá ser necessária. 

## Acessando e visualizando detalhes do armazenamento de Backup do EVault no {{site.data.keyword.slportal}}

Os detalhes de armazenamento de seu serviço de backup do EVault podem ser visualizados no {{site.data.keyword.slportal}} a qualquer momento. Detalhes que podem ser visualizados incluem a senha, o endereço de armazenamento e o uso que está associado ao serviço de backup do EVault selecionado. 

1. Para acessar a tela **Armazenamento de backup do EVault**, efetue login no
[{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} com suas credenciais exclusivas.
2. Clique em **Armazenamento** e selecione **Backup** na lista.
2. Clique em qualquer lugar na linha para a área segura de backup do EVault desejada para visualizar seus detalhes de armazenamento. Nessa visualização, a Senha não está visível. Continue com a próxima etapa para visualizar a senha que está associada ao seu serviço de backup do EVault.
3. Clique na caixa de seleção **Mostrar** ao lado do campo **Senha** para visualizar a senha para o serviço de backup do EVault selecionado.

Para muitos produtos e serviços {{site.data.keyword.BluSoftlayer_full}}, o recurso de armazenamento de senha dentro do {{site.data.keyword.slportal}} é usado exclusivamente para armazenamento ou rastreamento da senha. Para essas ofertas, as mudanças que são feitas neles dentro do {{site.data.keyword.slportal}} não são aplicadas ao produto ou serviço. 

Esse _não_ é o caso para o backup do EVault. As mudanças feitas na senha de backup do EVault dentro do {{site.data.keyword.slportal}} são feitas no próprio serviço. Quando você mudar sua senha, tenha em mente que ela afeta seu serviço diretamente. Para reconfigurar sua senha, siga as etapas
em [Como mudar uma senha
do EVault Backup no {{site.data.keyword.slportal}}](/docs/infrastructure/Backup/change-password-evault-backup-service.html).

## Instalando o agente do EVault

O EVault Agent é suportado nos S.O. a seguir:

**Windows**
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
 - Red Hat Enterprise Linux 7.x
 - Red Hat Enterprise Linux 6.x
 - Ubuntu Linux 16,04
 - Ubuntu Linux 14,04

Siga as instruções apropriadas para o seu S.O.
- [Instalando o EVault Backup Client no
Linux](install-evault-backup-client-linux.html)
- [Instalando o EVault Backup Client no
Windows](install-evault-backup-client-windows.html)
- [Instalando o EVault Backup Client para Windows
2016](install-evault-windows2016.html)

## Acessando o WebCentralControl (WebCC) para o EVault Backup

O WebCentralControl (WebCC) é o cliente usado para interagir com qualquer serviço de backup do EVault oferecido pelo {{site.data.keyword.BluSoftlayer_full}}. O WebCC é um cliente baseado em navegador que é executado na rede privada do {{site.data.keyword.BluSoftlayer_full}} e permite o controle total de qualquer serviço de backup do EVault, incluindo configuração e restaurações. Siga estas etapas para acessar o WebCC para backup do EVault.

1. Acesse a rede privada por meio de VPN.<br/>**Nota**: o WebCC não pode ser acessado pela rede pública. Uma conexão VPN deve ser estabelecida primeiro.
2. Acesse a tela de armazenamento de backup do EVault no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
3. Clique em qualquer lugar na linha do EVault Backup desejado para expandir a
visualização.
4. Clique em **Login do WebCC** para iniciar o cliente do WebCC em seu navegador.

## Configurando o agente do EVault no WebCC

Depois de ter pedido seu serviço EVault e o agente ser instalado no servidor, é possível iniciar a criação de backups de seus dados. Siga estas etapas para configurar seu agente e
o planejamento de retenção e iniciar sua primeira tarefa de backup.

1. Efetue login no WebCC.
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
   **Nota**: leia mais sobre como os Esquemas de retenção funcionam [aqui](evault-backup-faq.html)
5. Execute o agente e inicie um backup.
   1. Clique em **Todos os agentes** e, em seguida, selecione o agente que você configurou.
   2. Clique em **Executar backup**.
   3. Confirme o Destino e selecione um esquema de retenção.
   4. Clique em **Iniciar Backup**. É possível visualizar os detalhes de backups
enquanto o processo está em execução.
   5. Quando o backup estiver concluído, clique em **Fechar**.
   
>**Nota**: leia mais sobre como é possível configurar backups no nível do arquivo simples no Linux [aqui](configure-simple-file-backup-linux.html).

## Obtendo ajuda on-line

Os sistemas de WebCC são totalmente documentados e o suporte para o aplicativo é acessível no WebCC. Clique no ponto de interrogação branco em um círculo azul que está localizado no canto superior direito para obter **Ajuda**. Clique em qualquer artigo ou tópico na barra de navegação no lado esquerdo para visualizar mais informações.


