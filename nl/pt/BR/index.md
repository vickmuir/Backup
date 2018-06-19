---

copyright:
  years: 2014, 2018
lastupdated: "2018-06-05"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Introdução aos serviços EVault Backup

Os backups asseguram que seus dados sejam armazenados com segurança fora do seu dispositivo e protegidos,
caso sejam perdidos. O EVault Backup é um sistema de backup automatizado baseado em agente que é gerenciado
por meio do utilitário de gerenciamento baseado no navegador EVault WebCC, fornecendo aos usuários um método
para fazer backup de dados entre servidores em um ou mais data centers na Rede
do {{site.data.keyword.BluSoftlayer_full}}. Os administradores podem configurar backups para seguir um planejamento por hora, diário, semanal ou customizado que é destinado a sistemas integrais, diretórios específicos ou mesmo arquivos individuais. Plug-ins adicionais permitem compatibilidade com software como o Microsoft Exchange e Microsoft SQL, bem como outros tipos de software de terceiros e permite que os usuários executem uma Restauração bare metal, quando necessário.

## Solicitando EVault 

Há duas maneiras de comprar o serviço EVault Backup:

- Compra EVault quando Solicitando um Servidor
- Compra EVault como um Upgrade

### Compra EVault ao solicitar um servidor

1. Efetue login no [Catálogo do The IBM Cloud](https://console.bluemix.net/catalog/){:new_window} ou no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Pedir um servidor bare metal mensal. É possível saber mais sobre como solicitar servidores bare metal
[aqui](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html){:new_window}.
3. Você é redirecionado para o portal de gerenciamento para concluir o pedido. <br/>
  **Nota**: o serviço EVault Backup não está disponível ao solicitar um servidor
faturado por hora. No entanto, o serviço pode ser incluído posteriormente como um upgrade. 
4. Na seção **Complementos**, escolha uma das opções do EVault (exceto "Nenhuma").
6. Na parte inferior da página, clique em **Incluir no pedido**. A página de Saída é exibida.
7. Na página **CHECK-OUT**, localize a seção Nomes de host e de domínio e insira
os nomes de host e de domínio. É possível escolher qualquer nome de host e domínio que desejar.
8. À direita da página **CHECK-OUT**, clique nas caixas de seleção
**Termos de Serviço de Nuvem** e **Contrato de Prestação de Serviços de
Terceiro**.
9. Confirme ou insira suas informações de pagamento e clique em **Enviar pedido**. Você é redirecionado para uma tela com seu número de ordem de fornecimento. É possível imprimir a tela porque ela também é seu recibo de ordem de fornecimento. <br/>
**Nota**: também é possível salvar esse pedido sem efetuar a compra clicando em
**Salvar como cotação**.

Uma série de e-mails é enviada a seu administrador: confirmação, aprovação e processamento da ordem de fornecimento, e fornecimento concluído. 
O e-mail completo de fornecimento inclui um link para sua página *Detalhes* depois de
efetuar login no {{site.data.keyword.cloud_notm}}. Também é possível registrar-se diretamente no {{site.data.keyword.slportal}}.

**Confirmar a EVault serviço de compra**
1. No
[{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window},
selecione **Dispositivos** > **Lista de dispositivos** no menu principal. 
2. Localize o novo servidor que você pediu.
  - Se um ícone de relógio aparecer ao lado da URL, será necessário esperar para continuar com a
confirmação de compra do EVault. É possível atualizar a página para ver um status atualizado em seu novo
servidor. Quando o ícone de relógio não estiver mais sendo exibido, será possível continuar com as próximas etapas
para confirmar a compra do serviço EVault.
  - Quando o ícone de relógio não estiver mais sendo exibido para seu servidor, clique no link (a URL do
servidor) para acessar a página **Detalhes**. 
3. Clique na guia **Armazenamento** para exibir as informações do EVault.
4. Inspecione a seção do EVault e verifique se o tamanho selecionado durante o processo de compra do EVault é exibido próximo ao link do EVault.

### Compra EVault como um upgrade

**Selecione um servidor no qual instalar o EVault**
1. Efetue login no [Catálogo do The IBM Cloud](https://console.bluemix.net/catalog/){:new_window} ou no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Selecione **Dispositivos** > **Lista de dispositivos** no menu
principal. Localize o dispositivo para o qual você deseja incluir o serviço EVault.
3. Clique no Nome do dispositivo para acessar a página Detalhes do dispositivo.

**Incluir (compra) serviço EVault**
1. Clique na guia **Armazenamento** e localize a seção EVault próximo à parte
inferior da página.
2. Clique em **Incluir** link.
3. No pop-up, selecione um local ou aceite o padrão e selecione um tamanho.
4. Clique em **Continuar**
5. Clique na caixa de seleção, caso você concorde com os termos e condições.
6. Clique em **Fazer pedido**.

**Confirmar a EVault serviço de compra**
1. Atualize a página **Detalhes do dispositivo** e assegure-se de que a
guia **Armazenamento** esteja selecionada.
2. Inspecione a seção do EVault e verifique se o tamanho selecionado durante o processo de compra do EVault é exibido próximo ao link do EVault. <br /> 
**Nota**: se o tamanho de armazenamento do EVault continuar mostrando uma capacidade de
zero, uma segunda atualização de página poderá ser necessária. 

## Acessando e visualizando detalhes de armazenamento do EVault Backup no
{{site.data.keyword.slportal}}

Os detalhes de armazenamento sobre seu serviço EVault Backup podem ser visualizados usando o
{{site.data.keyword.slportal}} a qualquer momento. Os detalhes que podem ser visualizados incluem a
senha, o endereço de armazenamento e o uso associados ao serviço EVault Backup selecionado. 

1. Para acessar a tela **Armazenamento do EVault Backup** no
[{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window},
efetue login usando suas credenciais exclusivas.
2. Clique em **Armazenamento** e selecione **Backup** na lista
suspensa.
2. Clique em qualquer lugar na linha para o EVault Backup desejado para visualizar seus detalhes de
armazenamento. Nessa visualização, a Senha não está visível. Continue com a próxima etapa para visualizar a
senha associada ao serviço EVault Backup.
3. Clique na caixa de seleção **Mostrar** ao
lado do campo **Senha** para visualizar a senha para o serviço EVault Backup.

Para muitos produtos e serviços do {{site.data.keyword.BluSoftlayer_full}}, o
recurso de armazenamento de senha no {{site.data.keyword.slportal}} é utilizado somente para armazenamento ou
rastreamento de senha e as mudanças feitas nela dentro do {{site.data.keyword.slportal}} não são
aplicadas ao produto ou ao serviço. Esse _não_ é o caso para o EVault Backup. As mudanças feitas na
senha do EVault Backup dentro do {{site.data.keyword.slportal}} serão feitas no próprio serviço. Faça
as mudanças, lembrando que elas afetarão seu serviço diretamente. Para reconfigurar sua senha, siga as etapas
em [Como mudar uma senha
do EVault Backup no {{site.data.keyword.slportal}}](/docs/infrastructure/Backup/change-password-evault-backup-service.html).

## Instalando o agente do EVault

O EVault Agent é suportado nos S.O.s a seguir:

### Windows
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

### Linux
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - Red Hat Enterprise Linux 7.x
 - Red Hat Enterprise Linux 6.x
 - Ubuntu Linux 16,04
 - Ubuntu Linux 14,04

Siga as instruções apropriadas para seu S.O.:
- [Instalando o EVault Backup Client no
Linux](install-evault-backup-client-linux.html)
- [Instalando o EVault Backup Client no
Windows](install-evault-backup-client-windows.html)
- [Instalando o EVault Backup Client para Windows
2016](install-evault-windows2016.html)

## Acessando WebCentralControl (WebCC) para backup do EVault

WebCentralControl (WebCC) é o cliente usado ao interagir com qualquer serviço EVault Backup oferecido pela {{site.data.keyword.BluSoftlayer_full}}. WebCC é um cliente baseado em navegador
que é executado em nossa rede privada que permite obter controle total de qualquer serviço EVault Backup,
incluindo configuração e restaurações. Siga estas etapas para acessar o WebCC do EVault Backup.

1. Acesse a rede privada por meio de VPN. <br/>
    **Nota**: o WebCC não pode ser acessado pela rede pública. Uma conexão VPN deve ser
estabelecida para acessar o WebCC.
2. Acesse a tela Armazenamento do EVault Backup no
[{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
3. Clique em qualquer lugar na linha do EVault Backup desejado para expandir a
visualização.
3. Clique em **Login do WebCC** para iniciar o cliente do WebCC em seu navegador.

## Configurando o agente do EVault no WebCC

Após ter solicitado seu serviço EVault e instalado o agente no servidor, é possível iniciar a criação
de backups de seus dados. Siga estas etapas para configurar seu agente e
o planejamento de retenção e iniciar sua primeira tarefa de backup.

1. Efetue login no WebCc.
2. Clique em **Todos os Agentes**> **Agentes Configurado**.
3. Clique no link **Este é um novo agente que eu gostaria de configurar**. Percorra
o processo e especifique o seguinte:
   1. Configuração do agente - forneça a descrição do agente e clique em **Avançar**.
   2. Seleção de tipo de tarefa - insira o nome da tarefa, uma descrição da tarefa e o tipo de origem de
backup e clique em **Avançar**.
   3. Seleção - selecione diretórios e clique em **Incluir...**
   4. Opções-fornecer senhas
   5. Planejamento - clique em **Incluir** para criar um planejamento e clique em
**Avançar**.
   6. Selecione a área segura padrão, clique em **OK**.
   7. Clique em **Salvar**.
4. Crie um planejamento de retenção:
   1. Selecione **Editar** > **Configurações do Agente**.
   2. Clique em **Incluir**.
   3. Preencha os detalhes de retenção.
   4. Clique em **OK**.
   5. Clique em **Salvar**.
   **Nota** - leia mais sobre como os Esquemas de retenção funcionam
[aqui](evault-backup-faq.html#how-do-the-retention-schemes-work-)
5. Execute o agente e inicie um backup.
   1. Clique em **Todos os agentes** e, em seguida, selecione o agente que você
acabou de configurar.
   2. Clique em **Executar backup**.
   3. Confirme o Destino e selecione um esquema de retenção.
   4. Clique em **Iniciar Backup**. É possível visualizar os detalhes de backups
enquanto o processo está em execução.
   5. Quando o backup estiver concluído, clique em **Fechar**.
   
**Nota**: leia mais sobre como é possível configurar backups de nível de arquivo
simples no Linux [aqui](configure-simple-file-backup-linux.html).

## O que acontece depois

Os sistemas de WebCC são totalmente documentados e o suporte para o aplicativo é acessível no WebCC. 
Clique em **Ajuda** no canto superior direito, indicado por um ponto de interrogação branco
em um círculo azul. Clique em qualquer artigo ou tópico na barra de navegação no lado esquerdo da caixa pop-up
para visualizar mais informações.


