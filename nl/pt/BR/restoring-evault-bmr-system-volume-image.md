---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# Restaurando uma imagem de volume do sistema EVault BMR 

Se você precisar restaurar um backup de imagem Bare Metal do EVault, será possível restaurá-lo rapidamente no sistema EVault BMR Rescue Kernel. Com o EVault BMR, é possível restaurar o sistema sem a necessidade de um sistema operacional inicializável. Isso é útil quando o sistema operacional não é mais utilizável ou quando as unidades no sistema foram substituídas.

## Iniciando o sistema EVault BMR Rescue Kernel

É possível acessar o sistema EVault BMR Rescue Kernel por meio do {{site.data.keyword.slportal}}.
1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Clique em **Armazenamento** > **Backup** 
3. Clique na **Seta** ao lado da área segura.
4. Clique em **Iniciar Restauração de Bare Metal**. Essa ação inicia uma transação
que leva alguns minutos para ser concluída. Em seguida, é possível acessar o servidor seguindo as etapas que estão detalhadas aqui. Será enviado um e-mail para você quando o sistema concluir o processo de inicialização.


## Restaurando por meio do EVault BMR Rescue Kernel

1. Quando a transação do EVault BMR Rescue Kernel for carregada, será possível optar por acessá-la de duas maneiras diferentes. 
  - Um cliente VNC e o endereço IP público/privado de seu servidor e a senha que é listada no
{{site.data.keyword.slportal}} 
  - O console KVM do seu cartão de IPMI.
  Ambas as formas funcionam bem. 
2. Ao efetuar login no EVault BMR Rescue Kernel pela primeira vez, você é saudado com a tela
de seleção de idioma. Selecione o idioma de sua escolha e clique em **Avançar**.
<br/>![Figura 1 - Seleção de idioma do BMR](/images/bmr1.png)<br/> O contrato de licença para o software é exibido. 
3. Se você aceitar os termos, marque a caixa de seleção e clique em **Avançar** para continuar. <br/> O menu principal de restauração do sistema do EVault é apresentado. 
4. Selecione **Restaurar meu sistema**.
<br/>![Figura 2 - Menu principal do BMR](/images/bmr2.png)
5. O assistente de restauração do sistema EVault aparece. Selecione **Avançar** para continuar.
<br/>![Figura 3 - Assistente do BMR](/images/bmr3.png)
6. Selecione um tipo de backup para a restauração. Selecione **Software EVault** e,
em seguida, clique em **Avançar** para continuar.
7. Na tela **Local de backup**, selecione a área segura e insira o endereço da área segura, o número da conta do EVault, o nome do usuário e a senha. Em seguida, clique em **Avançar** para continuar.
<br/>![Figura 4 - Escolher local de backup](/images/bmr4.png)
8. A próxima tela exibe seu sistema na lista. Certifique-se de que ele esteja destacado e clique em **Avançar**.
<br/>![Figura 5 - Escolha seu sistema](/images/bmr5.png)
9. Na tela **Seleção de tarefa de backup**, selecione a Tarefa da qual você deseja restaurar e clique em **Avançar**.
<br/>![Figura 6 - Escolha seu ponto de restauração](/images/bmr6.png)
10. No menu **Selecionar ponto de restauração**, selecione o ponto de restauração desejado e clique em **Avançar**.
<br/>![Figura 8 - Escolher ponto de restauração](/images/bmr8.png)
11. Selecione os volumes de origem e de destino. Para restaurar a origem para o destino, arraste o
volume de origem para o volume de destino.
<br/>![Figura 9 - Selecionar volume de origem e destino](/images/bmr9.png)
12. Na caixa de confirmação de formatação ou de mesclagem de dados, é possível selecionar dentre duas opções. Selecione **Formatar** para uma restauração limpa que formata o disco. Se você deseja
mesclar os dados no volume de destino, selecione **Mesclar**.
<br/>![Figura 10 - Escolher mesclagem](/images/bmr10.png)
13. Na tela principal de volume de origem e de destino, clique em **Avançar**.
14. Na tela de resumo do plano de restauração, selecione a caixa para aceitar o plano e clique em
**Avançar**.
<br/>![Figura 11 - Iniciar a restauração](/images/bmr11.png)
15. A tela de progresso de restauração aparece, mostrando o progresso da restauração conforme ela acontece.
<br/>![Figura 12 - Progresso da restauração](/images/bmr12.png)
16. Quando concluída, é exibida uma janela de notificação informando que a restauração foi
concluída com sucesso. Clique em **OK**.
17. Na tela de progresso de restauração. Clique em **Avançar**.
18. Na tela final, marque a caixa para reiniciar o sistema e selecione **Concluir** e o servidor carregará a imagem do volume restaurado. A restauração está agora concluída. <br/>
    >**Nota**: na primeira vez que isso acontece, é possível ver a mensagem de encerramento inesperada. É normal com esse tipo de backup e desaparece após a primeira inicialização. 
