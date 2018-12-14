---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Registando novamente uma área segura

Esta tarefa será usada mais comumente depois que o Sistema Operacional de um servidor for recarregado. Também é possível usar essas etapas para [usar backups de um servidor para restaurar dados em outro servidor](restore-from-another-computer.html).

1. Inicie o WebCC e efetue login. Para obter mais informações, consulte o [Tutorial de introdução](index.html).

   Lembre-se, WebCC é acessível apenas por meio do {{site.data.keyword.BluVPN}}.
   {:tip}
2. À esquerda, clique em **Todos os Agentes**.
3. No canto superior direito, passe o mouse sobre **Editar**.
4. Selecione **Configurações de Segurança**.
5. Clique em **Registrar**.
6. Preencha o formulário.
  - Segurança de nome
  - Endereço da área segura
  - Conta

    "Conta" é o equivalente a "Nome da conta" no [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}. Normalmente, é semelhante a "SLE[ID da conta]"
    {:tip}
  - Nome do Usuário
  - Senha
7. Clique em **Carregar computadores** e selecione os computadores que você deseja carregar.
8. Clique em **Salvar mudanças**.
9. Atualize o website para restaurar tarefas de backup anteriores.
10. Sincronize cada tarefa de backup para restaurar o histórico do conjunto de segurança.
11. Se as tarefas de backup foram criadas usando uma senha de criptografia, insira a senha de criptografia para restaurar dados ou continuar com os backups.
12. Clique em **Fechar**.
