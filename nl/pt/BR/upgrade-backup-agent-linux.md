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

# Fazendo upgrade do agente de software de backup para Linux

É possível fazer download do agente mais recente do {{site.data.keyword.backup_notm}} na seção de links rápidos do seu Painel do portal do {{site.data.keyword.backup_notm}}.
{:tip}

Seguir o processo de upgrade assegura que é possível fazer upgrade do agente do {{site.data.keyword.backup_notm}} sem perder o registro

1. Efetue login em seu host no nível raiz.
2. Faça download da versão mais recente do agente.
   ```
   wget -N downloads.service.softlayer.com/evault/Agent-Linux-x64-8.11.5251.tar.gz2.
   ```
   {:pre}

3. Extraia o conteúdo do arquivo transferido por download.

   ```
   tar -xzvf Agent-Linux-x64-8.11.5251.tar.gz3.
   ```
4. Acesse o diretório de instalação recente
   ```
   cd Agent-Linux-x64-8.11.5251/4.
   ```

5. Execute o script de instalação.
   ```
   ./install.sh
   ```
   {:pre}

6. Responda aos prompts selecionando `N` para não registrar o computador como um novo host, selecionando seu idioma e `A` para criptografar dados usando o método de criptografia Integrado.

7. Se a instalação for bem-sucedida, ela será registrada em `/opt/BUAgent/Install.log`.
