# People Analytics: Case de Diagnóstico e Análise de Turnover

<img align="left" alt="Power BI" title="Power BI" width="30px" style="padding-right: 10px;" src="https://img.icons8.com/color/48/power-bi.png"/>

Este repositório contém um projeto de Business Intelligence focado em **People Analytics**. O objetivo é transformar dados brutos de movimentação de pessoal em um diagnóstico estratégico sobre a retenção de talentos da organização, identificando gargalos operacionais e gerando recomendações para a alta liderança.

---

##  Objetivo do Negócio

A alta taxa de rotatividade (turnover) impacta diretamente o caixa da empresa com custos de rescisão, novos processos seletivos, integração (onboarding) e perda de produtividade. Este painel foi desenhado para responder:
* Qual o tamanho real do nosso problema de turnover?
* Onde a perda de talentos está concentrada (Setor, Idade, Gênero)?
* O que está motivando os colaboradores a deixarem a empresa?

---

## 🛠️ Tecnologias e Arquitetura do Projeto

* **Processo de ETL (Power Query):** * **Extração:** Importação das tabelas brutas de movimentação de pessoal.
  * **Transformação:** Padronização dos tipos de dados (Texto/Inteiros), tratamento de valores nulos e criação de coluna condicional personalizada para segmentar a idade dos colaboradores em blocos de *Faixa Etária*, otimizando a análise demográfica.
  * **Carga:** Envio dos dados tratados para o modelo relacional do Power BI, reduzindo o volume de processamento necessário no painel.
* **Linguagem DAX:** Desenvolvimento de medidas para cálculo dinâmico de Headcount Ativo e a Taxa de Turnover:
  ```dax
  Taxa Turnover = 
  DIVIDE(
      COUNT(Desligamentos[ID_Colaborador]), 
      COUNT(Funcionarios[ID_Colaborador]), 
      0
  )

  ---

  ## 📊 Visualização

![Interface do Dashboard](./images/People%20Analytics%20-%20Dashboard%20de%20Turnover.png)
