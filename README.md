SOC Log Hunting with Splunk
Overview

This project focuses on exploring Splunk in the context of SOC analytics. The main emphasis is on log hunting: data ingestion and normalization, applying SPL queries, building metrics, and drawing conclusions.

Project Goals

Understand Splunk architecture (Forwarder, Indexer, Search Head).

Upload VPN logs and create the VPN_Logs index.

Analyze logs using SPL queries.

Extract key indicators of user and IP activity.

Prerequisites

Basic SIEM knowledge.

Access to Splunk (AttackBox/VPN).

Log file VPN_logs.

Methodology

Deployed the Splunk lab and connected via browser.

In Splunk: Add Data → Upload → VPN_logs → create index VPN_Logs.

Executed a series of SPL queries to count events and filter by UserName, Source_ip, and Source_Country.

Results

Total number of events: 2862

Events related to user Maleena: 60

Name associated with IP 107.14.182.38: Smith

Events excluding France: 2814

VPN events from IP 107.3.206.58: 14

SPL Query Examples
index="VPN_Logs" | stats count
index="VPN_Logs" UserName="Maleena" | stats count
index="VPN_Logs" Source_ip="107.14.182.38" | stats values(Name)
index="VPN_Logs" Source_Country!="France" | stats count
index="VPN_Logs" Source_ip="107.3.206.58" | stats count

Analysis

Splunk efficiently indexes and processes logs.

Filtering by users and IPs makes it easy to spot anomalies.

Geographical analysis provides insights into activity distribution.

Conclusions

This research demonstrated that Splunk is a convenient and powerful tool for SOC analytics. Even basic queries allow for extracting valuable information about user behavior and network connections. Future improvements could include building dashboards, setting up automated alerts, and correlating data from multiple sources.


SOC Log Hunting with Splunk
Visão Geral

Este projeto tem como foco a exploração do Splunk no contexto da análise de segurança em um SOC. A ênfase principal está na caça a logs: ingestão e normalização de dados, aplicação de consultas SPL, construção de métricas e elaboração de conclusões.

Objetivos do Projeto

Compreender a arquitetura do Splunk (Forwarder, Indexer, Search Head).

Carregar logs de VPN e criar o índice VPN_Logs.

Analisar logs utilizando consultas SPL.

Extrair indicadores-chave de atividade de usuários e endereços IP.

Pré-requisitos

Conhecimentos básicos de SIEM.

Acesso ao Splunk (AttackBox/VPN).

Arquivo de log VPN_logs.

Metodologia

Ambiente de laboratório do Splunk implantado e acessado via navegador.

No Splunk: Add Data → Upload → VPN_logs → criar índice VPN_Logs.

Execução de uma série de consultas SPL para contar eventos e filtrar por UserName, Source_ip e Source_Country.

Resultados

Número total de eventos: 2862

Eventos relacionados ao usuário Maleena: 60

Nome associado ao IP 107.14.182.38: Smith

Eventos excluindo a França: 2814

Eventos de VPN do IP 107.3.206.58: 14

Exemplos de Consultas SPL
index="VPN_Logs" | stats count
index="VPN_Logs" UserName="Maleena" | stats count
index="VPN_Logs" Source_ip="107.14.182.38" | stats values(Name)
index="VPN_Logs" Source_Country!="France" | stats count
index="VPN_Logs" Source_ip="107.3.206.58" | stats count

Análise

O Splunk indexa e processa logs de forma eficiente.

A filtragem por usuários e IPs permite identificar rapidamente anomalias.

A análise geográfica fornece insights sobre a distribuição das atividades.

Conclusões

A pesquisa demonstrou que o Splunk é uma ferramenta prática e poderosa para a análise em SOC. Mesmo consultas básicas permitem extrair informações valiosas sobre o comportamento dos usuários e conexões de rede. Como próximos passos, o projeto pode ser expandido com a criação de dashboards, configuração de alertas automáticos e correlação de dados de múltiplas fontes.



