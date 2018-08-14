---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-26"

---
{:new_window: target="_blank"}

# Configurando portas para permitir a comunicação entre o EVault Agent e o WebCC

O agente do EVault que está instalado em seu servidor precisa ser capaz de se comunicar com a área segura que você comprou. As informações do host do EVault Director para uma conta de usuário do EVault podem ser localizadas no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}. 

Sempre registre agentes para o WebCC e os diretores do EVault usando o FQDN porque os endereços IP para esses serviços podem mudar. 


```
evregister.service.softlayer.com TCP 8086,8087
```

Seus servidores devem se comunicar com o WebCC e todos os servidores proxy AMP para que o WebCC funcione corretamente, independentemente do local do data center. Servidores proxy AMP extras podem ser incluídos, conforme necessário, para manipular mais agentes do EVault que são registrados no WebCC. 

A Porta TCP 8086, 8087 deve ter acesso a 10.0.0.0/8. 

Se você precisar usar regras de firewall mais restritivas, poderá perder o acesso ao WebCC à medida que a infraestrutura for expandida. Atualmente, no mínimo, seus servidores devem permitir acesso às sub-redes 10.0.82.0/24 e 10.2.118.0/24 para as portas TCP 8086, 8087. Outras sub-redes poderão ser usadas no futuro, conforme necessário.

**Comercial**

*Servidores proxy WebCC e AMP*

- ev-webcc01.service.softlayer.com [10.0.82.12] 8086, 8087
- evregister.service.softlayer.com [10.0.82.12] 8086, 8087

*Servidores proxy AMP comerciais*

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

**Federal**

*Proxy WebCC e AMP*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087
 
O agente deve permitir a porta de entrada TCP/2548 na rede privada. Essa configuração permite que o CentralControl e o WebCC se conectem ao agente para gerenciá-lo. Versões mais antigas do EVault usavam a porta 808.

A porta de gerenciamento do EVault (2548) pode ser mudada atualizando a chave de registro em: `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (que é um `dword`) em sistemas operacionais Windows.

**Esclarecimento**. Quando se trata de configurações de conexão, a diferença entre o CentralControl de área de trabalho e o Agente é frequentemente um ponto confuso. O Agente residente no servidor se conecta aos servidores EVault, enquanto o CentralControl utilizado pela área de trabalho conecta-se ao seu servidor, usando seu endereço e as credenciais do servidor para acessá-lo.
