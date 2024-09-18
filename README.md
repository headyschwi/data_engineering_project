# Projeto de Engenharia de Dados de Ponta a Ponta

Este projeto demonstra um pipeline de engenharia de dados de ponta a ponta, começando pela extração de dados de um SQL Server local até a visualização no Power BI. O pipeline inclui a transformação de dados em várias camadas usando o Azure Data Factory.

## Visão Geral do Projeto

### Arquitetura
![image](https://github.com/user-attachments/assets/7a8f2559-2914-42ac-9425-da69e89e18ba)

O pipeline consiste nas seguintes etapas:

1. **Fonte de Dados (SQL Server Local)**  
   - Os dados são originados de um banco de dados SQL Server local.

2. **Extração (Azure Data Factory)**  
   - O Azure Data Factory (ADF) é usado para extrair os dados do SQL Server local para o Azure.
   
3. **Transformação e Carregamento (Databricks & Camadas do Data Lake)**  
   Os dados são transformados e carregados em três camadas distintas usando o Databricks:
   - **Camada Bronze:** Dados brutos são ingeridos nesta camada com transformação mínima.
   - **Camada Prata:** Os dados são limpos e enriquecidos, tornando-os adequados para análise.
   - **Camada Ouro:** Esta camada contém dados totalmente transformados e agregados, prontos para relatórios e análises avançadas.

4. **Visualização (Power BI)**  
   - Os dados finais são visualizados usando o Power BI para insights de negócios e relatórios.

## Stack de Tecnologia

- **SQL Server (Local):** Fonte de dados.
- **Azure Data Factory (ADF):** Extração de dados e orquestração do pipeline.
- **Databricks:** Transformação de dados e carregamento no Azure Data Lake.
- **Data Lake (Azure):** Armazenamento para dados brutos, limpos e processados.
- **Power BI:** Visualização e relatórios.

## Pipeline de Dados
![image](https://github.com/user-attachments/assets/3a135c84-54a4-48af-b28a-386455166487)

## Visualização no PowerBI
![image](https://github.com/user-attachments/assets/5fe34b2a-b84f-44bf-bbc7-59caf84a3df8)


## Instalação

Para configurar este pipeline, siga estas etapas:

1. **Configuração do SQL Server:**
   - Garanta que o SQL Server local esteja acessível.
   - Configure as regras de firewall e permissões necessárias para que o Azure Data Factory se conecte.

2. **Data Lake:**
   - Configure a conta de armazenamento e crie três camadas: `Bronze`, `Prata` e `Ouro`.

3. **Azure Data Factory:**
   - Crie uma nova instância do ADF no portal do Azure.
   - Configure os Serviços Vinculados para o SQL Server local e o Azure Data Lake.
   - Defina conjuntos de dados para a origem e o destino.
   - Crie o pipeline para extrair dados e carregá-los na camada Bronze do Data Lake.

4. **Configuração do Databricks:**
   - Crie um workspace do Databricks.
   - Configure um cluster para executar transformações.
   - Desenvolva notebooks para o seguinte:
     - Transformações de Bronze para Prata (limpeza e enriquecimento de dados).
     - Transformações de Prata para Ouro (agregação e lógica de negócios final).
   - Use jobs do Databricks para agendar e orquestrar as transformações.

5. **Power BI:**
   - Conecte o Power BI à camada Ouro do Data Lake.
   - Projete os relatórios e dashboards necessários para visualização de dados.

## Uso

1. Execute o pipeline do Azure Data Factory para extrair os dados para a camada `Bronze`.
2. Use o Databricks para transformar e mover dados através das camadas `Bronze`, `Prata` e `Ouro`.
3. Verifique os dados em cada camada.
4. Use o Power BI para visualizar os dados da camada `Ouro`.

## Estrutura do Projeto

```plaintext
├── data_engineering_project/
│   ├── Pipeline-ADF/         # Arquivos do pipeline do Azure Data Factory
│   ├── Notebooks-Databricks/ # Notebooks do Databricks para transformação de dados
│   ├── PowerBI/              # Arquivos de dashboard do Power BI
│   └── README.md             # Documentação do projeto
```
