# SmartScript - Solução de geração de links parametrizados Web para APP
Em caso de dúvidas, entrar em contato com: lucas.andrade@bancobmg.com.br
Versão 1.1.0

## Objetivo
Este documento tem o objetivo trazer todas as definições e regras do SmartScript com a intenção de facilitar o entendimento do comportamento do script para todas as outras áreas. 

## Definições e Regras
Nesta seção irei resumir as regras e comportamento do smartScript para que fique claro cada alteração

### Parametros enviados
Os parâmetros abaixo sempre são enviados. Caso o usuário venha de uma origem paga os valores persistem por 30 dias em um Cookie. Sempre considerando o Last Touch Channel. Ou seja caso o usuário acesse o site por uma nova campanha o valor a ser enviado será o da ultima campanha. 
Em caso de acesso direto/organico os valores enviados são setados por padrão de acordo com o descrito abaixo.
* PID = Caso não seja paga envia a seção do site.
* Campaign = Caso não seja paga envia o pageName
* AfSub1 = Sempre passa apenas o valor já enviado (usado algumas vezes como a indicação do Cadastro - MGM)
* AfSub2 = Envia o pageName do link clicado



Já estes parametros apenas são enviados caso o usuário tenha vindo de uma campanha com estes valores preenchidos:
* DeepLinkValue = Define se o link vai abrir ou não um deeplink no APP
* Channel
* Adset
* Ad

### Janela de Atribuição
A janela de atribuição 

### Links
O SmartScript altera apenas links com um dos seguintes href:
 * .onelink.me/
 * play.google.com
 * itunes.apple.com

 

### Dominios e APP's
Cada APP tem o seu dominio próprio para que o SmartScript possa encaminhar cada usuário para o APP correto é necessário que o desenvolvedor adicione na camada de dados a marca do APP que a página deseja enviar o usuário.
Utilizando a variavel BMGDatalayer.siteInfo.brand
Seguem os valores esperados:
* Meu BMG
* Meu Galo
* Meu Vasco
* Meu Corinthians
* Meu Vozao
* Novo Mundo
* Le Biscuit

Existe uma regra que sobrepoe a regra a cima.
Ela existe com o intuito de alterar o link gerado via Target e qualquer outra razão que o time de sites acredite ser necessária. Basta enviar o valor do link já parametrizado para a variavel global window.urlAppsFlyer


