---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-30"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Registrando um EVault

Esta tarefa é mais comumente uma etapa necessária após o recarregamento do S.O. de um servidor, no
entanto, essas etapas também podem ser usadas para [restaurar
backups de um servidor em outro servidor](restore-from-another-computer.html).

1. Efetue login como o usuário no WebCC. Consulte a
[Introdução aos serviços de backup](/docs/infrastructure/Backup/index.html) para obter
instruções. Lembre-se, WebCC é acessível apenas por meio do {{site.data.keyword.BluVPN}}.

2. À esquerda, clique em **Todos os Agentes**.

3. No canto superior direito, passe o mouse sobre **Editar**.

4. Selecione **Configurações de Segurança**.

5. Clique em **Registrar**.

6. Concluído: 
  - Segurança de nome
  - Endereço da área segura
  - Conta
  - Nome do Usuário
  - Senha. <br/>
  **Nota**: "Conta" é equivalente ao "Nome da conta" na
página [Introdução aos serviços de backup](index.html).
Normalmente, parece "SLE [ accountID ]"

7. Clique em **Carregar computadores** e selecione quais computadores deseja
carregar.

8. Clique em **Salvar Mudanças**.

9. Atualize o website para restaurar tarefas de backup anteriores.

10. Sincronize cada tarefa de backup para restaurar o histórico do conjunto de segurança. 

11. Se as tarefas de backup foram criadas usando uma senha de criptografia, deverá
inserir a senha de criptografia para restaurar dados ou continuar com os backups.

12. Clique em **Fechar** e pronto.
