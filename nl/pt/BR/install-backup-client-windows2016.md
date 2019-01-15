---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Configurando o {{site.data.keyword.backup_notm}} no Windows 2016

## Instalando o agente de backup

1. No servidor de destino, abra uma sessão do navegador e insira a URL a seguir para fazer download do
arquivo executável.
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
2. Clique duas vezes no arquivo transferido por download e clique em **Executar** na janela que aparece.
3. Selecione seu idioma para a instalação e clique em **OK**.
4. Clique em **Avançar** para começar.
5. Leia os Termos e condições e selecione **Eu aceito os termos no contrato de licença**. Em seguida, clique em **Avançar**.
6. Selecione **Típica** como o Tipo de configuração. Clique em **Avançar**.
7. Na tela Registrar o agente com o portal, selecione **Ignorar registro**. Clique em **Avançar**
8. Na próxima tela, clique em **Instalar**.
9. Quando a instalação estiver concluída, clique em **Concluir**.

## Instalando o Central Control 8.30

1. No servidor de destino, abra uma sessão do navegador e insira a URL a seguir para fazer download do
arquivo executável.

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. Clique duas vezes no arquivo transferido por download e clique em **Executar** na janela que aparece.
3. Siga as etapas de instalação para uma configuração **Típica**.
   1. Quando for solicitado para que você inclua um atalho da área de trabalho, selecione **Sim**. Clique em **Avançar**.
   2. Depois de ler o Contrato de licença de software, selecione **ACEITAR**. Clique em **Avançar**.
   3. Mantenha a pasta de destino padrão e clique em **Avançar**.
4. Quando a instalação estiver completa, marque **Ativar o EVault Software Central Control**. Clique em **Concluir**.


## Configurando o Central Control

Esta tarefa é concluída por meio de uma série de interações enquanto você está conectado ao servidor designado ao serviço {{site.data.keyword.backup_notm}}.

1. Realize o controle remoto de seu servidor por meio de RDP.
2. Inicie o controle central.
3. Na área de trabalho, clique com o botão direito em **Meu agente** e selecione **Configuração do agente**.
4. Na guia Áreas seguras, clique em **Novo**. O Assistente de Configuração de Área Segura aparece. Clique em **Avançar**.
5. Selecione **Registrar como um novo computador** e clique em
**Avançar**.
6. Insira o nome da área segura no campo Nome do perfil.

   O nome da área segura pode ser obtido do [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window}.
   {:tip}
6. Insira o endereço de rede (o endereço IP da área segura designada) e clique em **Incluir**. Em seguida, clique em **Avançar**.
7. Insira os novos valores de porta e clique em **Incluir** e, em seguida, em **Avançar**.
8. Na tela Configurações de conexão, insira o número de segundos e minutos desejados. Mantenha a caixa **Ativar a criptografia de ligação para transmissões de e para a área segura** marcada. Clique em **Avançar**.
9. Na tela de autenticação, insira as suas credenciais e clique em **Avançar**.
10. A janela Computadores registrados exibe o nome do host de seu servidor. Clique em **Avançar**.
11.	Clique em **Concluir** para concluir a configuração.


## Criando os esquemas de retenção

1. Realize o controle remoto de seu servidor por meio de RDP.
2. Inicie o controle central.
3. Na área de trabalho, clique com o botão direito em **Meu agente** e selecione **Configuração do agente**.
4. Clique na guia **Retenções**. O Assistente de retenção aparece; clique em **Avançar**.
5. Insira o nome de retenção. Clique em **Avançar**.<br/>

   A entrada pode ter 32 caracteres alfanuméricos, no máximo. Espaços não são permitidos, mas sublinhados (`_`) e traços (`-`) podem ser usados.
   {:important}
6. Insira os dias de retenção on-line e as cópias para esse tipo de retenção. Em seguida, clique em **Avançar**.<br/>

   A combinação de dias de retenção e cópias é usada para assegurar que uma duração mínima e um número de
backups sejam retidos.
   {:tip}
7. Selecione **Eu não desejo criar nenhuma cópia de backup de archive**. Clique em **Avançar**.
8. Clique em **Concluir** para concluir a configuração do esquema de retenção.


## Configurando a tarefa de backup

1. Realize o controle remoto de seu servidor por meio de RDP.
2. Inicie o controle central.
3. Na área de trabalho, clique com o botão direito em **Meu agente** e selecione **Nova tarefa**.
4. Na tela de boas-vindas, clique em **Avançar**.
5. Selecione o tipo de origem de backup.
6. Selecione **Unicode** para codificação. Clique em **Avançar**.
7. Selecione o destino ao qual essa tarefa é dirigida. Clique em **Avançar**.
8. Insira o nome para a tarefa e sua descrição.<br/>

   O nome deve ter de 1 a 30 caracteres de comprimento. O nome pode conter letras, números, sublinhados (`_`), hifens (`-`) e símbolos de dólar (`$`).
   {:important}
9. Selecione as origens de dados. Clique em **Incluir**.
10. Especifique as opções de tempo de processamento e de backup. Marque **Varredura rápida de arquivo** e insira as horas ou minutos que você deseja como o espaço de tempo de backup. Em seguida, clique em **Avançar**.
11. Selecione o tipo de criptografia (a configuração padrão é AES de 256 bits) e insira sua senha de criptografia. Clique em **Avançar**
12. Selecione as opções de log para sua tarefa. Marque **Criar arquivo de log** e selecione **Limpar somente arquivos de log expirados automaticamente**. Em seguida, clique em **Avançar**
13. Selecione **Apenas sair deste assistente** e clique em **Concluir** para concluir a configuração. A nova tarefa agora aparece sob Meu agente.


## Executando a tarefa de backup

1. Realize o controle remoto de seu servidor por meio de RDP.
2. Inicie o controle central.
3. Na área de trabalho, clique com o botão direito em **Meu agente** e selecione o agente que você criou.
4. Na tela de boas-vindas, clique em **Avançar**.
5. Selecione o destino de backup ou outro local para iniciar a tarefa de backup. Clique em **Avançar**.<br/>
   Para obter mais informações sobre múltiplas áreas seguras, consulte
[Criação de múltiplas áreas seguras](multivaulting.html)
   {:tip}
6. Selecione a opção de varredura rápida de arquivo para evitar a leitura de arquivos que não mudaram. Clique em **Avançar**.
7. Clique em **Concluir** para concluir a configuração e iniciar o backup. Aparece uma janela de informações do processo que mostra o status da tarefa de backup. Quando a tarefa de backup estiver pronta, clique em **Fechar**.
