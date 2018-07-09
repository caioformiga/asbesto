-- execute os Script .sql no banco via pgAdmin -> Tools -> Query Tool (Ctrl+E)
Passo 0: limpar todas as tabelas relacionas com EMPRESA
TB_EMPRESAS_RELACOES_delete_drop.sql

Passo 1: criar a tabela empresa e seus relacionamentos de histórico
TB_EMPRESA_create.sql


Passo 2: povoar a tabela empresa com query insert
TB_EMPRESA_query_insert_GRAD_5.sql


Passo 3: criar a view com os dados da tabela ouro filtrados na wh_rais_dados_tab_ouro
VIEW_TAB_OURO_RAIS.sql


Passo 4: criar as functions
TB_HIST_ATIVIDADE_ECONOMICA_EMPRESA_function_insert.sql
TB_HIST_MUNICIPIO_EMPRESA_function_insert.sql
TB_HIST_NATUREZA_JURIDICA_EMPRESA_function_insert.sql
TB_HIST_TAMANHO_ESTAB_function_insert.sql
TB_HIST_TIPO_ESTAB_EMPRESA_function_insert.sql
TB_EMPRESA_function_update.sql


Passo 5: povoar as tabelas de histórico usando as functions
select asbesto."INSERT_TB_HIST_ATIVIDADE_ECONOMICA_EMPRESA"()

select asbesto."INSERT_TB_HIST_MUNICIPIO_EMPRESA"()

select asbesto."INSERT_TB_HIST_NATUREZA_JURIDICA_EMPRESA"()

select asbesto."INSERT_TB_HIST_TAMANHO_ESTAB"()

select asbesto."INSERT_TB_HIST_TIPO_ESTAB_EMPRESA"()


Passo 6: atualizar a tabela empresa usando a function
select asbesto."UPDATE_TB_EMPRESA"()