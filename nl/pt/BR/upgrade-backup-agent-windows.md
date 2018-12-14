---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Atualizando o agente de software de backup para Windows

Use essas instruções passo a passo para atualizar o agente do {{site.data.keyword.backup_notm}} em um
servidor Windows.

1. Controle remotamente o servidor do {{site.data.keyword.BluSoftlayer_full}} que está
precisando de um upgrade do {{site.data.keyword.backup_notm}} por meio do RDP.
2. Abra um navegador e acesse o endereço a seguir.
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
3. Clique no arquivo que você deseja. (Por exemplo, Agente-Windows-x64-6-72-1072a.exe)

   O número da versão está no nome do arquivo. Escolha o mais recente. <br/>Há instaladores de 32 e 64 bits
separados. Se você tiver um sistema operacional de 64 bits,
faça download do arquivo com x64 em seu nome.
   {:tip}
4. Clique em **Executar** na tela de download e, novamente, após ele ser transferido por download.
5. Clique em **Sim** para fazer upgrade do **EVault Software Agent**.

   O instalador pode desaparecer por um minuto enquanto está carregando.
   {:note}
6. Selecione **Manter meu registro atual** e clique em
**Avançar**.
7. Clique em **Avançar**. O agente inicia o processo de upgrade. Pode levar alguns minutos.
8. Na tela de conclusão, clique em **Concluir**.
