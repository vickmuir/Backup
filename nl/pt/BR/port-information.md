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

# Configurando as portas para permitir a comunicação entre o agente de backup e o WebCC

O agente do {{site.data.keyword.backup_full}} que está instalado no servidor precisa ser capaz de se
comunicar com a área segura que você comprou. As informações do host do {{site.data.keyword.backup_notm}}
Director para uma conta do usuário do {{site.data.keyword.backup_notm}} podem ser localizadas no
[{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} e no [console
do {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window}.

Sempre registre os agentes para o WebCC e os diretores do {{site.data.keyword.backup_notm}} usando o FQDN
porque os endereços IP para esses serviços podem mudar.

Seus servidores devem se comunicar com o WebCC e todos os servidores proxy AMP para que o WebCC funcione corretamente, independentemente do local do data center.

```
evregister.service.softlayer.com TCP 8086,8087
```

Os servidores proxy AMP extras podem ser incluídos conforme necessário para manipular mais agentes do {{site.data.keyword.backup_notm}} que estão registrados no WebCC.

A Porta TCP 8086, 8087 deve ter acesso a 10.0.0.0/8.

Se você precisar usar regras de firewall mais restritivas, poderá perder o acesso ao WebCC à medida que a infraestrutura for expandida. Atualmente, no mínimo, seus servidores devem permitir acesso às sub-redes 10.0.82.0/24 e 10.2.118.0/24 para as portas TCP 8086, 8087. Outras sub-redes poderão ser usadas no futuro, conforme necessário.

## Comercial

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

## Federal

*Proxy WebCC e AMP*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087

O agente deve permitir a porta de entrada TCP/2548 na rede privada. Essa configuração permite que o CentralControl e o WebCC se conectem ao agente para gerenciá-lo. Versões mais antigas do EVault usavam a porta 808.

A porta de gerenciamento do {{site.data.keyword.backup_notm}} (2548) pode ser mudada atualizando a
chave de registro em: `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (que é um `dword`) nos sistemas operacionais Windows.

Quando se trata de configurações de conexão, a diferença entre o CentralControl de área de trabalho e o Agente é frequentemente um ponto confuso.
O agente residente no servidor se conecta aos servidores do {{site.data.keyword.backup_notm}}, enquanto o
controle central utilizado na área de trabalho conecta-se ao seu servidor usando o endereço dele e as credenciais
do servidor para acessá-lo.
{:tip}
