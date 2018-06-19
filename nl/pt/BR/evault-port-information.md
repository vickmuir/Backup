---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-30"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# EVault informações da porta

O agente EVault instalado em seu servidor precisa ser capaz de se comunicar com a área segura que você
comprou. As informações do host do EVault Diretor para uma conta de usuário do EVault podem ser
localizadas no portal do cliente. Sempre registre agentes no WebCC e nos diretores do EVault usando o FQDN,
porque os IPs desses serviços podem mudar. 

Seus servidores devem se comunicar com o WebCC e com todos os servidores proxy AMP para que o WebCC
funcione corretamente, independentemente do local do data center: evregister.service.softlayer.com TCP 8086,8087. 

Servidores proxy AMP extras podem ser incluídos conforme necessário para manipular mais agentes
do EVault registrados no WebCC. 

A Porta TCP 8086, 8087 deve ter acesso a 10.0.0.0/8. 

Se você precisar usar regras de firewall mais restritivas, poderá perder o acesso ao WebCC por causa
da infraestrutura expandida. Atualmente, seus servidores devem permitir acesso pelo menos às sub-redes
10.0.82.0/24 e 10.2.118.0/24 para as portas TCP 8086, 8087. Sub-redes adicionais podem ser usadas no futuro
conforme necessário.

## Comercial:

### WebCC e servidores proxy: AMP

- ev-webcc01.service.softlayer.com [10.0.82.12] 8086, 8087
- Evregister.service.softlayer.com [ 10.0.82.12 ] 8086, 8087

### Uso AMP servidores proxy:

- Evwebamp0901.service.softlayer.com [ 10.2.118.12 ] 8087
- Evwebamp0902.service.softlayer.com [ 10.2.118.13 ] 8087
- Evwebamp0903.service.softlayer.com [ 10.2.118.14 ] 8087
- Evwebamp0904.service.softlayer.com [ 10.2.118.15 ] 8087
- Evwebamp0905.service.softlayer.com [ 10.2.118.16 ] 8087
- Evwebamp0906.service.softlayer.com [ 10.2.118.17 ] 8087
- Evwebamp0907.service.softlayer.com [ 10.2.118.18 ] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## Federal:

### Proxy WebCC e AMP:

- Webcc.service.usgov.softlayer.com [ 100.100.6.20 ] 8086, 8087
 
O agente deve permitir a porta de entrada TCP/2548 na rede privada. Isso permite que o CentralControl e
o WebCC se conectem ao agente para gerenciá-lo. Versões mais antigas do EVault usavam a porta 808.

A porta de gerenciamento do EVault (2548) pode ser mudada atualizando a chave de registro em:
HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber (que é um dword) em sistemas operacionais Windows.

**Esclarecimento adicional**: a diferença entre o uso do CentralControl de área de
trabalho e do agente com relação às configurações de conexão é sempre um ponto de confusão. O agente
residente no servidor se conecta aos servidores EVault, enquanto que o CentralControl usado pela área de
trabalho se conecta, na realidade, ao seu servidor usando esse endereço e as credenciais do servidor para
acessá-lo.
