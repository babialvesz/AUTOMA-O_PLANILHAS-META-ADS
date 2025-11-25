Automação de Relatórios Semanais do Meta Ads para Google Sheets

Este projeto contém um fluxo do n8n desenvolvido para automatizar a extração, transformação e gravação de dados do Meta Ads em uma planilha no Google Sheets. O objetivo é substituir o trabalho manual de consolidação semanal por um processo totalmente automatizado.

Objetivo

Consultar dados de campanhas no Meta Ads por período.

Normalizar e transformar os resultados retornados pela API.

Gerar agregações semanais e totais por unidade.

Atualizar automaticamente abas específicas em uma planilha do Google Sheets.

Manter o relatório sempre consistente e padronizado.

Tecnologias utilizadas

n8n

Meta Ads Insights API

Google Sheets API

JavaScript (em Code Nodes)

Descrição geral do fluxo

Cálculo do período semanal
Um script determina automaticamente o intervalo da semana anterior e gera o código de período usado no relatório.

Requisição ao Meta Ads
Os dados são obtidos da API utilizando parâmetros dinâmicos como datas e níveis de agrupamento.

Transformação dos dados
Os resultados brutos são normalizados, codificados e preparados para inserção em planilhas.

Preparação das linhas
Os dados são padronizados em campos como tipo de campanha, valores monetários e códigos.

Agregações
O fluxo gera duas tabelas:

Consolidado por semana

Gasto total por unidade

Atualização da planilha
Antes de inserir novos dados, os intervalos relevantes são limpos. Em seguida, as novas linhas são escritas nas abas correspondentes.

Configuração necessária

Antes de usar o fluxo, configure:

Variável / Credencial	Descrição
{{META_ACCESS_TOKEN}}	Token de acesso à API do Meta Ads
{{AD_ACCOUNT_ID}}	ID da conta de anúncios
{{GOOGLE_SHEET_ID}}	ID da planilha onde os dados serão escritos
{{GOOGLE_SHEETS_CREDENTIAL_ID}}	Credenciais OAuth2 do Google

Esses valores foram removidos do JSON fornecido neste repositório.

Como importar o fluxo

Abra o n8n.

Vá em Workflows → Import.

Selecione o arquivo JSON deste repositório.

Configure as credenciais ausentes.

Execute o fluxo para validar.

Uso

O workflow pode ser executado manualmente ou programado via triggers do n8n. O cálculo automático do período garante que o relatório semanal sempre reflita o intervalo correto, sem necessidade de ajustes manuais.
