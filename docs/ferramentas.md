# Ferramentas

Jus MCP expõe 270 ferramentas (todas somente leitura).

### 1. `pncp_buscar`
**Input**: `termo` (opcional), `termos` (opcional), `tipo` (opcional), `ordenacao` (opcional), `status` (opcional), `pagina` (opcional), `tam_pagina` (opcional)

Busca licitações por PALAVRA-CHAVE no objeto (cobertura NACIONAL ampla, índice full-text), em editais, atas ou contratos.

### 2. `pncp_listar`
**Input**: `termos` (opcional), `data_inicial` (opcional), `data_final` (opcional), `modalidade` (opcional), `apenas_abertas` (opcional), `uf` (opcional), `municipio` (opcional), `cnpj` (opcional), `valor_min` (opcional), `valor_max` (opcional), `ordenacao` (opcional), `tamanho_pagina` (opcional), `pagina` (opcional), `incluir_valor` (opcional), `expandir` (opcional)

Busca PRINCIPAL de licitações abertas por palavra-chave, faixa de VALOR, estado, modalidade e período.

### 3. `pncp_oportunidades`
**Input**: `termos` (opcional), `termo` (opcional), `excluir` (opcional), `data_inicial` (opcional), `data_final` (opcional), `tipo_periodo` (opcional), `valor_min` (opcional), `valor_max` (opcional), `ufs` (opcional), `modalidades` (opcional), `portais` (opcional), `superoportunidades` (opcional), `participacao_exclusiva` (opcional), `excluir_registro_preco` (opcional), `somente_sigilosos` (opcional), `itens_desertos` (opcional), `tipo_item` (opcional), `pesquisa_ampla` (opcional), `expandir` (opcional), `pagina` (opcional)

Busca de OPORTUNIDADES de licitação (editais/pregões) com filtros ricos por palavra-chave, FAIXA DE VALOR da compra, UFs, modalidades, portais, registro de preço, participação exclusiva ME/EPP e superoportunidades.

### 4. `pncp_processo`
**Input**: `id` (opcional), `ids` (opcional)

Detalhe de oportunidade(s) por `id` (de pncp_listar/pncp_oportunidades).

### 5. `pncp_detalhe`
**Input**: `cnpj`, `ano`, `sequencial`, `itens` (opcional), `resultado` (opcional)

Detalhe completo de uma licitação/contratação a partir de cnpj+ano+sequencial (a referência devolvida pela pncp_buscar).

### 6. `pncp_resultado`
**Input**: `cnpj`, `ano`, `sequencial`, `numero_item` (opcional)

Quem GANHOU a licitação: o(s) fornecedor(es) vencedor(es) homologado(s) a partir de cnpj+ano+sequencial (a referência da pncp_buscar).

### 7. `pncp_arquivos`
**Input**: `cnpj`, `ano`, `sequencial`

Documentos de uma licitação/edital (edital, termo de referência, anexos) com o LINK de download de cada arquivo (em geral PDF).

### 8. `pncp_texto`
**Input**: `cnpj`, `ano`, `sequencial`, `documento` (opcional), `de_pagina` (opcional), `ate_pagina` (opcional)

Texto INTEIRO do edital em markdown (com marcadores '## Página N'), pra você RESUMIR ou ler o documento todo.

### 9. `pncp_contratos`
**Input**: `data_inicial`, `data_final`, `cnpj_orgao` (opcional), `pagina` (opcional), `tamanho_pagina` (opcional)

Lista contratos públicos firmados num período, opcionalmente filtrando por órgão (CNPJ).

### 10. `pncp_atas`
**Input**: `data_inicial`, `data_final`, `cnpj` (opcional), `pagina` (opcional), `tamanho_pagina` (opcional)

Lista atas de registro de preços vigentes num período (referência de preços praticados pelo governo), opcionalmente por órgão (CNPJ).

### 11. `pncp_pca`
**Input**: `ano_pca`, `codigo_classificacao_superior`, `pagina` (opcional), `tamanho_pagina` (opcional)

Plano anual de contratações (PCA) por ano e classificação superior do catálogo: o que os órgãos planejam contratar no ano.

### 12. `pncp_historico`
**Input**: `termo` (opcional), `uf` (opcional), `modalidade` (opcional), `situacao` (opcional), `valor_min` (opcional), `valor_max` (opcional), `desde` (opcional), `ate` (opcional), `pagina` (opcional), `tam_pagina` (opcional)

Arquivo histórico de licitações: consulta editais que a plataforma acumulou ao longo do tempo (inclusive os que já encerraram ou saíram do ar), por PALAVRA-CHAVE no objeto, estado (UF), modalidade, situação e período…

### 13. `pncp_orgaos`
**Input**: `termo` (opcional), `termos` (opcional), `uf` (opcional), `portais` (opcional), `antecipagov` (opcional), `pagina` (opcional)

Busca de ÓRGÃOS/entidades compradoras por nome, UF e/ou portal.

### 14. `tcu_buscar`
**Input**: `termo`, `base` (opcional), `inicio` (opcional), `tamanho` (opcional)

Busca textual (por palavra-chave) na jurisprudência do TCU.

### 15. `tcu_acordaos_recentes`
**Input**: `inicio` (opcional), `quantidade` (opcional)

Lista os acórdãos mais recentes do TCU (dados abertos oficiais), paginado, sem palavra-chave: sumário, relator, colegiado, data da sessão e links.

### 16. `datajud_get_processo`
**Input**: `tribunal`, `numero_processo`

Busca um processo pelo número único do CNJ (com ou sem máscara) em um tribunal.

### 17. `datajud_search`
**Input**: `tribunal`, `classe_codigo` (opcional), `orgao_julgador_codigo` (opcional), `assunto_codigo` (opcional), `numero_processo` (opcional), `size` (opcional), `from` (opcional), `sort_desc` (opcional)

Busca processos em um tribunal por classe, órgão julgador e/ou assunto (códigos das tabelas do CNJ), paginada e ordenada por data de ajuizamento.

### 18. `datajud_movimentos`
**Input**: `tribunal`, `numero_processo`

Retorna apenas a timeline de movimentações (+ metadados) de um processo — ideal pra detectar se houve movimentação nova.

### 19. `datajud_raw_query`
**Input**: `tribunal`, `query`, `size` (opcional), `from` (opcional), `sort` (opcional), `search_after` (opcional)

Avançado: envia um corpo de query Elasticsearch cru pro índice do tribunal (escape hatch).

### 20. `calculo_atualizar`
**Input**: `parcelas`, `indice` (opcional), `data_calculo` (opcional), `taxa_juros` (opcional), `periodicidade_juros` (opcional), `juros_tipo` (opcional), `multa` (opcional), `multa_incide_sobre_juros` (opcional), `honorarios` (opcional), `honorarios_tipo` (opcional), `pro_rata` (opcional)

Atualização monetária / liquidação de débito judicial: corrige parcelas por um índice oficial (IPCA, INPC, IGP-M, SELIC, TR…) e aplica juros, multa e honorários.

### 21. `calculo_indice`
**Input**: `indice`, `data_inicial`, `data_final` (opcional), `valor` (opcional), `pro_rata` (opcional), `incluir_valores` (opcional)

Consulta de índice oficial: fator de correção acumulado entre duas datas (mês inicial excluído, mês final incluído — convenção BACEN/IBGE).

### 22. `calculo_salario_minimo`
**Input**: `ano` (opcional)

Salário mínimo nacional vigente de um ano (dinâmico, IPEADATA).

### 23. `calculo_aluguel`
**Input**: `aluguel_inicial`, `inicio_contrato`, `inicio_atraso`, `fim_atraso`, `data_calculo` (opcional), `indice` (opcional), `periodicidade_meses` (opcional), `juros` (opcional), `multa` (opcional)

Aluguéis em atraso (Lei 8.245/91): reajusta o aluguel ao longo do contrato pelo índice, corrige cada mês atrasado até hoje, aplica juros de mora (1% a.m.) e multa moratória.

### 24. `calculo_pensao`
**Input**: `forma`, `referencia`, `inicio_atraso`, `fim_atraso`, `data_calculo` (opcional), `indice` (opcional), `juros` (opcional), `pagamentos` (opcional), `remuneracoes` (opcional)

Pensão alimentícia em atraso (art.

### 25. `calculo_trabalhista`
**Input**: `salario`, `admissao`, `demissao`, `motivo` (opcional), `aviso` (opcional), `saldo_fgts` (opcional), `dependentes` (opcional), `ferias_vencidas` (opcional), `projetar_aviso` (opcional)

Verbas rescisórias / liquidação trabalhista (CLT): saldo de salário, aviso prévio indenizado (Lei 12.506/2011), 13º proporcional, férias proporcionais + 1/3, férias vencidas, multa de 40%/20% do FGTS, com descontos de…

### 26. `calculo_fgts`
**Input**: `depositos`, `data_calculo` (opcional), `indice` (opcional), `incluir_juros_3aa` (opcional)

Correção do FGTS (tese TR → INPC/IPCA-E, STF): por depósito calcula a diferença entre corrigir pelo índice de inflação vs pela TR, com juros de 3% a.a.

### 27. `calculo_dosimetria`
**Input**: `pena_min_anos`, `pena_max_anos`, `circunstancias_desfavoraveis` (opcional), `atenuantes` (opcional), `agravantes` (opcional), `causas_aumento` (opcional), `causas_diminuicao` (opcional), `fracao_fase1` (opcional), `fracao_fase2` (opcional)

Dosimetria da pena (art. 68 CP, sistema trifásico): pena-base pelas circunstâncias judiciais (art. 59), pena intermediária por atenuantes/agravantes (Súmula 231 STJ), pena definitiva por causas de aumento/diminuição (…

### 28. `calculo_progressao`
**Input**: `pena_anos`, `inicio_cumprimento`, `reincidente` (opcional), `hediondo` (opcional), `violencia` (opcional), `resultado_morte` (opcional), `dias_trabalhados` (opcional), `horas_estudo` (opcional), `dias_detracao` (opcional)

Progressão de regime (LEP art.

### 29. `calculo_partilha`
**Input**: `regime`, `bens`, `dividas` (opcional), `nomes` (opcional)

Partilha de bens no divórcio por regime (Código Civil): apura a massa partilhável (bens − dívidas conforme o regime) e a quota de cada cônjuge, com torna por desequilíbrio.

### 30. `calculo_tempo_contribuicao`
**Input**: `sexo`, `vinculos`

Tempo de contribuição (CNIS): soma os vínculos contando concomitância uma vez e converte atividade especial em comum (fatores EC 103/2019, só até 13/11/2019).

### 31. `calculo_rmi`
**Input**: `sexo`, `media_salarios`, `tempo_contribuicao_anos`, `salario_minimo` (opcional), `teto_inss` (opcional)

RMI — Renda Mensal Inicial (pós-reforma EC 103/2019): média dos salários de contribuição × coeficiente (60% + 2% por ano acima de 20H/15M), com piso (salário mínimo) e teto (INSS).

### 32. `calculo_revisional`
**Input**: `valor_financiado`, `num_parcelas`, `taxa_contratada_am`, `parcela_paga`, `sistema` (opcional), `modalidade` (opcional), `data_contrato` (opcional), `taxa_bacen_am` (opcional)

Revisional de contrato bancário: recalcula o financiamento pela taxa média de mercado do BACEN (busca ao vivo por modalidade+mês) e apura o excedente por parcela (Price ou SAC).

### 33. `calculo_superendividamento`
**Input**: `renda_liquida`, `dividas`, `minimo_existencial` (opcional), `prazo_meses` (opcional)

Superendividamento (Lei 14.181/2021): % da renda comprometida, mínimo existencial (R$600, parametrizável), renda disponível e capacidade de pagamento de um plano de até 5 anos.

### 34. `calculo_rmc_rcc`
**Input**: `beneficio_mensal`, `descontos`, `indice` (opcional), `data_calculo` (opcional), `tipo` (opcional)

RMC/RCC — reserva de margem consignável de cartão (INSS, códigos 217/268): limites de 5% e restituição corrigida dos descontos.

### 35. `calculo_restituicao_inss`
**Input**: `descontos`, `indice` (opcional), `data_calculo` (opcional)

Restituição de descontos indevidos no INSS (fraude associativa, códigos 280/304/310/378): soma as parcelas descontadas corrigidas.

### 36. `djen_search_comunicacoes`
**Input**: `numero_oab` (opcional), `uf_oab` (opcional), `nome_advogado` (opcional), `nome_parte` (opcional), `numero_processo` (opcional), `sigla_tribunal` (opcional), `data_inicio` (opcional), `data_fim` (opcional), `meio` (opcional), `texto` (opcional), `pagina` (opcional), `itens_por_pagina` (opcional)

Busca publicações/intimações no Diário de Justiça Eletrônico Nacional (DJEN) por OAB, nome de advogado, número de processo, tribunal e data.

### 37. `djen_processos_por_parte`
**Input**: `nome_parte`, `sigla_tribunal` (opcional), `data_inicio` (opcional), `data_fim` (opcional), `itens_por_pagina` (opcional), `pagina` (opcional)

DESCOBERTA por NOME de parte (grátis, sem captcha): busca o DJEN por quem figura no processo e agrupa por número — devolve a lista de processos da pessoa/empresa, com partes e tribunal.

### 38. `djen_get_certidao`
**Input**: `hash`

Retorna a URL da certidão (PDF) de uma comunicação do DJEN pelo seu hash (campo `hash` retornado na busca).

### 39. `processos_buscar_por_nome`
**Input**: `nome`, `platforms` (opcional), `tribunais` (opcional), `max_results` (opcional)

DESCOBERTA: busca processos pelo NOME de uma parte (pessoa ou empresa) raspando os portais públicos dos tribunais (ESAJ/PJe/eproc/Projudi) — o gap que datajud (só por número) e djen (OAB/advogado) não cobrem.

### 40. `processos_buscar_por_documento`
**Input**: `documento`, `platforms` (opcional), `tribunais` (opcional), `max_results` (opcional)

DESCOBERTA por CPF ou CNPJ. O serviço resolve o documento em nome(s) (CNPJ→razão social/sócios; CPF→nome) e então busca os processos por nome nos portais. ASSÍNCRONO: retorna { job_id }; faça o polling com processos_g…

### 41. `processos_obter_pecas`
**Input**: `numero_cnj`, `tribunal` (opcional), `peca_ids` (opcional), `formato` (opcional)

DOWNLOAD das DECISÕES PÚBLICAS de um processo (acórdãos/inteiro teor): busca as decisões públicas do processo, baixa o PDF e converte em Markdown (o teor da decisão), com link temporário.

### 42. `processos_get_resultado`
**Input**: `job_id`, `job_ids` (opcional)

Polling de um job de busca (de processos_buscar_por_nome/documento).

### 43. `cnpj_consultar`
**Input**: `cnpj`

Consulta cadastral de um CNPJ (grátis): razão social, nome fantasia, situação cadastral, CNAE principal, porte, município/UF e SÓCIOS (QSA).

### 44. `cnpj_processos`
**Input**: `cnpj`, `incluir_socios` (opcional)

DESCOBERTA por CNPJ: resolve o CNPJ em razão social (e sócios) e busca os processos por NOME no Diário (DJEN) — grátis, com número de processo completo.

### 45. `cpf_validar`
**Input**: `cpf`

Valida os dígitos verificadores de um CPF (mod 11) e informa se há broker de identidade disponível.

### 46. `cpf_processos`
**Input**: `cpf`, `nome` (opcional)

DESCOBERTA por CPF: busca os processos da pessoa por NOME no Diário (DJEN), grátis.

### 47. `transparencia_sancoes`
**Input**: `cpf_cnpj`

Consulta sanções de uma pessoa ou empresa por CPF/CNPJ no Portal da Transparência (consolida CEIS — inidôneas/suspensas, CNEP — empresas punidas, e CEPIM — entidades impedidas).

### 48. `transparencia_pep`
**Input**: `cpf`

Verifica se um CPF é de Pessoa Exposta Politicamente (PEP) e retorna função/órgão/período.

### 49. `transparencia_despesas_favorecido`
**Input**: `cpf_cnpj`, `mes_ano_inicio` (opcional), `mes_ano_fim` (opcional)

DESPESAS recebidas por uma empresa ou pessoa (CPF/CNPJ) do Governo Federal num período: 'quanto a empresa recebeu da União'.

### 50. `transparencia_despesas_documentos`
**Input**: `cpf_cnpj`, `ano` (opcional), `fase` (opcional), `ordenacao` (opcional), `pagina` (opcional)

Documentos de despesa (Empenho, Liquidação ou Pagamento) emitidos pelo Governo Federal para um favorecido (CPF/CNPJ) num ano, item-a-item: data, documento, espécie, valor, órgão, elemento de despesa e nº do processo.

### 51. `querido_diario_buscar`
**Input**: `termo`, `territory_ids` (opcional), `data_inicio` (opcional), `data_fim` (opcional), `size` (opcional)

Busca em diários oficiais MUNICIPAIS (milhares de prefeituras) por termo/nome — útil pra menções fora do Judiciário: licitações, nomeações, contratos, sanções municipais.

### 52. `jurisprudencia_buscar`
**Input**: `termo`, `tipo` (opcional), `max` (opcional)

Busca jurisprudência (acórdãos, súmulas, OJs) no acervo público LexML por termo/tese — cobre tribunais superiores e demais.

### 53. `jurisprudencia_sumulas`
**Input**: `termo`, `max` (opcional)

Busca SÚMULAS (incluindo vinculantes) por termo no acervo LexML.

### 54. `legal_dossie`
**Input**: `nome` (opcional), `cnpj` (opcional), `cpf` (opcional), `nome_titular` (opcional), `numero_processo` (opcional), `incluir_andamento` (opcional), `incluir_socios` (opcional), `incluir_sancoes` (opcional), `incluir_mencoes_municipais` (opcional), `max_processos` (opcional), `sigla_tribunal` (opcional)

Raio-X jurídico de uma pessoa ou empresa: descobre os processos e (opcional) o andamento, num relatório consolidado.

### 55. `legal_monitorar`
**Input**: `numero_processo` (opcional), `nome` (opcional), `cnpj` (opcional), `oab` (opcional), `uf` (opcional), `sigla_tribunal` (opcional), `intervalo_horas` (opcional), `label` (opcional)

Cria um monitoramento: avisa quando houver NOVIDADE — nova movimentação (numero_processo), novo processo de uma pessoa/empresa (nome/cnpj), ou nova publicação/intimação de uma OAB (oab+uf).

### 56. `legal_listar_monitoramentos`
**Input**: nenhum input

Lista os monitoramentos ativos do workspace.

### 57. `legal_remover_monitoramento`
**Input**: `watch_id`, `watch_ids` (opcional)

Remove (desativa) um monitoramento pelo seu id (`watch_id`).

### 58. `legal_checar_novidades`
**Input**: `watch_id` (opcional), `watch_ids` (opcional)

Checa AGORA se há novidade nos monitoramentos (sem esperar o ciclo automático).

### 59. `capivara_resolver`
**Input**: `texto` (opcional), `cnpj` (opcional), `seguir_dossie` (opcional), `nivel` (opcional)

CAMADA 1 (descoberta de identidade): a partir do que você SABE da pessoa em TEXTO LIVRE (nome, cidade, emprego, empresa, qualquer pista), descobre o CPF mais provável e devolve um PERFIL NORMALIZADO (nome, CPF, empres…

### 60. `capivara_registrar_consentimento`
**Input**: `cpf` (opcional), `cnpj` (opcional), `finalidade`, `base_legal`, `autorizacao_titular` (opcional), `observacao` (opcional)

Registra, de forma auditável (LGPD), a finalidade e a base legal de uma investigação — e, quando aplicável, a DECLARAÇÃO do usuário de que tem autorização do titular para dados sob sigilo (SCR/Bacen, cadastro positivo).

### 61. `capivara_dossie`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional), `nivel` (opcional), `formato` (opcional), `autorizacao_titular_scr` (opcional)

Raio-X cadastral 360º de uma PESSOA (por CPF) OU EMPRESA (por CNPJ) — consolidado num relatório por seção.

### 62. `jus_cenprot_sp_protestos_consultar`
**Input**: `cnpj` (opcional), `cpf` (opcional)

CENPROT SP: Protestos, consulta em fonte oficial.

### 63. `jus_certidoes_cndt`
**Input**: `cnpj` (opcional), `cpf` (opcional)

Consulta a Certidão Negativa de Débitos Trabalhistas (CNDT) por CNPJ ou CPF.

### 64. `jus_certidoes_fgts`
**Input**: `cnpj`

Consulta a regularidade do empregador perante o FGTS (Certificado de Regularidade — CRF) por CNPJ.

### 65. `jus_certidoes_pgfn`
**Input**: `cnpj` (opcional), `cpf` (opcional)

Emite/consulta a Certidão de débitos relativos a Tributos Federais e à Dívida Ativa da União (CND Federal/PGFN) por CNPJ ou CPF.

### 66. `jus_cnj_improbidade_consultar`
**Input**: `nome` (opcional), `cnpj` (opcional), `cpf` (opcional)

Conselho Nacional de Justiça: Improbidade Administrativa e Inelegibilidade, consulta em fonte oficial.

### 67. `jus_cnj_mandados_prisao_consultar`
**Input**: `nome` (opcional), `nome_mae` (opcional), `cpf` (opcional)

Conselho Nacional de Justiça: Mandados de Prisão, consulta em fonte oficial.

### 68. `jus_cnj_seeu_processos_consultar`
**Input**: `nome_parte` (opcional), `nome_mae` (opcional), `numero_processo` (opcional), `cnpj` (opcional), `cpf` (opcional)

Conselho Nacional de Justiça SEEU: Processos, consulta em fonte oficial.

### 69. `jus_cnj_serventias_extrajud_lista_consultar`
**Input**: `uf`, `municipio`

Conselho Nacional de Justiça: Serventias Extrajudiciais (Lista), consulta em fonte oficial.

### 70. `jus_cnj_serventias_extrajudiciais_consultar`
**Input**: `cns`

Conselho Nacional de Justiça: Serventias Extrajudiciais (Detalhes), consulta em fonte oficial.

### 71. `jus_compliance_antecedentes_civil`
**Input**: `CPF` (opcional), `RG` (opcional), `NOMEMAE` (opcional), `NOME` (opcional), `DATANASCIMENTO` (opcional), `GENERO` (opcional), `UF`, `completo` (opcional)

Antecedentes criminais (Polícia Civil) por CPF/nome/UF.

### 72. `jus_compliance_antecedentes_pf`
**Input**: `CPF` (opcional), `NOME` (opcional), `DATANASCIMENTO` (opcional), `NOMEMAE` (opcional), `NOMEPAI` (opcional), `completo` (opcional)

Antecedentes criminais (Polícia Federal) por CPF/nome.

### 73. `jus_compliance_antt`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `RNTRC` (opcional), `completo` (opcional)

Regularidade de transportadora na ANTT por CPF/CNPJ/RNTRC.

### 74. `jus_compliance_bacen_inabilitados`
**Input**: `CPF` (opcional), `completo` (opcional)

Banco Central — quadro geral de inabilitados, por CPF/CNPJ.

### 75. `jus_compliance_bacen_proibidos`
**Input**: `CNPJ` (opcional), `CPF` (opcional), `completo` (opcional)

Banco Central — quadro geral de proibidos, por CPF/CNPJ.

### 76. `jus_compliance_cadin`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `UF` (opcional), `completo` (opcional)

CADIN estadual (inadimplentes com a Fazenda) por CPF/CNPJ/UF.

### 77. `jus_compliance_carf`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `completo` (opcional)

Processos no CARF (Conselho Administrativo de Recursos Fiscais) por CPF/CNPJ.

### 78. `jus_compliance_ceaf`
**Input**: `CPF` (opcional), `completo` (opcional)

CEAF — expulsões da administração federal, por CPF.

### 79. `jus_compliance_ceis`
**Input**: `CNPJ` (opcional), `CPF` (opcional), `completo` (opcional)

CEIS — empresas inidôneas e suspensas, por CNPJ/CPF.

### 80. `jus_compliance_cepim`
**Input**: `CNPJ` (opcional), `completo` (opcional)

CEPIM — entidades privadas impedidas, por CNPJ.

### 81. `jus_compliance_cgu`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `TIPO`, `completo` (opcional)

Consulta de penalidades CGU por CPF/CNPJ.

### 82. `jus_compliance_cnd_municipal`
**Input**: `CNPJ` (opcional), `IM` (opcional), `CPF` (opcional), `MUNICIPIO`, `completo` (opcional)

Certidão Negativa de Débitos Municipal por CNPJ/CPF (informe o município).

### 83. `jus_compliance_cnep`
**Input**: `CNPJ` (opcional), `CPF` (opcional), `completo` (opcional)

CNEP — empresas punidas, por CNPJ/CPF.

### 84. `jus_compliance_confea_crea`
**Input**: `CPF` (opcional), `REGISTRONACIONAL` (opcional), `completo` (opcional)

Registro profissional no CONFEA/CREA (engenharia/agronomia).

### 85. `jus_compliance_cvm`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `completo` (opcional)

Cadastro na CVM (Comissão de Valores Mobiliários) por CPF/CNPJ.

### 86. `jus_compliance_cvm_sancionadores`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `completo` (opcional)

Processos administrativos sancionadores da CVM por CPF/CNPJ.

### 87. `jus_compliance_fbi`
**Input**: `NOME` (opcional), `completo` (opcional)

Busca na lista FBI Most Wanted por nome.

### 88. `jus_compliance_fincen`
**Input**: `NOME` (opcional), `completo` (opcional)

Busca na lista FINCEN por nome.

### 89. `jus_compliance_ibama_debitos`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `completo` (opcional)

Certidão negativa de débitos do IBAMA por CPF/CNPJ.

### 90. `jus_compliance_improbidade`
**Input**: `CNPJ` (opcional), `CPF` (opcional), `completo` (opcional)

CNIA — condenações por improbidade administrativa e inelegibilidade, por CNPJ/CPF.

### 91. `jus_compliance_interpol`
**Input**: `NOME` (opcional), `SOBRENOME` (opcional), `DATANASCIMENTO` (opcional), `completo` (opcional)

Busca na lista da INTERPOL por nome.

### 92. `jus_compliance_leniencia`
**Input**: `CNPJ` (opcional), `completo` (opcional)

Acordos de leniência por CNPJ.

### 93. `jus_compliance_mandados_prisao`
**Input**: `CPF` (opcional), `NOME` (opcional), `NOMEMAE` (opcional), `NOMEPAI` (opcional), `ALCUNHA` (opcional), `completo` (opcional)

CNJ — mandados de prisão em aberto, por CPF/nome.

### 94. `jus_compliance_ofac`
**Input**: `NOME` (opcional), `completo` (opcional)

Busca em listas de sanções OFAC (EUA) por nome.

### 95. `jus_compliance_onu`
**Input**: `NOME` (opcional), `completo` (opcional)

Busca na lista consolidada de sanções da ONU por nome.

### 96. `jus_compliance_pep`
**Input**: `CPF` (opcional), `completo` (opcional)

Verifica se um CPF é Pessoa Exposta Politicamente (PEP).

### 97. `jus_compliance_pep_parentescos`
**Input**: `CPF` (opcional), `completo` (opcional)

PEP estendida — pessoa exposta politicamente + parentescos.

### 98. `jus_compliance_pix`
**Input**: `DOCUMENTO`, `CHAVE`, `TIPO` (opcional), `completo` (opcional)

Antifraude de chave PIX — valida o titular de uma chave PIX.

### 99. `jus_compliance_trabalho_forcado`
**Input**: `CNPJ` (opcional), `CPF` (opcional), `completo` (opcional)

Verificação de empregador em lista de trabalho forçado/escravo, por CNPJ/CPF.

### 100. `jus_compliance_ue`
**Input**: `NOME` (opcional), `completo` (opcional)

Busca na lista de sanções financeiras da União Europeia por nome.

### 101. `jus_compliance_uk`
**Input**: `NOME` (opcional), `completo` (opcional)

Busca na lista de sanções do Reino Unido (HM Treasury) por nome.

### 102. `jus_ieptb_protestos_consultar`
**Input**: `cnpj` (opcional), `cpf` (opcional), `login_cpf` (opcional), `login_senha` (opcional), `pkcs12_cert` (opcional), `pkcs12_pass` (opcional)

IEPTB (CENPROT): Protestos, consulta em fonte oficial.

### 103. `jus_ieptb_protestos_detalhes_sp_consultar`
**Input**: `obter_detalhes`, `login_cpf` (opcional), `login_senha` (opcional), `pkcs12_cert` (opcional), `pkcs12_pass` (opcional)

IEPTB (CENPROT) Protestos: Detalhes SP, consulta em fonte oficial.

### 104. `jus_inpi_marcas_busca`
**Input**: `marca`, `ncl` (opcional), `pesquisa_textual` (opcional), `pedidos_vivos` (opcional), `tipo` (opcional), `pagina` (opcional)

Busca marcas no INPI pelo nome/termo (anterioridade/colidência).

### 105. `jus_inpi_marcas_processo`
**Input**: `numero_processo`

Detalhes completos de um processo de registro de marca no INPI pelo número do processo (situação, depósito, concessão, vigência, titulares, classes Nice/Viena, petições, publicações).

### 106. `jus_inpi_marcas_processo_resumido`
**Input**: `numero_processo`

Resumo de um processo de registro de marca no INPI pelo número do processo (marca, titular, classe, situação).

### 107. `jus_inpi_marcas_titular`
**Input**: `cnpj` (opcional), `cpf` (opcional)

Marcas registradas no INPI por titular (CPF ou CNPJ).

### 108. `jus_inpi_patentes`
**Input**: `cnpj` (opcional), `cpf` (opcional)

Patentes registradas no INPI por titular (CPF ou CNPJ).

### 109. `jus_investigacao_aml`
**Input**: `CPF` (opcional), `completo` (opcional)

Rede de vínculos societários para prevenção à lavagem de dinheiro, por CPF.

### 110. `jus_investigacao_beneficiario_final`
**Input**: `CNPJ` (opcional), `CPF` (opcional), `completo` (opcional)

Beneficiário final (UBO) de uma empresa ou pessoa.

### 111. `jus_investigacao_beneficios_sociais`
**Input**: `CPF` (opcional), `completo` (opcional)

Benefícios sociais recebidos por um CPF (Bolsa Família, BPC, etc.).

### 112. `jus_investigacao_cnh`
**Input**: `CPF` (opcional), `completo` (opcional)

Dados da CNH (Carteira Nacional de Habilitação) por CPF.

### 113. `jus_investigacao_enriquecimento`
**Input**: `CELULAR` (opcional), `EMAIL` (opcional), `completo` (opcional)

Descobre a pessoa por trás de um celular e/ou email (enriquecimento reverso).

### 114. `jus_investigacao_historico_veicular`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `completo` (opcional)

Histórico veicular (SP) por CPF ou CNPJ.

### 115. `jus_investigacao_localizacao`
**Input**: `CPF` (opcional), `NAME` (opcional), `SURNAME` (opcional), `DOB` (opcional), `completo` (opcional)

Localização de uma pessoa (nome, endereço, telefone, email).

### 116. `jus_investigacao_obito`
**Input**: `CPF` (opcional), `completo` (opcional)

Verificação de óbito por CPF.

### 117. `jus_investigacao_participacoes`
**Input**: `CNPJ` (opcional), `completo` (opcional)

QSA + participações societárias de um CNPJ (sócios e empresas ligadas).

### 118. `jus_investigacao_pessoa_fisica`
**Input**: `CPF` (opcional), `completo` (opcional)

Dados cadastrais completos de um CPF: nome, contato (telefone/email), endereço, renda estimada e faixa salarial.

### 119. `jus_investigacao_pessoa_juridica`
**Input**: `CNPJ` (opcional), `completo` (opcional)

Dados cadastrais completos de um CNPJ.

### 120. `jus_investigacao_pis`
**Input**: `CPF` (opcional), `completo` (opcional)

PIS vinculado a um CPF.

### 121. `jus_investigacao_prf_infracoes`
**Input**: `PLACA`, `RENAVAM`, `TIPO`, `completo` (opcional)

Infrações da Polícia Rodoviária Federal por placa + RENAVAM.

### 122. `jus_investigacao_propriedade_veicular`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `completo` (opcional)

Veículos no nome de uma pessoa ou empresa (frota) por CPF/CNPJ.

### 123. `jus_investigacao_renda`
**Input**: `CPF` (opcional), `completo` (opcional)

Nível socioeconômico e renda estimada de um CPF.

### 124. `jus_investigacao_situacao_eleitoral`
**Input**: `NOME` (opcional), `CPF` (opcional), `NUMEROTITULOELEITORAL` (opcional), `DATANASCIMENTO` (opcional), `completo` (opcional)

Situação eleitoral de uma pessoa (TSE).

### 125. `jus_investigacao_titulo_eleitoral`
**Input**: `NOME` (opcional), `CPF` (opcional), `NUMEROTITULOELEITORAL` (opcional), `DATANASCIMENTO`, `NOMEMAE`, `completo` (opcional)

Título e local de votação (TSE).

### 126. `jus_investigacao_veiculo_placa`
**Input**: `PLACA` (opcional), `completo` (opcional)

Dados e débitos de um veículo pela placa (não exige RENAVAM).

### 127. `jus_investigacao_vinculo_empregaticio`
**Input**: `CNPJ` (opcional), `completo` (opcional)

Vínculos empregatícios.

### 128. `jus_investigacao_vinculos_societarios`
**Input**: `CNPJ` (opcional), `CPF` (opcional), `completo` (opcional)

Vínculos/relacionamentos societários de uma pessoa ou empresa.

### 129. `jus_mp_sp_inquerito_civil_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `nome` (opcional), `nome_exato` (opcional), `pagina` (opcional), `numero_mp` (opcional)

Ministério Público SP: Inquérito Civil, consulta em fonte oficial.

### 130. `jus_mpf_amazonia_protege_consultar`
**Input**: `cnpj` (opcional), `cpf` (opcional)

MPF: Amazônia Protege, consulta em fonte oficial.

### 131. `jus_mpf_certidao_negativa_consultar`
**Input**: `cnpj` (opcional), `cpf` (opcional)

MPF: Certidão Negativa, consulta em fonte oficial.

### 132. `jus_mpf_processos_consultar`
**Input**: `query`

MPF: Processos, consulta em fonte oficial.

### 133. `jus_mpt_ac_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT AC e RO: Certidão Negativa de Feitos, consulta em fonte oficial.

### 134. `jus_mpt_al_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT AL: Certidão Negativa de Feitos, consulta em fonte oficial.

### 135. `jus_mpt_am_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT AM e RR: Certidão Negativa de Feitos, consulta em fonte oficial.

### 136. `jus_mpt_ap_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT AP e PA: Certidão Negativa de Feitos, consulta em fonte oficial.

### 137. `jus_mpt_ba_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT BA: Certidão Negativa de Feitos, consulta em fonte oficial.

### 138. `jus_mpt_ce_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT CE: Certidão Negativa de Feitos, consulta em fonte oficial.

### 139. `jus_mpt_cnf_unificada_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `uf`

MPT Unificada: Certidão Negativa de Feitos, consulta em fonte oficial.

### 140. `jus_mpt_df_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT DF e TO: Certidão Negativa de Feitos, consulta em fonte oficial.

### 141. `jus_mpt_es_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT ES: Certidão Negativa de Feitos, consulta em fonte oficial.

### 142. `jus_mpt_go_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT GO: Certidão Negativa de Feitos, consulta em fonte oficial.

### 143. `jus_mpt_ma_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT MA: Certidão Negativa de Feitos, consulta em fonte oficial.

### 144. `jus_mpt_mg_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT MG: Certidão Negativa de Feitos, consulta em fonte oficial.

### 145. `jus_mpt_ms_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT MS: Certidão Negativa de Feitos, consulta em fonte oficial.

### 146. `jus_mpt_mt_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT MT: Certidão Negativa de Feitos, consulta em fonte oficial.

### 147. `jus_mpt_pb_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT PB: Certidão Negativa de Feitos, consulta em fonte oficial.

### 148. `jus_mpt_pe_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT PE: Certidão Negativa de Feitos, consulta em fonte oficial.

### 149. `jus_mpt_pi_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT PI: Certidão Negativa de Feitos, consulta em fonte oficial.

### 150. `jus_mpt_pr_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT PR: Certidão Negativa de Feitos, consulta em fonte oficial.

### 151. `jus_mpt_rj_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT RJ: Certidão Negativa de Feitos, consulta em fonte oficial.

### 152. `jus_mpt_rn_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT RN: Certidão Negativa de Feitos, consulta em fonte oficial.

### 153. `jus_mpt_rs_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT RS: Certidão Negativa de Feitos, consulta em fonte oficial.

### 154. `jus_mpt_sc_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT SC: Certidão Negativa de Feitos, consulta em fonte oficial.

### 155. `jus_mpt_se_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT SE: Certidão Negativa de Feitos, consulta em fonte oficial.

### 156. `jus_mpt_sp_campinas_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT SP Campinas: Certidão Negativa de Feitos, consulta em fonte oficial.

### 157. `jus_mpt_sp_cnf_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

MPT SP: Certidão Negativa de Feitos, consulta em fonte oficial.

### 158. `jus_onr_mapa_registro_imoveis_consultar`
**Input**: `camada`, `hash_endereco` (opcional), `car` (opcional)

ONR: Mapa do Registro de Imóveis, consulta em fonte oficial.

### 159. `jus_registradores_certid_download_consultar`
**Input**: `email` (opcional), `senha` (opcional), `pkcs12_cert` (opcional), `pkcs12_pass` (opcional), `tipo_login` (opcional), `numero_pedido` (opcional)

Registradores (ARISP) Certidão: Download de Certidão Digital, consulta em fonte oficial.

### 160. `jus_registradores_certid_pedido_consultar`
**Input**: `email` (opcional), `senha` (opcional), `pkcs12_cert` (opcional), `pkcs12_pass` (opcional), `tipo_login` (opcional), `uf`, `municipio`, `cartorio`, `tipo_certidao`, `matricula`

Registradores (ARISP) Certidão: Novo Pedido de Certidão Digital, consulta em fonte oficial.

### 161. `jus_registradores_certid_recibo_consultar`
**Input**: `email` (opcional), `senha` (opcional), `pkcs12_cert` (opcional), `pkcs12_pass` (opcional), `tipo_login` (opcional), `numero_pedido` (opcional)

Registradores (ARISP) Certidão: Download de Recibo, consulta em fonte oficial.

### 162. `jus_registradores_info_conta_consultar`
**Input**: `email` (opcional), `senha` (opcional), `pkcs12_cert` (opcional), `pkcs12_pass` (opcional), `tipo_login` (opcional)

Registradores (ARISP): Consulta de Informações da Conta, consulta em fonte oficial.

### 163. `jus_registradores_matric_download_consultar`
**Input**: `email` (opcional), `senha` (opcional), `pkcs12_cert` (opcional), `pkcs12_pass` (opcional), `tipo_login` (opcional), `numero_pedido` (opcional)

Registradores (ARISP) Matrícula: Download de Matrícula, consulta em fonte oficial.

### 164. `jus_registradores_matric_lista_consultar`
**Input**: `email` (opcional), `senha` (opcional), `pkcs12_cert` (opcional), `pkcs12_pass` (opcional), `tipo_login` (opcional)

Registradores (ARISP) Matrícula: Lista de Pedidos, consulta em fonte oficial.

### 165. `jus_registradores_matric_pedido_consultar`
**Input**: `email` (opcional), `senha` (opcional), `pkcs12_cert` (opcional), `pkcs12_pass` (opcional), `tipo_login` (opcional), `matricula`, `uf`, `municipio`, `cartorio`, `finalidade`

Registradores (ARISP) Matrícula: Novo Pedido de Visualização de Matrícula, consulta em fonte oficial.

### 166. `jus_registradores_matric_recibo_consultar`
**Input**: `email` (opcional), `senha` (opcional), `pkcs12_cert` (opcional), `pkcs12_pass` (opcional), `tipo_login` (opcional), `numero_pedido` (opcional)

Registradores (ARISP) Matrícula: Download de Recibo, consulta em fonte oficial.

### 167. `jus_registro_civil_val_cert_eletr_consultar`
**Input**: `codigo_certidao`

Registro Civil: Validar Certidão Eletrônica, consulta em fonte oficial.

### 168. `jus_tribunal_stj_certidao_negativa_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

Tribunal STJ: Certidão Negativa, consulta em fonte oficial.

### 169. `jus_tribunal_tjba_primeiro_grau_consultar`
**Input**: `nome` (opcional), `naturalidade` (opcional), `cpf` (opcional), `rg` (opcional), `orgao_expedidor` (opcional), `estado_civil` (opcional), `endereco` (opcional), `filiacao_1` (opcional), `razao_social` (opcional), `cnpj` (opcional), `tipo_certidao` (opcional), `tipo_participacao` (opcional)

Tribunal TJBA: Certidão do 1º Grau, consulta em fonte oficial.

### 170. `jus_tribunal_tjdf_nada_consta_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `primeiro_nome` (opcional), `nome_mae` (opcional), `nome_pai` (opcional), `tipo_certidao`

Tribunal TJDF: Nada Consta, consulta em fonte oficial.

### 171. `jus_tribunal_tjgo_nada_consta_consultar`
**Input**: `tipo_certidao`, `cnpj` (opcional), `cpf` (opcional), `razao_social` (opcional), `nome` (opcional), `nome_mae` (opcional), `birthdate` (opcional)

Tribunal TJGO: Nada Consta, consulta em fonte oficial.

### 172. `jus_tribunal_tjma_nada_consta_consultar`
**Input**: `instancia`, `natureza`, `cpf`, `nome`, `birthdate`, `nome_mae`, `nome_pai` (opcional)

Tribunal TJMA: Nada Consta, consulta em fonte oficial.

### 173. `jus_tribunal_tjmg_processo_consultar`
**Input**: `numero_processo` (opcional), `cpf` (opcional), `cnpj` (opcional), `nome_parte` (opcional), `nome_advogado` (opcional)

Tribunal TJMG: Processo, consulta em fonte oficial.

### 174. `jus_tribunal_tjms_obter_certidao_consultar`
**Input**: `numero_pedido`, `cpf` (opcional), `cnpj` (opcional), `data_pedido`

Tribunal TJMS: Conferência de Certidão, consulta em fonte oficial.

### 175. `jus_tribunal_tjms_pedido_cert_consultar`
**Input**: `comarca`, `modelo`, `nome_razao_social`, `cpf` (opcional), `cnpj` (opcional), `rg` (opcional), `genero` (opcional), `nome_pai` (opcional), `nome_mae` (opcional), `birthdate` (opcional), `email`

Tribunal TJMS: Cadastro de Pedido de Certidão (1º grau), consulta em fonte oficial.

### 176. `jus_tribunal_tjmt_primeiro_grau_pf_consultar`
**Input**: `cpf`, `birthdate`, `tipo_certidao`

Tribunal TJMT: Certidão do 1º Grau (Pessoa Física), consulta em fonte oficial.

### 177. `jus_tribunal_tjpa_cert_criminal_consultar`
**Input**: `nome_requerente`, `nome_mae`, `endereco`, `rg` (opcional), `cpf` (opcional), `orgao_emissor_rg` (opcional), `uf_emissor_rg` (opcional)

Tribunal TJPA: Certidão Criminal, consulta em fonte oficial.

### 178. `jus_tribunal_tjpr_processo_consultar`
**Input**: `numero_processo` (opcional), `nome_juizo` (opcional), `instancia` (opcional), `tipo_competencia` (opcional), `orgao_julgador` (opcional), `cpf` (opcional), `cnpj` (opcional), `nome_comarca` (opcional), `nome_parte` (opcional), `nome_advogado` (opcional), `oab` (opcional), `oab_complemento` (opcional), `oab_uf` (opcional)

Tribunal TJPR: Processo, consulta em fonte oficial.

### 179. `jus_tribunal_tjrj_obter_certidao_consultar`
**Input**: `numero_requerimento`

Tribunal TJRJ: Visualizar Certidão, consulta em fonte oficial.

### 180. `jus_tribunal_tjrj_pedido_cert_consultar`
**Input**: `nome`, `cpf` (opcional), `cnpj` (opcional), `email`, `tipo_certidao`, `comarca`, `finalidade`, `inscricao_imovel` (opcional), `endereco` (opcional), `numero_endereco` (opcional), `complemento_endereco` (opcional), `bairro` (opcional)

Tribunal TJRJ: Cadastro de Pedido de Certidão, consulta em fonte oficial.

### 181. `jus_tribunal_tjrj_processo_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `oab` (opcional), `nome_advogado` (opcional), `origem` (opcional), `comarca_regional` (opcional), `competencia` (opcional), `ano_inicial` (opcional), `ano_final` (opcional), `numero_processo` (opcional)

Tribunal TJRJ: Processo, consulta em fonte oficial.

### 182. `jus_tribunal_tjrj_processo_eproc_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `numero_processo` (opcional), `nome` (opcional), `oab` (opcional)

Tribunal TJRJ: Processo (eproc), consulta em fonte oficial.

### 183. `jus_tribunal_tjrs_primeiro_grau_consultar`
**Input**: `tipo_certidao`, `nacionalidade` (opcional), `cpf` (opcional), `rg` (opcional), `orgao_expedidor_rg` (opcional), `uf_rg` (opcional), `genero` (opcional), `nome_mae` (opcional), `nome_pai` (opcional), `birthdate` (opcional), `cnpj` (opcional), `estado_civil` (opcional), `nome`, `endereco`

Tribunal TJRS: Certidão do 1º Grau, consulta em fonte oficial.

### 184. `jus_tribunal_tjsc_obter_certidao_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `numero_pedido`

Tribunal TJSC: Visualizar Certidão, consulta em fonte oficial.

### 185. `jus_tribunal_tjsc_pedido_certidao_consultar`
**Input**: `instancia`, `tipo`, `finalidade_certidao` (opcional), `nome`, `cpf` (opcional), `cnpj` (opcional), `rg` (opcional), `orgao_expedidor` (opcional), `uf`, `municipio`, `email`, `nome_mae` (opcional), `nome_pai` (opcional), `birthdate` (opcional), `login_cpf` (opcional), `login_senha` (opcional), `pkcs12_cert` (opcional), `pkcs12_pass` (opcional)

Tribunal TJSC: Pedido de Certidão, consulta em fonte oficial.

### 186. `jus_tribunal_tjsc_processo_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `numero_processo` (opcional), `nome` (opcional), `oab` (opcional)

Tribunal TJSC: Processo, consulta em fonte oficial.

### 187. `jus_tribunal_tjsp_colegio_recursal_consultar`
**Input**: `numero_processo` (opcional), `nome_parte` (opcional), `rg` (opcional), `cpf` (opcional), `nome_advogado` (opcional), `oab` (opcional), `secao` (opcional), `pagina` (opcional)

Tribunal TJSP: Colégio Recursal e Turma de Uniformização, consulta em fonte oficial.

### 188. `jus_tribunal_tjsp_eproc_lista_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `nome_parte` (opcional), `oab` (opcional)

Tribunal TJSP: Lista de Processos (eproc), consulta em fonte oficial.

### 189. `jus_tribunal_tjsp_eproc_unificada_consultar`
**Input**: `numero_processo`

Tribunal TJSP: Consulta Processual Unificada (Eproc), consulta em fonte oficial.

### 190. `jus_tribunal_tjsp_obter_cert_1grau_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `numero_pedido`

Tribunal TJSP: Download da Certidão de 1º Grau, consulta em fonte oficial.

### 191. `jus_tribunal_tjsp_obter_certidao_consultar`
**Input**: `numero_pedido`, `cpf` (opcional), `cnpj` (opcional), `pedido_data` (opcional)

Tribunal TJSP: Visualizar Certidão, consulta em fonte oficial.

### 192. `jus_tribunal_tjsp_pedido_certidao_consultar`
**Input**: `modelo`, `email_envio`, `nome_completo` (opcional), `cpf` (opcional), `rg` (opcional), `cin` (opcional), `razao_social` (opcional), `cnpj` (opcional), `genero` (opcional), `nome_mae` (opcional), `nome_pai` (opcional), `birthdate` (opcional), `naturalidade_municipio` (opcional), `naturalidade_uf` (opcional)

Tribunal TJSP: Cadastro de Pedido de Certidão, consulta em fonte oficial.

### 193. `jus_tribunal_tjsp_pedido_civel_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `nome` (opcional), `razao_social` (opcional), `instancia` (opcional), `email`, `finalidade`, `pais` (opcional), `uf` (opcional), `municipio` (opcional), `login_cpf` (opcional), `login_senha` (opcional), `pkcs12_cert` (opcional), `pkcs12_pass` (opcional)

Tribunal TJSP: Certidão Cível de 1º Grau, consulta em fonte oficial.

### 194. `jus_tribunal_tjsp_pedido_criminal_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `nome` (opcional), `razao_social` (opcional), `email`, `finalidade`, `pais` (opcional), `uf` (opcional), `municipio` (opcional), `login_cpf` (opcional), `login_senha` (opcional), `pkcs12_cert` (opcional), `pkcs12_pass` (opcional)

Tribunal TJSP: Certidão Criminal de 1º Grau, consulta em fonte oficial.

### 195. `jus_tribunal_tjsp_primeiro_grau_consultar`
**Input**: `processo` (opcional), `parte` (opcional), `cpf` (opcional), `cnpj` (opcional), `rg` (opcional), `advogado` (opcional), `oab` (opcional), `carta_precatoria` (opcional), `documento_delegacia` (opcional), `cda` (opcional), `pagina` (opcional)

Tribunal TJSP: Processos do 1º Grau, consulta em fonte oficial.

### 196. `jus_tribunal_tjsp_segundo_grau_consultar`
**Input**: `numero_processo` (opcional), `nome_parte` (opcional), `cpf` (opcional), `cnpj` (opcional), `rg` (opcional), `advogado` (opcional), `oab` (opcional), `carta_precatoria` (opcional), `documento_delegacia` (opcional), `pagina` (opcional)

Tribunal TJSP: Processos do 2º Grau, consulta em fonte oficial.

### 197. `jus_tribunal_tjsp_selo_digital_consultar`
**Input**: `selo`

Tribunal TJSP: Selo Digital, consulta em fonte oficial.

### 198. `jus_tribunal_tjto_cert_judicial_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `competencia` (opcional), `nome` (opcional)

Tribunal TJTO: Certidão Judicial, consulta em fonte oficial.

### 199. `jus_tribunal_trf_cert_unificada_consultar`
**Input**: `tipo`, `cpf` (opcional), `cnpj` (opcional), `nome_social` (opcional), `email`

Tribunal TRF: Certidão Unificada da Justiça Federal, consulta em fonte oficial.

### 200. `jus_tribunal_trf1_certidao_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `tipo`, `orgao` (opcional), `considera_filiais` (opcional)

Tribunal TRF1: Certidão Negativa Cível e Criminal, consulta em fonte oficial.

### 201. `jus_tribunal_trf1_processo_consultar`
**Input**: `processo` (opcional), `parte` (opcional), `cpf` (opcional), `cnpj` (opcional), `advogado` (opcional), `oab` (opcional)

Tribunal TRF1: Processo, consulta em fonte oficial.

### 202. `jus_tribunal_trf2_certidao_consultar`
**Input**: `cpf` (opcional), `birthdate` (opcional), `cnpj` (opcional), `tipo_certidao`

Tribunal TRF2: Certidão Negativa Cível e Criminal, consulta em fonte oficial.

### 203. `jus_tribunal_trf2_processo_consultar`
**Input**: `numero_processo` (opcional), `oab` (opcional), `cpf` (opcional), `cnpj` (opcional), `nome_parte` (opcional)

Tribunal TRF2: Processo, consulta em fonte oficial.

### 204. `jus_tribunal_trf2_processo_eproc_consultar`
**Input**: `numero_processo` (opcional), `oab` (opcional), `cpf` (opcional), `cnpj` (opcional), `nome_parte` (opcional)

Tribunal TRF2: Processo (eproc), consulta em fonte oficial.

### 205. `jus_tribunal_trf3_certidao_distr_consultar`
**Input**: `abrangencia` (opcional), `tipo` (opcional), `cpf` (opcional), `cnpj` (opcional), `nome` (opcional), `razao_social` (opcional), `nome_social` (opcional), `nome_mae` (opcional), `birthdate` (opcional), `tipo_documento` (opcional), `documento` (opcional), `endereco` (opcional), `tipo_telefone` (opcional), `telefone` (opcional)

Tribunal TRF3: Certidão de Distribuição, consulta em fonte oficial.

### 206. `jus_tribunal_trf3_consulta_publica_consultar`
**Input**: `numero_processo` (opcional), `nome_parte` (opcional), `nome_advogado` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRF3: Consulta Pública, consulta em fonte oficial.

### 207. `jus_tribunal_trf3_obter_certidao_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `numero_certidao`

Tribunal TRF3: Obter Certidão de Distribuição, consulta em fonte oficial.

### 208. `jus_tribunal_trf3_processo_consultar`
**Input**: `numero_processo` (opcional), `processo_origem` (opcional), `uf_origem` (opcional), `cidade_origem` (opcional), `cpf` (opcional), `cnpj` (opcional), `nome_parte` (opcional), `oab` (opcional), `nome_advogado` (opcional), `data_inicio_autuacao` (opcional), `data_final_autuacao` (opcional)

Tribunal TRF3: Processo, consulta em fonte oficial.

### 209. `jus_tribunal_trf4_certidao_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `birthdate` (opcional), `tipo`

Tribunal TRF4: Certidão Negativa Cível e Criminal, consulta em fonte oficial.

### 210. `jus_tribunal_trf5_certidao_consultar`
**Input**: `tipo_certidao`, `cpf` (opcional), `cnpj` (opcional), `birthdate` (opcional), `orgao` (opcional)

Tribunal TRF5: Certidão Negativa Cível e Criminal, consulta em fonte oficial.

### 211. `jus_tribunal_trf5_processo_consultar`
**Input**: `processo` (opcional), `originario` (opcional), `parte_advogado` (opcional), `cpf` (opcional), `cnpj` (opcional), `oab` (opcional), `oab_uf` (opcional)

Tribunal TRF5: Processo, consulta em fonte oficial.

### 212. `jus_tribunal_trf6_certidao_consultar`
**Input**: `tipo_certidao`, `orgao` (opcional), `considera_filiais` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRF6: Certidão Negativa Cível e Criminal, consulta em fonte oficial.

### 213. `jus_tribunal_trf6_processo_consultar`
**Input**: `numero_processo` (opcional), `nome_parte` (opcional), `nome_advogado` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRF6: Processo, consulta em fonte oficial.

### 214. `jus_tribunal_trt_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT: Consulta Processual Unificada, consulta em fonte oficial.

### 215. `jus_tribunal_trt1_ceat_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT1: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 216. `jus_tribunal_trt1_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT1: Consulta Processual, consulta em fonte oficial.

### 217. `jus_tribunal_trt10_ceat_consultar`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT10: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 218. `jus_tribunal_trt10_ceat_digital_consultar`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT10: Certidão Eletrônica de Ações Trabalhistas (CEAT) - Processos Digitais, consulta em fonte oficial.

### 219. `jus_tribunal_trt10_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT10: Consulta Processual, consulta em fonte oficial.

### 220. `jus_tribunal_trt11_ceat_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT11: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 221. `jus_tribunal_trt11_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT11: Consulta Processual, consulta em fonte oficial.

### 222. `jus_tribunal_trt12_ceat_consultar`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT12: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 223. `jus_tribunal_trt12_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT12: Consulta Processual, consulta em fonte oficial.

### 224. `jus_tribunal_trt13_ceat_consultar`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT13: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 225. `jus_tribunal_trt13_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT13: Consulta Processual, consulta em fonte oficial.

### 226. `jus_tribunal_trt14_ceat_consultar`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT14: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 227. `jus_tribunal_trt14_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT14: Consulta Processual, consulta em fonte oficial.

### 228. `jus_tribunal_trt15_ceat_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `nome` (opcional)

Tribunal TRT15: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 229. `jus_tribunal_trt15_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT15: Consulta Processual, consulta em fonte oficial.

### 230. `jus_tribunal_trt16_ceat_consultar`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT16: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 231. `jus_tribunal_trt16_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT16: Consulta Processual, consulta em fonte oficial.

### 232. `jus_tribunal_trt17_ceat_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `nome_completo` (opcional)

Tribunal TRT17: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 233. `jus_tribunal_trt17_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT17: Consulta Processual, consulta em fonte oficial.

### 234. `jus_tribunal_trt18_ceat_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `nome_requerente`, `cpf_requerente`

Tribunal TRT18: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 235. `jus_tribunal_trt18_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT18: Consulta Processual, consulta em fonte oficial.

### 236. `jus_tribunal_trt19_ceat_consultar`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT19: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 237. `jus_tribunal_trt19_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT19: Consulta Processual, consulta em fonte oficial.

### 238. `jus_tribunal_trt2_ceat_consultar`
**Input**: `nome`, `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT2: Certidão Eletrônica de Ações Trabalhistas (CEAT) - Processos Físicos, consulta em fonte oficial.

### 239. `jus_tribunal_trt2_ceat_digital_consultar`
**Input**: `cpf` (opcional), `cnpj_raiz` (opcional)

Tribunal TRT2: Certidão Eletrônica de Ações Trabalhistas (CEAT) - Processos Digitais, consulta em fonte oficial.

### 240. `jus_tribunal_trt2_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT2: Consulta Processual, consulta em fonte oficial.

### 241. `jus_tribunal_trt20_ceat_consultar`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT20: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 242. `jus_tribunal_trt20_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT20: Consulta Processual, consulta em fonte oficial.

### 243. `jus_tribunal_trt21_ceat_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT21: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 244. `jus_tribunal_trt21_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT21: Consulta Processual, consulta em fonte oficial.

### 245. `jus_tribunal_trt22_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT22: Consulta Processual, consulta em fonte oficial.

### 246. `jus_tribunal_trt23_ceat_consultar`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT23: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 247. `jus_tribunal_trt24_ceat_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `cpf_solicitante`

Tribunal TRT24: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 248. `jus_tribunal_trt24_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT24: Consulta Processual, consulta em fonte oficial.

### 249. `jus_tribunal_trt3_ceat_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT3: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 250. `jus_tribunal_trt4_ceat_consultar`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT4: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 251. `jus_tribunal_trt4_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT4: Consulta Processual, consulta em fonte oficial.

### 252. `jus_tribunal_trt5_ceat_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT5: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 253. `jus_tribunal_trt5_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT5: Consulta Processual, consulta em fonte oficial.

### 254. `jus_tribunal_trt6_certidao_consultar`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT6: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 255. `jus_tribunal_trt6_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT6: Consulta Processual, consulta em fonte oficial.

### 256. `jus_tribunal_trt7_ceat_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `nome` (opcional)

Tribunal TRT7: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 257. `jus_tribunal_trt7_ceat_digital_consultar`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT7: Certidão Eletrônica de Ações Trabalhistas (CEAT) - Processos Digitais, consulta em fonte oficial.

### 258. `jus_tribunal_trt7_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT7: Consulta Processual, consulta em fonte oficial.

### 259. `jus_tribunal_trt8_ceat_consultar`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional)

Tribunal TRT8: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 260. `jus_tribunal_trt8_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT8: Consulta Processual, consulta em fonte oficial.

### 261. `jus_tribunal_trt9_ceat_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `nome_completo` (opcional)

Tribunal TRT9: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial.

### 262. `jus_tribunal_trt9_processo_consultar`
**Input**: `numero_processo`, `grau` (opcional)

Tribunal TRT9: Consulta Processual, consulta em fonte oficial.

### 263. `jus_tribunal_tse_certidao_consultar`
**Input**: `name`, `birthdate`, `cpf` (opcional), `titulo_eleitoral` (opcional), `mother` (opcional), `father` (opcional)

Tribunal TSE: Certidão de Quitação Eleitoral, consulta em fonte oficial.

### 264. `jus_tribunal_tse_doador_fornecedor_consultar`
**Input**: `nome` (opcional), `cpf` (opcional), `cnpj` (opcional), `ano`

Tribunal TSE: Doadores e Fornecedores, consulta em fonte oficial.

### 265. `jus_tribunal_tse_pje_consultar`
**Input**: `numero_processo` (opcional), `cpf` (opcional), `cnpj` (opcional), `classe_judicial` (opcional), `objeto` (opcional), `orgao` (opcional), `uf` (opcional), `municipio` (opcional), `ano_eleicao` (opcional), `data_inicial_autuacao` (opcional), `data_final_autuacao` (opcional), `nome_parte` (opcional), `nome_advogado` (opcional), `oab` (opcional)

Tribunal TSE: Processo Judicial Eletrônico (PJe), consulta em fonte oficial.

### 266. `jus_tribunal_tse_situacao_consultar`
**Input**: `name` (opcional), `cpf` (opcional), `titulo_eleitoral` (opcional), `birthdate` (opcional)

Tribunal TSE: Situação Eleitoral, consulta em fonte oficial.

### 267. `jus_tribunal_tse_titulo_consultar`
**Input**: `birthdate`, `mother` (opcional), `father` (opcional), `name` (opcional), `cpf` (opcional), `titulo_eleitoral` (opcional)

Tribunal TSE: Título Eleitoral, consulta em fonte oficial.

### 268. `jus_tribunal_tst_banco_falencias_consultar`
**Input**: `cnpj` (opcional), `razao_social` (opcional), `numero_processo` (opcional)

Tribunal TST: Banco de Falências, consulta em fonte oficial.

### 269. `jus_tribunal_tst_cndt_consultar`
**Input**: `cnpj` (opcional), `cpf` (opcional)

Tribunal TST: CNDT, consulta em fonte oficial.

### 270. `jus_tribunal_tst_validacao_cndt_consultar`
**Input**: `cpf` (opcional), `cnpj` (opcional), `numero_certidao`, `ano`

Tribunal TST: Validação de CNDT, consulta em fonte oficial.

## Prompts de exemplo

```
Monte um raio-X dos processos de Fulano de Tal
Tem intimação para a OAB 21076/SP nos últimos 7 dias?
Atualize R$ 12.500 pelo IPCA de 01/2020 até hoje e calcule os juros
Esse CNPJ tem CNDT negativa e aparece em alguma lista de inidôneos?
```
