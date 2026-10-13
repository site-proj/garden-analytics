# Integração diária — Garden Analytics

## Estado atual
O painel público é apenas uma interface manual; não possui ligação automática com o Reputação Garden nem com o Google.

A rotina agendada em GitHub Actions verifica o estado da configuração todo dia às 05:00 UTC (02:00 de Brasília). **Ainda não realiza coleta, comparação nem grava resultados**.

## Condições de ativação
1. Identificar um meio **autorizado e somente leitura** para consultar scans diários do site Reputação Garden. Acesso ao navegador pessoal não transfere sessão para o GitHub Actions. É preciso API, exportação autenticada, ou automação explicitamente autorizada e tecnicamente testada.
2. Obter acesso autorizado à Google Business Profile API para consultar as avaliações. Confirmar permissões e IDs necessários. Diferenciar novas avaliações de variação líquida do total.
3. Proteger tokens em segredos do GitHub Actions; nunca publicar senha, token, cookie ou CSV privado no repositório.
4. Definir armazenamento privado para histórico. **Este repositório é público; não grave aqui métricas internas ou nomes da equipe sem autorização expressa.**
5. Somente depois de validar as duas fontes ativar persistência, leitura do painel e comparar dias. Dias com coleta faltante devem aparecer como incompletos, nunca como zero.
6. Comparação é **conversão estimada**, pois algumas avaliações são espontâneas e podem ser publicadas após o scan.

## Custo
Utilizar somente recursos gratuitos com cotas compatíveis. Nenhum serviço pago deve ser habilitado sem consentimento expresso.

## Horário
05:00 UTC = 02:00 horário de Brasília (UTC−3). Execuções do GitHub Actions agendadas podem atrasar e podem ser desativadas por inatividade do repositório público.
