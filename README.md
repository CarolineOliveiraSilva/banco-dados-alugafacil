# 🚗 AlugaFácil - Sistema de Gestão de Locadora de Veículos

![Status](https://img.shields.io/badge/Status-Concluído-green)
![Database](https://img.shields.io/badge/Database-MySQL-blue)
![Tools](https://img.shields.io/badge/Tools-MySQL%20Workbench-orange)

Projeto de banco de dados relacional desenvolvido para simular o ecossistema de uma locadora de veículos. O sistema gerencia todo o ciclo de vida do aluguel, desde o cadastro do cliente e frota até a devolução do veículo e cálculo de multas.

## 📋 Sobre o Projeto

Este repositório contém a modelagem e implementação de um banco de dados SQL completo. O objetivo foi aplicar conceitos avançados de **Modelagem de Dados**, **Integridade Referencial (FK/PK)** e **Otimização de Consultas (Views)**.

### Principais Funcionalidades e Regras de Negócio:
* **Controle de Frota:** Gestão de veículos por marca, modelo, placa e status.
* **Ciclo de Contrato:** Monitoramento de status (`Agendado` → `Ativo` → `Concluído`).
* **Cálculo de Multas:** Sistema automatizado que aplica uma multa de **10% sobre o valor da diária** em caso de atrasos.
* **Histórico de Devoluções:** Registro de quilometragem final e avarias (observações) no ato da entrega.
* **Relatórios Gerenciais:** Views pré-configuradas para análise financeira e operacional.

---

## 📂 Estrutura do Repositório

O projeto foi organizado para facilitar tanto o estudo passo-a-passo quanto a execução rápida:

| Arquivo | Descrição |
| :--- | :--- |
| **`alugafacil_completo_dump.sql`** | 🏆 **Arquivo Principal:** Backup completo (Estrutura + Dados + Views). Ideal para importação rápida via "Data Import". |
| `Locadora.sql` | Script DDL: Criação do Schema e das Tabelas. |
| `Script_Insert.sql` | Script DML: Povoamento inicial do banco com dados fictícios para testes. |
| `Script_update-delete.sql` | Exemplos práticos de manipulação de dados (CRUD). |
| `Script_select.sql` | Consultas complexas (JOINs) e criação das Views. |
| `diagrama.png` | Imagem do Diagrama Entidade-Relacionamento (EER). |

---

## 🚀 Como Executar o Projeto

Você tem duas opções para rodar este banco de dados na sua máquina:

### Opção A: Instalação Rápida (Recomendada)
1.  Abra o **MySQL Workbench**.
2.  Vá em **Server** > **Data Import**.
3.  Selecione **Import from Self-Contained File** e escolha o arquivo `alugafacil_completo_dump.sql`.
4.  Clique em **Start Import**.
5.  Pronto! O banco `alugafacil` será criado com tudo pronto.

### Opção B: Execução Passo a Passo (Educacional)
Se preferir rodar os scripts manualmente para entender a lógica, siga esta ordem estrita para evitar erros de chave estrangeira:
  Execute `Script_Insert.sql` (Insere dados).
  Execute `Script_select.sql` (Cria os relatórios).

---

## 📊 Relatórios Implementados (Views)

O sistema conta com "Visões" que facilitam a tomada de decisão. Após instalar, você pode consultá-las com comandos simples:

* **Relatório de Status:** Visão geral de quem alugou qual carro e qual a previsão de entrega.
    ```sql
    SELECT * FROM relatorio_status_contratos;
    ```
* **Alerta de Atrasos:** Lista automática de clientes que não devolveram o carro na data prevista.
    ```sql
    SELECT * FROM view_alerta_atrasos;
    ```
* **Resumo Financeiro:** Total arrecadado agrupado por método de pagamento.
    ```sql
    SELECT * FROM view_resumo_financeiro;
    ```

---

## ✒️ Autora

**Caroline Oliveira** 

---
*Projeto desenvolvido para fins acadêmicos.*
