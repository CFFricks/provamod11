# Documentação da Arquitetura de Dados para Streaming de Mídia

## Visão Geral

A Arquitetura foi montada para a plataforma de streaming de midia, visando escalabilidade. 

## Componentes da Arquitetura

S3: O S3 é escalável, seguro e econômico, alem disso tem integração com os outros serviços da AWS para ser feito o processamento de dados.
COGINITO IDENDITY POOL: O Cognito tem o sistema de autenticação segura, é escalavel e possui integração com o API gateway.
SPARK:Empregado para processos ETL devido à sua capacidade de processamento rápido e eficiente para grandes volumes de dados.
REDSHIFT:Redshift é ideal para análise de grandes volumes de dados, suportando consultas SQL.
Frontend no S3.

### Armazenamento de Dados

Os dados estão sendo armazenados no S3, nesse caso, eu não especifiquei como esses dados estão sendo passados, mas poderiam ser passados como csv, já que o S3 suporta esse tipo de arquivo, porem pensando em aprimorar o sistema, os dados poderiam ser passados em parquet, tornando a aplicação mais rapida.
Dados transformados e validados são armazenados no Redshift, que possui excelente performance em operações de data warehousing e análise complexa.

### Processamento de Dados

Os dados estão passando pelo Spark que vai executar o proceso de ETL, já que possui uma capacidade exelente para processamento rapido e eficientes para grandes volumes de dados (o que é o nosso casos aqui).

### Segurança e Conformidade

Descrição das medidas de segurança e como a arquitetura cumpre com as regulamentações de proteção de dados.
O Cognito gerencia a autenticação e autorização dos usuários com base em suas funções.

### Escalabilidade e Flexibilidade
Discussão sobre como a arquitetura suporta a escalabilidade e se adapta a novas demandas e tecnologias.

Alem de todos os serviços que eu escolhi terem a escalabilidade e flexibilidade alta, coloquei duas zonas da aws para aumentar a escalabilidade do serviço caso precise.

### Integração de Serviços

Explique como os diferentes serviços são integrados e orquestrados na arquitetura
Todos os serviços são da propria amazon, então eles tem essa conexão interna, mas isso causa tambem uma dependencia na AWS, então se a AWS cair, toda a aplicação cai.
