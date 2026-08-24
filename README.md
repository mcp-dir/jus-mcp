# Jus MCP

### O MCP jurídico do Brasil para Claude, Cursor e agentes de IA

Todo o jurídico brasileiro numa conexão só: processos por nome/CPF/CNPJ/número, publicações e intimações do DJEN, jurisprudência, cálculos judiciais, licitações do PNCP e acórdãos do TCU, certidões de regularidade, sanções e compliance, e mais de 150 consultas em fontes e órgãos oficiais. Hospedado pela plataforma, sem login, com as fontes públicas grátis e crédito pré-pago só nas consultas pagas.

- ⚖️ **Um MCP, não trinta** — processos, publicações, jurisprudência, cálculos, licitações, certidões e compliance na MESMA conexão
- 🔎 **Descoberta por nome, CPF, CNPJ ou número** do processo, com raio-X consolidado (`legal_dossie`)
- 📢 **Publicações e intimações do DJEN** por OAB, parte ou processo
- 📜 **Jurisprudência e súmulas** dos tribunais superiores
- 🧮 **16 cálculos judiciais** — atualização monetária, trabalhista, FGTS, pensão, dosimetria, RMI, partilha
- 🏛️ **Licitações (PNCP) e acórdãos do TCU**
- 🧾 **Certidões de regularidade** (CND Federal/PGFN, CNDT, FGTS)
- 🛡️ **Compliance e sanções** — PEP, OFAC/ONU/UE/Reino Unido, CEIS/CNEP, improbidade
- 📥 **Baixa as decisões públicas** do processo (acórdãos e inteiro teor) já convertidas em texto
- 🗂️ **+150 consultas em órgãos oficiais** — tribunais estaduais, cartórios, protestos, MPs
- ⚡ **Sem login, sem credencial** — funciona na primeira pergunta
- 💳 **Fontes públicas grátis**; só as consultas pagas descontam crédito, pelo MESMO preço do MCP avulso
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Jus MCP` e **URL** `https://api.mcp.ai/jus`.

### Cursor

[➕ Instalar Jus MCP no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=jus&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvanVzIn0=)

### VS Code (Copilot Chat)

[➕ Instalar Jus MCP no VS Code](vscode:mcp/install?name=jus&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fjus%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/jus
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Monte um raio-X dos processos de Fulano de Tal
Tem intimação para a OAB 21076/SP nos últimos 7 dias?
Atualize R$ 12.500 pelo IPCA de 01/2020 até hoje e calcule os juros
Esse CNPJ tem CNDT negativa e aparece em alguma lista de inidôneos?
```

---

## 270 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `pncp_buscar` | Busca licitações por PALAVRA-CHAVE no objeto (cobertura NACIONAL ampla, índice full-text), em editais, atas ou contratos. |
| `pncp_listar` | Busca PRINCIPAL de licitações abertas por palavra-chave, faixa de VALOR, estado, modalidade e período. |
| `pncp_oportunidades` | Busca de OPORTUNIDADES de licitação (editais/pregões) com filtros ricos por palavra-chave, FAIXA DE VALOR da compra, UFs, modalidades, portais, registro de preço, participação exclusiva ME/EPP e superoportunidades. |
| `pncp_processo` | Detalhe de oportunidade(s) por `id` (de pncp_listar/pncp_oportunidades). |
| `pncp_detalhe` | Detalhe completo de uma licitação/contratação a partir de cnpj+ano+sequencial (a referência devolvida pela pncp_buscar). |
| `pncp_resultado` | Quem GANHOU a licitação: o(s) fornecedor(es) vencedor(es) homologado(s) a partir de cnpj+ano+sequencial (a referência da pncp_buscar). |
| `pncp_arquivos` | Documentos de uma licitação/edital (edital, termo de referência, anexos) com o LINK de download de cada arquivo (em geral PDF). |
| `pncp_texto` | Texto INTEIRO do edital em markdown (com marcadores '## Página N'), pra você RESUMIR ou ler o documento todo. |
| `pncp_contratos` | Lista contratos públicos firmados num período, opcionalmente filtrando por órgão (CNPJ). |
| `pncp_atas` | Lista atas de registro de preços vigentes num período (referência de preços praticados pelo governo), opcionalmente por órgão (CNPJ). |
| `pncp_pca` | Plano anual de contratações (PCA) por ano e classificação superior do catálogo: o que os órgãos planejam contratar no ano. |
| `pncp_historico` | Arquivo histórico de licitações: consulta editais que a plataforma acumulou ao longo do tempo (inclusive os que já encerraram ou saíram do ar), por PALAVRA-CHAVE no objeto, estado (UF), modalidade, situação e período… |
| `pncp_orgaos` | Busca de ÓRGÃOS/entidades compradoras por nome, UF e/ou portal. |
| `tcu_buscar` | Busca textual (por palavra-chave) na jurisprudência do TCU. |
| `tcu_acordaos_recentes` | Lista os acórdãos mais recentes do TCU (dados abertos oficiais), paginado, sem palavra-chave: sumário, relator, colegiado, data da sessão e links. |
| `datajud_get_processo` | Busca um processo pelo número único do CNJ (com ou sem máscara) em um tribunal. |
| `datajud_search` | Busca processos em um tribunal por classe, órgão julgador e/ou assunto (códigos das tabelas do CNJ), paginada e ordenada por data de ajuizamento. |
| `datajud_movimentos` | Retorna apenas a timeline de movimentações (+ metadados) de um processo — ideal pra detectar se houve movimentação nova. |
| `datajud_raw_query` | Avançado: envia um corpo de query Elasticsearch cru pro índice do tribunal (escape hatch). |
| `calculo_atualizar` | Atualização monetária / liquidação de débito judicial: corrige parcelas por um índice oficial (IPCA, INPC, IGP-M, SELIC, TR…) e aplica juros, multa e honorários. |
| `calculo_indice` | Consulta de índice oficial: fator de correção acumulado entre duas datas (mês inicial excluído, mês final incluído — convenção BACEN/IBGE). |
| `calculo_salario_minimo` | Salário mínimo nacional vigente de um ano (dinâmico, IPEADATA). |
| `calculo_aluguel` | Aluguéis em atraso (Lei 8.245/91): reajusta o aluguel ao longo do contrato pelo índice, corrige cada mês atrasado até hoje, aplica juros de mora (1% a.m.) e multa moratória. |
| `calculo_pensao` | Pensão alimentícia em atraso (art. |
| `calculo_trabalhista` | Verbas rescisórias / liquidação trabalhista (CLT): saldo de salário, aviso prévio indenizado (Lei 12.506/2011), 13º proporcional, férias proporcionais + 1/3, férias vencidas, multa de 40%/20% do FGTS, com descontos de… |
| `calculo_fgts` | Correção do FGTS (tese TR → INPC/IPCA-E, STF): por depósito calcula a diferença entre corrigir pelo índice de inflação vs pela TR, com juros de 3% a.a. |
| `calculo_dosimetria` | Dosimetria da pena (art. 68 CP, sistema trifásico): pena-base pelas circunstâncias judiciais (art. 59), pena intermediária por atenuantes/agravantes (Súmula 231 STJ), pena definitiva por causas de aumento/diminuição (… |
| `calculo_progressao` | Progressão de regime (LEP art. |
| `calculo_partilha` | Partilha de bens no divórcio por regime (Código Civil): apura a massa partilhável (bens − dívidas conforme o regime) e a quota de cada cônjuge, com torna por desequilíbrio. |
| `calculo_tempo_contribuicao` | Tempo de contribuição (CNIS): soma os vínculos contando concomitância uma vez e converte atividade especial em comum (fatores EC 103/2019, só até 13/11/2019). |
| `calculo_rmi` | RMI — Renda Mensal Inicial (pós-reforma EC 103/2019): média dos salários de contribuição × coeficiente (60% + 2% por ano acima de 20H/15M), com piso (salário mínimo) e teto (INSS). |
| `calculo_revisional` | Revisional de contrato bancário: recalcula o financiamento pela taxa média de mercado do BACEN (busca ao vivo por modalidade+mês) e apura o excedente por parcela (Price ou SAC). |
| `calculo_superendividamento` | Superendividamento (Lei 14.181/2021): % da renda comprometida, mínimo existencial (R$600, parametrizável), renda disponível e capacidade de pagamento de um plano de até 5 anos. |
| `calculo_rmc_rcc` | RMC/RCC — reserva de margem consignável de cartão (INSS, códigos 217/268): limites de 5% e restituição corrigida dos descontos. |
| `calculo_restituicao_inss` | Restituição de descontos indevidos no INSS (fraude associativa, códigos 280/304/310/378): soma as parcelas descontadas corrigidas. |
| `djen_search_comunicacoes` | Busca publicações/intimações no Diário de Justiça Eletrônico Nacional (DJEN) por OAB, nome de advogado, número de processo, tribunal e data. |
| `djen_processos_por_parte` | DESCOBERTA por NOME de parte (grátis, sem captcha): busca o DJEN por quem figura no processo e agrupa por número — devolve a lista de processos da pessoa/empresa, com partes e tribunal. |
| `djen_get_certidao` | Retorna a URL da certidão (PDF) de uma comunicação do DJEN pelo seu hash (campo `hash` retornado na busca). |
| `processos_buscar_por_nome` | DESCOBERTA: busca processos pelo NOME de uma parte (pessoa ou empresa) raspando os portais públicos dos tribunais (ESAJ/PJe/eproc/Projudi) — o gap que datajud (só por número) e djen (OAB/advogado) não cobrem. |
| `processos_buscar_por_documento` | DESCOBERTA por CPF ou CNPJ. O serviço resolve o documento em nome(s) (CNPJ→razão social/sócios; CPF→nome) e então busca os processos por nome nos portais. ASSÍNCRONO: retorna { job_id }; faça o polling com processos_g… |
| `processos_obter_pecas` | DOWNLOAD das DECISÕES PÚBLICAS de um processo (acórdãos/inteiro teor): busca as decisões públicas do processo, baixa o PDF e converte em Markdown (o teor da decisão), com link temporário. |
| `processos_get_resultado` | Polling de um job de busca (de processos_buscar_por_nome/documento). |
| `cnpj_consultar` | Consulta cadastral de um CNPJ (grátis): razão social, nome fantasia, situação cadastral, CNAE principal, porte, município/UF e SÓCIOS (QSA). |
| `cnpj_processos` | DESCOBERTA por CNPJ: resolve o CNPJ em razão social (e sócios) e busca os processos por NOME no Diário (DJEN) — grátis, com número de processo completo. |
| `cpf_validar` | Valida os dígitos verificadores de um CPF (mod 11) e informa se há broker de identidade disponível. |
| `cpf_processos` | DESCOBERTA por CPF: busca os processos da pessoa por NOME no Diário (DJEN), grátis. |
| `transparencia_sancoes` | Consulta sanções de uma pessoa ou empresa por CPF/CNPJ no Portal da Transparência (consolida CEIS — inidôneas/suspensas, CNEP — empresas punidas, e CEPIM — entidades impedidas). |
| `transparencia_pep` | Verifica se um CPF é de Pessoa Exposta Politicamente (PEP) e retorna função/órgão/período. |
| `transparencia_despesas_favorecido` | DESPESAS recebidas por uma empresa ou pessoa (CPF/CNPJ) do Governo Federal num período: 'quanto a empresa recebeu da União'. |
| `transparencia_despesas_documentos` | Documentos de despesa (Empenho, Liquidação ou Pagamento) emitidos pelo Governo Federal para um favorecido (CPF/CNPJ) num ano, item-a-item: data, documento, espécie, valor, órgão, elemento de despesa e nº do processo. |
| `querido_diario_buscar` | Busca em diários oficiais MUNICIPAIS (milhares de prefeituras) por termo/nome — útil pra menções fora do Judiciário: licitações, nomeações, contratos, sanções municipais. |
| `jurisprudencia_buscar` | Busca jurisprudência (acórdãos, súmulas, OJs) no acervo público LexML por termo/tese — cobre tribunais superiores e demais. |
| `jurisprudencia_sumulas` | Busca SÚMULAS (incluindo vinculantes) por termo no acervo LexML. |
| `legal_dossie` | Raio-X jurídico de uma pessoa ou empresa: descobre os processos e (opcional) o andamento, num relatório consolidado. |
| `legal_monitorar` | Cria um monitoramento: avisa quando houver NOVIDADE — nova movimentação (numero_processo), novo processo de uma pessoa/empresa (nome/cnpj), ou nova publicação/intimação de uma OAB (oab+uf). |
| `legal_listar_monitoramentos` | Lista os monitoramentos ativos do workspace. |
| `legal_remover_monitoramento` | Remove (desativa) um monitoramento pelo seu id (`watch_id`). |
| `legal_checar_novidades` | Checa AGORA se há novidade nos monitoramentos (sem esperar o ciclo automático). |
| `capivara_resolver` | CAMADA 1 (descoberta de identidade): a partir do que você SABE da pessoa em TEXTO LIVRE (nome, cidade, emprego, empresa, qualquer pista), descobre o CPF mais provável e devolve um PERFIL NORMALIZADO (nome, CPF, empres… |
| `capivara_registrar_consentimento` | Registra, de forma auditável (LGPD), a finalidade e a base legal de uma investigação — e, quando aplicável, a DECLARAÇÃO do usuário de que tem autorização do titular para dados sob sigilo (SCR/Bacen, cadastro positivo). |
| `capivara_dossie` | Raio-X cadastral 360º de uma PESSOA (por CPF) OU EMPRESA (por CNPJ) — consolidado num relatório por seção. |
| `jus_cenprot_sp_protestos_consultar` | CENPROT SP: Protestos, consulta em fonte oficial. |
| `jus_certidoes_cndt` | Consulta a Certidão Negativa de Débitos Trabalhistas (CNDT) por CNPJ ou CPF. |
| `jus_certidoes_fgts` | Consulta a regularidade do empregador perante o FGTS (Certificado de Regularidade — CRF) por CNPJ. |
| `jus_certidoes_pgfn` | Emite/consulta a Certidão de débitos relativos a Tributos Federais e à Dívida Ativa da União (CND Federal/PGFN) por CNPJ ou CPF. |
| `jus_cnj_improbidade_consultar` | Conselho Nacional de Justiça: Improbidade Administrativa e Inelegibilidade, consulta em fonte oficial. |
| `jus_cnj_mandados_prisao_consultar` | Conselho Nacional de Justiça: Mandados de Prisão, consulta em fonte oficial. |
| `jus_cnj_seeu_processos_consultar` | Conselho Nacional de Justiça SEEU: Processos, consulta em fonte oficial. |
| `jus_cnj_serventias_extrajud_lista_consultar` | Conselho Nacional de Justiça: Serventias Extrajudiciais (Lista), consulta em fonte oficial. |
| `jus_cnj_serventias_extrajudiciais_consultar` | Conselho Nacional de Justiça: Serventias Extrajudiciais (Detalhes), consulta em fonte oficial. |
| `jus_compliance_antecedentes_civil` | Antecedentes criminais (Polícia Civil) por CPF/nome/UF. |
| `jus_compliance_antecedentes_pf` | Antecedentes criminais (Polícia Federal) por CPF/nome. |
| `jus_compliance_antt` | Regularidade de transportadora na ANTT por CPF/CNPJ/RNTRC. |
| `jus_compliance_bacen_inabilitados` | Banco Central — quadro geral de inabilitados, por CPF/CNPJ. |
| `jus_compliance_bacen_proibidos` | Banco Central — quadro geral de proibidos, por CPF/CNPJ. |
| `jus_compliance_cadin` | CADIN estadual (inadimplentes com a Fazenda) por CPF/CNPJ/UF. |
| `jus_compliance_carf` | Processos no CARF (Conselho Administrativo de Recursos Fiscais) por CPF/CNPJ. |
| `jus_compliance_ceaf` | CEAF — expulsões da administração federal, por CPF. |
| `jus_compliance_ceis` | CEIS — empresas inidôneas e suspensas, por CNPJ/CPF. |
| `jus_compliance_cepim` | CEPIM — entidades privadas impedidas, por CNPJ. |
| `jus_compliance_cgu` | Consulta de penalidades CGU por CPF/CNPJ. |
| `jus_compliance_cnd_municipal` | Certidão Negativa de Débitos Municipal por CNPJ/CPF (informe o município). |
| `jus_compliance_cnep` | CNEP — empresas punidas, por CNPJ/CPF. |
| `jus_compliance_confea_crea` | Registro profissional no CONFEA/CREA (engenharia/agronomia). |
| `jus_compliance_cvm` | Cadastro na CVM (Comissão de Valores Mobiliários) por CPF/CNPJ. |
| `jus_compliance_cvm_sancionadores` | Processos administrativos sancionadores da CVM por CPF/CNPJ. |
| `jus_compliance_fbi` | Busca na lista FBI Most Wanted por nome. |
| `jus_compliance_fincen` | Busca na lista FINCEN por nome. |
| `jus_compliance_ibama_debitos` | Certidão negativa de débitos do IBAMA por CPF/CNPJ. |
| `jus_compliance_improbidade` | CNIA — condenações por improbidade administrativa e inelegibilidade, por CNPJ/CPF. |
| `jus_compliance_interpol` | Busca na lista da INTERPOL por nome. |
| `jus_compliance_leniencia` | Acordos de leniência por CNPJ. |
| `jus_compliance_mandados_prisao` | CNJ — mandados de prisão em aberto, por CPF/nome. |
| `jus_compliance_ofac` | Busca em listas de sanções OFAC (EUA) por nome. |
| `jus_compliance_onu` | Busca na lista consolidada de sanções da ONU por nome. |
| `jus_compliance_pep` | Verifica se um CPF é Pessoa Exposta Politicamente (PEP). |
| `jus_compliance_pep_parentescos` | PEP estendida — pessoa exposta politicamente + parentescos. |
| `jus_compliance_pix` | Antifraude de chave PIX — valida o titular de uma chave PIX. |
| `jus_compliance_trabalho_forcado` | Verificação de empregador em lista de trabalho forçado/escravo, por CNPJ/CPF. |
| `jus_compliance_ue` | Busca na lista de sanções financeiras da União Europeia por nome. |
| `jus_compliance_uk` | Busca na lista de sanções do Reino Unido (HM Treasury) por nome. |
| `jus_ieptb_protestos_consultar` | IEPTB (CENPROT): Protestos, consulta em fonte oficial. |
| `jus_ieptb_protestos_detalhes_sp_consultar` | IEPTB (CENPROT) Protestos: Detalhes SP, consulta em fonte oficial. |
| `jus_inpi_marcas_busca` | Busca marcas no INPI pelo nome/termo (anterioridade/colidência). |
| `jus_inpi_marcas_processo` | Detalhes completos de um processo de registro de marca no INPI pelo número do processo (situação, depósito, concessão, vigência, titulares, classes Nice/Viena, petições, publicações). |
| `jus_inpi_marcas_processo_resumido` | Resumo de um processo de registro de marca no INPI pelo número do processo (marca, titular, classe, situação). |
| `jus_inpi_marcas_titular` | Marcas registradas no INPI por titular (CPF ou CNPJ). |
| `jus_inpi_patentes` | Patentes registradas no INPI por titular (CPF ou CNPJ). |
| `jus_investigacao_aml` | Rede de vínculos societários para prevenção à lavagem de dinheiro, por CPF. |
| `jus_investigacao_beneficiario_final` | Beneficiário final (UBO) de uma empresa ou pessoa. |
| `jus_investigacao_beneficios_sociais` | Benefícios sociais recebidos por um CPF (Bolsa Família, BPC, etc.). |
| `jus_investigacao_cnh` | Dados da CNH (Carteira Nacional de Habilitação) por CPF. |
| `jus_investigacao_enriquecimento` | Descobre a pessoa por trás de um celular e/ou email (enriquecimento reverso). |
| `jus_investigacao_historico_veicular` | Histórico veicular (SP) por CPF ou CNPJ. |
| `jus_investigacao_localizacao` | Localização de uma pessoa (nome, endereço, telefone, email). |
| `jus_investigacao_obito` | Verificação de óbito por CPF. |
| `jus_investigacao_participacoes` | QSA + participações societárias de um CNPJ (sócios e empresas ligadas). |
| `jus_investigacao_pessoa_fisica` | Dados cadastrais completos de um CPF: nome, contato (telefone/email), endereço, renda estimada e faixa salarial. |
| `jus_investigacao_pessoa_juridica` | Dados cadastrais completos de um CNPJ. |
| `jus_investigacao_pis` | PIS vinculado a um CPF. |
| `jus_investigacao_prf_infracoes` | Infrações da Polícia Rodoviária Federal por placa + RENAVAM. |
| `jus_investigacao_propriedade_veicular` | Veículos no nome de uma pessoa ou empresa (frota) por CPF/CNPJ. |
| `jus_investigacao_renda` | Nível socioeconômico e renda estimada de um CPF. |
| `jus_investigacao_situacao_eleitoral` | Situação eleitoral de uma pessoa (TSE). |
| `jus_investigacao_titulo_eleitoral` | Título e local de votação (TSE). |
| `jus_investigacao_veiculo_placa` | Dados e débitos de um veículo pela placa (não exige RENAVAM). |
| `jus_investigacao_vinculo_empregaticio` | Vínculos empregatícios. |
| `jus_investigacao_vinculos_societarios` | Vínculos/relacionamentos societários de uma pessoa ou empresa. |
| `jus_mp_sp_inquerito_civil_consultar` | Ministério Público SP: Inquérito Civil, consulta em fonte oficial. |
| `jus_mpf_amazonia_protege_consultar` | MPF: Amazônia Protege, consulta em fonte oficial. |
| `jus_mpf_certidao_negativa_consultar` | MPF: Certidão Negativa, consulta em fonte oficial. |
| `jus_mpf_processos_consultar` | MPF: Processos, consulta em fonte oficial. |
| `jus_mpt_ac_cnf_consultar` | MPT AC e RO: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_al_cnf_consultar` | MPT AL: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_am_cnf_consultar` | MPT AM e RR: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_ap_cnf_consultar` | MPT AP e PA: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_ba_cnf_consultar` | MPT BA: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_ce_cnf_consultar` | MPT CE: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_cnf_unificada_consultar` | MPT Unificada: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_df_cnf_consultar` | MPT DF e TO: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_es_cnf_consultar` | MPT ES: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_go_cnf_consultar` | MPT GO: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_ma_cnf_consultar` | MPT MA: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_mg_cnf_consultar` | MPT MG: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_ms_cnf_consultar` | MPT MS: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_mt_cnf_consultar` | MPT MT: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_pb_cnf_consultar` | MPT PB: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_pe_cnf_consultar` | MPT PE: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_pi_cnf_consultar` | MPT PI: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_pr_cnf_consultar` | MPT PR: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_rj_cnf_consultar` | MPT RJ: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_rn_cnf_consultar` | MPT RN: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_rs_cnf_consultar` | MPT RS: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_sc_cnf_consultar` | MPT SC: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_se_cnf_consultar` | MPT SE: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_sp_campinas_cnf_consultar` | MPT SP Campinas: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_mpt_sp_cnf_consultar` | MPT SP: Certidão Negativa de Feitos, consulta em fonte oficial. |
| `jus_onr_mapa_registro_imoveis_consultar` | ONR: Mapa do Registro de Imóveis, consulta em fonte oficial. |
| `jus_registradores_certid_download_consultar` | Registradores (ARISP) Certidão: Download de Certidão Digital, consulta em fonte oficial. |
| `jus_registradores_certid_pedido_consultar` | Registradores (ARISP) Certidão: Novo Pedido de Certidão Digital, consulta em fonte oficial. |
| `jus_registradores_certid_recibo_consultar` | Registradores (ARISP) Certidão: Download de Recibo, consulta em fonte oficial. |
| `jus_registradores_info_conta_consultar` | Registradores (ARISP): Consulta de Informações da Conta, consulta em fonte oficial. |
| `jus_registradores_matric_download_consultar` | Registradores (ARISP) Matrícula: Download de Matrícula, consulta em fonte oficial. |
| `jus_registradores_matric_lista_consultar` | Registradores (ARISP) Matrícula: Lista de Pedidos, consulta em fonte oficial. |
| `jus_registradores_matric_pedido_consultar` | Registradores (ARISP) Matrícula: Novo Pedido de Visualização de Matrícula, consulta em fonte oficial. |
| `jus_registradores_matric_recibo_consultar` | Registradores (ARISP) Matrícula: Download de Recibo, consulta em fonte oficial. |
| `jus_registro_civil_val_cert_eletr_consultar` | Registro Civil: Validar Certidão Eletrônica, consulta em fonte oficial. |
| `jus_tribunal_stj_certidao_negativa_consultar` | Tribunal STJ: Certidão Negativa, consulta em fonte oficial. |
| `jus_tribunal_tjba_primeiro_grau_consultar` | Tribunal TJBA: Certidão do 1º Grau, consulta em fonte oficial. |
| `jus_tribunal_tjdf_nada_consta_consultar` | Tribunal TJDF: Nada Consta, consulta em fonte oficial. |
| `jus_tribunal_tjgo_nada_consta_consultar` | Tribunal TJGO: Nada Consta, consulta em fonte oficial. |
| `jus_tribunal_tjma_nada_consta_consultar` | Tribunal TJMA: Nada Consta, consulta em fonte oficial. |
| `jus_tribunal_tjmg_processo_consultar` | Tribunal TJMG: Processo, consulta em fonte oficial. |
| `jus_tribunal_tjms_obter_certidao_consultar` | Tribunal TJMS: Conferência de Certidão, consulta em fonte oficial. |
| `jus_tribunal_tjms_pedido_cert_consultar` | Tribunal TJMS: Cadastro de Pedido de Certidão (1º grau), consulta em fonte oficial. |
| `jus_tribunal_tjmt_primeiro_grau_pf_consultar` | Tribunal TJMT: Certidão do 1º Grau (Pessoa Física), consulta em fonte oficial. |
| `jus_tribunal_tjpa_cert_criminal_consultar` | Tribunal TJPA: Certidão Criminal, consulta em fonte oficial. |
| `jus_tribunal_tjpr_processo_consultar` | Tribunal TJPR: Processo, consulta em fonte oficial. |
| `jus_tribunal_tjrj_obter_certidao_consultar` | Tribunal TJRJ: Visualizar Certidão, consulta em fonte oficial. |
| `jus_tribunal_tjrj_pedido_cert_consultar` | Tribunal TJRJ: Cadastro de Pedido de Certidão, consulta em fonte oficial. |
| `jus_tribunal_tjrj_processo_consultar` | Tribunal TJRJ: Processo, consulta em fonte oficial. |
| `jus_tribunal_tjrj_processo_eproc_consultar` | Tribunal TJRJ: Processo (eproc), consulta em fonte oficial. |
| `jus_tribunal_tjrs_primeiro_grau_consultar` | Tribunal TJRS: Certidão do 1º Grau, consulta em fonte oficial. |
| `jus_tribunal_tjsc_obter_certidao_consultar` | Tribunal TJSC: Visualizar Certidão, consulta em fonte oficial. |
| `jus_tribunal_tjsc_pedido_certidao_consultar` | Tribunal TJSC: Pedido de Certidão, consulta em fonte oficial. |
| `jus_tribunal_tjsc_processo_consultar` | Tribunal TJSC: Processo, consulta em fonte oficial. |
| `jus_tribunal_tjsp_colegio_recursal_consultar` | Tribunal TJSP: Colégio Recursal e Turma de Uniformização, consulta em fonte oficial. |
| `jus_tribunal_tjsp_eproc_lista_consultar` | Tribunal TJSP: Lista de Processos (eproc), consulta em fonte oficial. |
| `jus_tribunal_tjsp_eproc_unificada_consultar` | Tribunal TJSP: Consulta Processual Unificada (Eproc), consulta em fonte oficial. |
| `jus_tribunal_tjsp_obter_cert_1grau_consultar` | Tribunal TJSP: Download da Certidão de 1º Grau, consulta em fonte oficial. |
| `jus_tribunal_tjsp_obter_certidao_consultar` | Tribunal TJSP: Visualizar Certidão, consulta em fonte oficial. |
| `jus_tribunal_tjsp_pedido_certidao_consultar` | Tribunal TJSP: Cadastro de Pedido de Certidão, consulta em fonte oficial. |
| `jus_tribunal_tjsp_pedido_civel_consultar` | Tribunal TJSP: Certidão Cível de 1º Grau, consulta em fonte oficial. |
| `jus_tribunal_tjsp_pedido_criminal_consultar` | Tribunal TJSP: Certidão Criminal de 1º Grau, consulta em fonte oficial. |
| `jus_tribunal_tjsp_primeiro_grau_consultar` | Tribunal TJSP: Processos do 1º Grau, consulta em fonte oficial. |
| `jus_tribunal_tjsp_segundo_grau_consultar` | Tribunal TJSP: Processos do 2º Grau, consulta em fonte oficial. |
| `jus_tribunal_tjsp_selo_digital_consultar` | Tribunal TJSP: Selo Digital, consulta em fonte oficial. |
| `jus_tribunal_tjto_cert_judicial_consultar` | Tribunal TJTO: Certidão Judicial, consulta em fonte oficial. |
| `jus_tribunal_trf_cert_unificada_consultar` | Tribunal TRF: Certidão Unificada da Justiça Federal, consulta em fonte oficial. |
| `jus_tribunal_trf1_certidao_consultar` | Tribunal TRF1: Certidão Negativa Cível e Criminal, consulta em fonte oficial. |
| `jus_tribunal_trf1_processo_consultar` | Tribunal TRF1: Processo, consulta em fonte oficial. |
| `jus_tribunal_trf2_certidao_consultar` | Tribunal TRF2: Certidão Negativa Cível e Criminal, consulta em fonte oficial. |
| `jus_tribunal_trf2_processo_consultar` | Tribunal TRF2: Processo, consulta em fonte oficial. |
| `jus_tribunal_trf2_processo_eproc_consultar` | Tribunal TRF2: Processo (eproc), consulta em fonte oficial. |
| `jus_tribunal_trf3_certidao_distr_consultar` | Tribunal TRF3: Certidão de Distribuição, consulta em fonte oficial. |
| `jus_tribunal_trf3_consulta_publica_consultar` | Tribunal TRF3: Consulta Pública, consulta em fonte oficial. |
| `jus_tribunal_trf3_obter_certidao_consultar` | Tribunal TRF3: Obter Certidão de Distribuição, consulta em fonte oficial. |
| `jus_tribunal_trf3_processo_consultar` | Tribunal TRF3: Processo, consulta em fonte oficial. |
| `jus_tribunal_trf4_certidao_consultar` | Tribunal TRF4: Certidão Negativa Cível e Criminal, consulta em fonte oficial. |
| `jus_tribunal_trf5_certidao_consultar` | Tribunal TRF5: Certidão Negativa Cível e Criminal, consulta em fonte oficial. |
| `jus_tribunal_trf5_processo_consultar` | Tribunal TRF5: Processo, consulta em fonte oficial. |
| `jus_tribunal_trf6_certidao_consultar` | Tribunal TRF6: Certidão Negativa Cível e Criminal, consulta em fonte oficial. |
| `jus_tribunal_trf6_processo_consultar` | Tribunal TRF6: Processo, consulta em fonte oficial. |
| `jus_tribunal_trt_processo_consultar` | Tribunal TRT: Consulta Processual Unificada, consulta em fonte oficial. |
| `jus_tribunal_trt1_ceat_consultar` | Tribunal TRT1: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt1_processo_consultar` | Tribunal TRT1: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt10_ceat_consultar` | Tribunal TRT10: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt10_ceat_digital_consultar` | Tribunal TRT10: Certidão Eletrônica de Ações Trabalhistas (CEAT) - Processos Digitais, consulta em fonte oficial. |
| `jus_tribunal_trt10_processo_consultar` | Tribunal TRT10: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt11_ceat_consultar` | Tribunal TRT11: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt11_processo_consultar` | Tribunal TRT11: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt12_ceat_consultar` | Tribunal TRT12: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt12_processo_consultar` | Tribunal TRT12: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt13_ceat_consultar` | Tribunal TRT13: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt13_processo_consultar` | Tribunal TRT13: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt14_ceat_consultar` | Tribunal TRT14: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt14_processo_consultar` | Tribunal TRT14: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt15_ceat_consultar` | Tribunal TRT15: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt15_processo_consultar` | Tribunal TRT15: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt16_ceat_consultar` | Tribunal TRT16: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt16_processo_consultar` | Tribunal TRT16: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt17_ceat_consultar` | Tribunal TRT17: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt17_processo_consultar` | Tribunal TRT17: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt18_ceat_consultar` | Tribunal TRT18: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt18_processo_consultar` | Tribunal TRT18: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt19_ceat_consultar` | Tribunal TRT19: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt19_processo_consultar` | Tribunal TRT19: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt2_ceat_consultar` | Tribunal TRT2: Certidão Eletrônica de Ações Trabalhistas (CEAT) - Processos Físicos, consulta em fonte oficial. |
| `jus_tribunal_trt2_ceat_digital_consultar` | Tribunal TRT2: Certidão Eletrônica de Ações Trabalhistas (CEAT) - Processos Digitais, consulta em fonte oficial. |
| `jus_tribunal_trt2_processo_consultar` | Tribunal TRT2: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt20_ceat_consultar` | Tribunal TRT20: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt20_processo_consultar` | Tribunal TRT20: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt21_ceat_consultar` | Tribunal TRT21: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt21_processo_consultar` | Tribunal TRT21: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt22_processo_consultar` | Tribunal TRT22: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt23_ceat_consultar` | Tribunal TRT23: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt24_ceat_consultar` | Tribunal TRT24: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt24_processo_consultar` | Tribunal TRT24: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt3_ceat_consultar` | Tribunal TRT3: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt4_ceat_consultar` | Tribunal TRT4: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt4_processo_consultar` | Tribunal TRT4: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt5_ceat_consultar` | Tribunal TRT5: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt5_processo_consultar` | Tribunal TRT5: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt6_certidao_consultar` | Tribunal TRT6: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt6_processo_consultar` | Tribunal TRT6: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt7_ceat_consultar` | Tribunal TRT7: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt7_ceat_digital_consultar` | Tribunal TRT7: Certidão Eletrônica de Ações Trabalhistas (CEAT) - Processos Digitais, consulta em fonte oficial. |
| `jus_tribunal_trt7_processo_consultar` | Tribunal TRT7: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt8_ceat_consultar` | Tribunal TRT8: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt8_processo_consultar` | Tribunal TRT8: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_trt9_ceat_consultar` | Tribunal TRT9: Certidão Eletrônica de Ações Trabalhistas (CEAT), consulta em fonte oficial. |
| `jus_tribunal_trt9_processo_consultar` | Tribunal TRT9: Consulta Processual, consulta em fonte oficial. |
| `jus_tribunal_tse_certidao_consultar` | Tribunal TSE: Certidão de Quitação Eleitoral, consulta em fonte oficial. |
| `jus_tribunal_tse_doador_fornecedor_consultar` | Tribunal TSE: Doadores e Fornecedores, consulta em fonte oficial. |
| `jus_tribunal_tse_pje_consultar` | Tribunal TSE: Processo Judicial Eletrônico (PJe), consulta em fonte oficial. |
| `jus_tribunal_tse_situacao_consultar` | Tribunal TSE: Situação Eleitoral, consulta em fonte oficial. |
| `jus_tribunal_tse_titulo_consultar` | Tribunal TSE: Título Eleitoral, consulta em fonte oficial. |
| `jus_tribunal_tst_banco_falencias_consultar` | Tribunal TST: Banco de Falências, consulta em fonte oficial. |
| `jus_tribunal_tst_cndt_consultar` | Tribunal TST: CNDT, consulta em fonte oficial. |
| `jus_tribunal_tst_validacao_cndt_consultar` | Tribunal TST: Validação de CNDT, consulta em fonte oficial. |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)


---

## Como funciona

```
1. Instala o MCP no seu cliente (Claude / Cursor / VS Code)
2. Pergunta em português — sem login, sem chave de API
3. O agente escolhe a fonte certa entre ~270 ferramentas
4. Fontes públicas (processos, publicações, jurisprudência, cálculos,
   licitações, acórdãos) são GRÁTIS
5. Consultas pagas (certidões, compliance, sanções, cartórios) descontam
   crédito pré-pago, pelo mesmo preço do MCP avulso
```

Cada família também existe como MCP separado (Legal, DataJud, Cálculo, PNCP,
TCU, INPI, Certidões, Compliance). O Jus é o pacote: uma URL, uma carteira.

---

## Preços

Pré-pago (carteira de créditos), paga por uso. Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**Precisa de login ou cadastro?**
Não pra começar. As fontes públicas respondem na primeira pergunta. Só as consultas pagas exigem uma conta com saldo em créditos.

**Custa mais caro que instalar os MCPs separados?**
Não. Cada consulta custa exatamente o mesmo que custaria no MCP avulso — o pacote é conveniência de descoberta, não markup extra.

**O que é grátis?**
Processos e movimentações (CNJ/DataJud), publicações e intimações (DJEN), jurisprudência, dados de CNPJ/CPF, transparência, diários municipais, os 16 cálculos judiciais, licitações do PNCP e acórdãos do TCU.

**Pega processo em segredo de justiça?**
Não. Só o que é público nas bases oficiais.

**Baixa as peças/decisões do processo?**
As DECISÕES PÚBLICAS sim: acórdãos e inteiro teor, baixados do tribunal e já convertidos em texto, com link temporário do PDF. Os autos completos, com petições, dependem de credencial de advogado no sistema do tribunal, e isso a gente não faz.

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills, tudo MIT.


---

## Suporte

- 📧 [jus@mcp.ai](mailto:jus@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/jus-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/jus` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
