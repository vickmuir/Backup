---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-14"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Restaurando uma imagem de volume do sistema EVault BMR 

Se você precisa restaurar um backup de imagem Bare Metal por meio do EVault, é possível restaurá-lo
rapidamente por meio do nosso sistema EVault BMR Rescue Kernel. Isso permite restaurar o sistema sem a
necessidade de um sistema operacional inicializável. Isso é muito útil quando o sistema operacional não é
mais utilizável ou quando as unidades no sistema são substituídas.

## Iniciando o sistema EVault BMR Rescue Kernel

É possível acessar o sistema EVault BMR Rescue Kernel por meio do {{site.data.keyword.slportal}}.
1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Clique em **Storage** > **Backup** 
3. Clique na **Seta** ao lado da área segura.
4. Clique em **Iniciar Restauração de Bare Metal**. Essa ação inicia uma transação
que leva alguns minutos para ser concluída. Na sequência, é possível acessar o servidor seguindo as etapas
detalhadas aqui. Você receberá um e-mail quando o sistema concluir o processo de inicialização.


## Restaurando por meio do EVault BMR Rescue Kernel

1. Quando a transação do EVault BMR Rescue Kernel é carregada, ele pode ser acessado
de duas maneiras diferentes. 
  - Um cliente VNC e o endereço IP público/privado de seu servidor e a senha que é listada no
{{site.data.keyword.slportal}} 
  - O console KVM do seu cartão de IPMI.
  Qualquer uma dessas maneiras funciona bem. 
2. Ao efetuar login no EVault BMR Rescue Kernel pela primeira vez, você é saudado com a tela
de seleção de idioma. Selecione o idioma de sua escolha e clique em **Avançar**.
<br/>![Figure 1: BMR Language selection](/images/bmr1.png)<br/> Isso exibe o
contrato de licença para o software. 
3. Se você aceitar os termos, marque a caixa de seleção e clique em **Avançar**
para continuar. <br/> Isso exibe o menu principal de restauração do sistema EVault. 
4. Para essa operação, selecione **Restaurar meu sistema**.
<br/>![Figure 2: BMR Main menu](/images/bmr2.png)
5. O assistente de restauração do sistema EVault aparece. Ela fornece uma visão geral do que será feito
e as etapas necessárias. Selecione **Avançar** para continuar
<br/>![Figure 3: BMR Wizard](/images/bmr3.png)
6. Selecione um tipo de backup para a restauração. Selecione **Software EVault** e,
em seguida, clique em **Avançar** para continuar.
7. Na tela **Local do backup**, selecione a área segura e insira o
endereço da área segura, o número da conta do EVault, além do nome de usuário e da senha da conta do EVault. Em seguida, clique em **Avançar** para continuar.
<br/>![Figure 4: Choose backup location](/images/bmr4.png)
8. Agora é necessário ver seu sistema listado nessa tela. Certifique-se de que ele esteja destacado e clique
em **Avançar**.
<br/>![Figure 5: Choose your system](/images/bmr5.png)
9. Na tela **Seleção de tarefa de backup**, selecione a tarefa
que você deseja para a restauração e clique em **Avançar**.
<br/>![Figure 6: Choose your Restore point](/images/bmr6.png)
10. No menu **Selecionar ponto de restauração**, selecione o
ponto de restauração desejado e clique em **Avançar**.
<br/>![Figure 8: Choose Restore Point](/images/bmr8.png)
11. Selecione os volumes de origem e de destino. Para restaurar a origem para o destino, arraste o
volume de origem para o volume de destino.
<br/>![Figura 9: selecione volumes de origem e de destino](/images/bmr9.png)
12. Na caixa de confirmação de formatação ou de mesclagem de dados, há duas opções. Para este artigo,
selecionamos **Formatar** para uma restauração limpa que formata o disco. Se você deseja
mesclar os dados no volume de destino, selecione **Mesclar**.
<br/>![Figure 10: Choose Merge](/images/bmr10.png)
13. Na tela principal de volume de origem e de destino. Clique em **Avançar**.
14. Na tela de resumo do plano de restauração, selecione a caixa para aceitar o plano e clique em
**Avançar**.
<br/>![Figure 11: Start the restore](/images/bmr11.png)
15. A tela de progresso de restauração aparece, mostrando o progresso da restauração conforme ela acontece.
<br/>![Figure 12: Restore Progress](/images/bmr12.png)
16. Quando concluída, é exibida uma janela de notificação informando que a restauração foi
concluída com sucesso. Clique em **OK**.
17. Na tela de progresso de restauração. Clique em **Avançar**.
18. Na tela final, selecione a caixa para reiniciar o sistema e selecione
**Concluir** e o servidor é inicializado para sua imagem de volume restaurada.
  A restauração está agora concluída. <br/>
  **Nota**: na primeira vez em que isso acontecer, a mensagem de encerramento inesperado é
exibida. Essa mensagem é completamente normal com esse tipo de backup e desaparece após a primeira
inicialização. 
