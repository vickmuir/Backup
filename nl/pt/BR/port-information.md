---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configurando portas para permitir a comunicação entre o agente de backup e o portal do {{site.data.keyword.backup_notm}}

O agente do {{site.data.keyword.backup_full}} que está instalado no servidor precisa ser capaz de se
comunicar com a área segura que você comprou. As informações de host do {{site.data.keyword.backup_notm}} Director para uma conta de usuário do {{site.data.keyword.backup_notm}} podem ser localizadas no [{{site.data.keyword.slportal}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://control.softlayer.com/){:new_window} e no console do [{{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window}.

Sempre registre agentes para o portal do {{site.data.keyword.backup_notm}} e os diretores do {{site.data.keyword.backup_notm}} usando o FQDN porque os endereços IP para esses serviços podem mudar.

Seus servidores devem se comunicar com o portal do {{site.data.keyword.backup_notm}} e com todos os servidores proxy AMP para que o portal do {{site.data.keyword.backup_notm}} funcione corretamente, independentemente do local do data center.

```
evregister.service.softlayer.com TCP 8086,8087
```

É possível incluir servidores proxy AMP extras, conforme necessário, para manipular mais agentes do {{site.data.keyword.backup_notm}} que estão registrados no portal do {{site.data.keyword.backup_notm}}.

A Porta TCP 8086, 8087 deve ter acesso a 10.0.0.0/8.

Se for necessário usar regras de firewall mais restritivas, você poderá perder o acesso ao portal do {{site.data.keyword.backup_notm}}, conforme a infraestrutura for expandida. Atualmente, no mínimo, seus servidores devem permitir acesso às sub-redes 10.0.82.0/24 e 10.2.118.0/24 para as portas TCP 8086, 8087. Outras sub-redes poderão ser usadas no futuro, conforme necessário.

## Comercial

*Portal do {{site.data.keyword.backup_notm}} e servidores proxy AMP*

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

## Federal

*Portal do {{site.data.keyword.backup_notm}} e proxy AMP*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087

O agente deve permitir que a porta TCP 2548 seja a entrada na rede privada. Essa configuração permite que o CentralControl e o portal do {{site.data.keyword.backup_notm}} se conectem ao agente para gerenciá-lo. Versões mais antigas do EVault usavam a porta 808.

A porta de gerenciamento do {{site.data.keyword.backup_notm}} (2548) pode ser mudada atualizando a
chave de registro em: `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (que é um `dword`) nos sistemas operacionais Windows.

Quando se trata de configurações de conexão, a diferença entre o CentralControl de área de trabalho e o Agente é frequentemente um ponto confuso. O agente residente no servidor se conecta aos servidores do {{site.data.keyword.backup_notm}}, enquanto o
controle central utilizado na área de trabalho conecta-se ao seu servidor usando o endereço dele e as credenciais
do servidor para acessá-lo.
{:tip}
