---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, upgrade agent, Windows

subcollection: Backup

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Fazendo upgrade do agente de software de backup para Windows
{: #UpgradeinWindows}

É possível fazer download do agente de backup mais recente da seção de links rápidos do Painel do portal do {{site.data.keyword.backup_notm}}.
{:tip}

1. Controle remotamente seu servidor {{site.data.keyword.cloud}} que está precisado de um upgrade do {{site.data.keyword.backup_notm}}.
2. Abra um navegador e acesse o endereço a seguir.
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
3. Clique no arquivo que você deseja. (Por exemplo, Agente-Windows-x64-6-72-1072a.exe)

   O número da versão está no nome do arquivo. Escolha o mais recente. O <br/>{{site.data.keyword.cloud}} oferece instaladores separados de 32 e de 64 bits. Se você tiver um sistema operacional de 64 bits,
faça download do arquivo com x64 em seu nome.
   {:tip}
4. Clique em **Executar** na tela de download e, novamente, após ele ser transferido por download.
5. Clique em **Sim** para fazer upgrade do **Agente de software do {{site.data.keyword.backup_notm}}**.

   O instalador pode desaparecer por um minuto enquanto está carregando.
   {:note}
6. Selecione **Manter meu registro atual** e clique em **Avançar**.
7. Clique em **Avançar**. O agente inicia o processo de upgrade. Pode levar alguns minutos.
8. Na tela de conclusão, clique em **Concluir**.
