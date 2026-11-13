# Atomic Ledger --- Documento de Discovery

**Versão:** 0.1\
**Status:** Consolidação preliminar para revisão\
**Etapa:** Discovery\
**Data de consolidação:** 13/11/2026\
**Natureza das informações:** Exercício de Discovery baseado em
entrevistas e cenários simulados

> **Nota de validade:** Este documento consolida o que foi relatado e
> discutido durante as simulações de Discovery. As informações não
> representam pesquisa realizada com uma empresa real nem validação
> empírica com clientes. Expectativas relatadas por stakeholders
> simulados não devem ser tratadas automaticamente como decisões
> aprovadas de produto.

------------------------------------------------------------------------

## 1. Visão geral

### 1.1 Contexto

O Atomic Ledger é uma proposta de plataforma voltada à centralização,
consolidação e conciliação de informações financeiras provenientes de
diferentes provedores de pagamento e sistemas comerciais utilizados por
empresas clientes.

O cenário investigado considera empresas que utilizam provedores como
Mercado Pago e Pagar.me, além de sistemas comerciais próprios, ERPs de
terceiros e, em alguns casos, planilhas.

Atualmente, equipes financeiras precisam consultar diferentes fontes,
relacionar informações de vendas e pagamentos, analisar valores e
acompanhar situações que não apresentam correspondência evidente. Parte
desse trabalho é realizada manualmente, com apoio de planilhas e
controles individuais.

### 1.2 Problema identificado

A equipe financeira enfrenta dificuldades para reunir, relacionar e
analisar informações comerciais e financeiras distribuídas em diferentes
sistemas.

Entre os problemas relatados estão:

-   Necessidade de acessar painéis de diferentes provedores.
-   Exportação e consolidação manual de relatórios.
-   Dificuldade para relacionar vendas e pagamentos.
-   Dificuldade para identificar divergências entre valores esperados,
    cobrados, disponibilizados e recebidos.
-   Falta de padronização no registro e acompanhamento de ocorrências.
-   Dependência de contato com clientes ou outras pessoas para
    investigar e resolver determinadas situações.
-   Dificuldade para acompanhar ocorrências que permanecem pendentes por
    vários dias.

A centralização é uma possível estratégia para reduzir esses problemas,
mas não deve ser confundida com a própria definição do problema. Ainda é
necessário medir o impacto de cada dificuldade e identificar quais delas
são mais relevantes.

### 1.3 Objetivo preliminar do produto

Investigar e validar uma solução capaz de reunir informações financeiras
e comerciais de diferentes fontes, facilitar a conciliação entre
registros, identificar possíveis divergências e melhorar a visibilidade
e a rastreabilidade do trabalho da equipe financeira.

O nível de atuação do Atomic ainda não está definido. Não foi decidido
se o produto ficará restrito à consulta, consolidação e identificação de
divergências ou se também oferecerá acompanhamento de ocorrências,
solicitação de correções e execução de ações nos sistemas de origem.

------------------------------------------------------------------------

## 2. Stakeholders

Os stakeholders identificados no cenário são:

  -----------------------------------------------------------------------
  Stakeholder             Interesse ou            Pontos ainda não
                          participação            esclarecidos
                          identificada            
  ----------------------- ----------------------- -----------------------
  Diretoria               Definir objetivos,      Autoridade final sobre
                          expectativa de          decisões de escopo,
                          lançamento, público e   critérios de sucesso e
                          prioridades do produto. apetite a risco.

  Equipe financeira       Consultar informações,  Perfis, permissões,
                          realizar conciliações,  autonomia, volume de
                          identificar e           trabalho e diferenças
                          investigar              entre clientes.
                          divergências.           

  Empresas clientes       Utilizar a solução e    Quais clientes
                          fornecer ou             utilizarão diretamente
                          disponibilizar dados    a plataforma e quais
                          comerciais e            serão atendidos por
                          financeiros.            equipes internas.

  Administradores das     Possível gestão de      Necessidades e
  empresas clientes       usuários, contas e      responsabilidades
                          integrações.            efetivas ainda não
                                                  confirmadas.

  Equipe de tecnologia    Viabilizar integrações  Responsabilidades
                          e lidar com diferenças  operacionais, suporte,
                          e limitações das        tratamento de falhas e
                          fontes.                 gestão de integrações.

  Provedores de pagamento Disponibilizar          Dados disponíveis,
                          informações e, conforme semântica, limites,
                          suas capacidades, APIs  histórico, permissões e
                          e notificações.         operações suportadas.

  Sistemas comerciais e   Manter registros de     Autoridade sobre os
  ERPs                    vendas e outras         dados, capacidades de
                          informações comerciais. integração e
                                                  possibilidade de
                                                  atualização externa.

  Responsáveis por        Realizar ou autorizar   Identidade dos
  correções nos sistemas  alterações quando o     responsáveis, fluxo de
  dos clientes            analista não possui     aprovação e prazos.
                          permissão.              
  -----------------------------------------------------------------------

A lista é preliminar. É necessário confirmar quem são os usuários
diretos do Atomic, quem administra cada ambiente e quem possui
autoridade para aprovar alterações ou encerrar ocorrências.

------------------------------------------------------------------------

## 3. Usuários e contexto de utilização

### 3.1 Cenário informado

Na simulação, a gestão informou a intenção de disponibilizar o Atomic
para até 500 empresas clientes.

Foi mencionado que cada empresa poderia ter aproximadamente 3 a 5
usuários, além de administradores internos. O cenário inicial também
considerou cerca de 100 mil operações financeiras por mês.

Esses números são estimativas relatadas durante a simulação, não
requisitos de capacidade ou compromissos comerciais aprovados.

### 3.2 Necessidades identificadas

A equipe financeira deseja:

-   Consultar informações de diferentes provedores em um único lugar.
-   Relacionar vendas e pagamentos.
-   Identificar registros sem correspondência.
-   Identificar possíveis diferenças entre valores.
-   Consultar detalhes das movimentações para investigar ocorrências.
-   Gerar relatórios consolidados e exportações.
-   Reduzir trabalho manual e dificuldade de acompanhamento.

### 3.3 Lacunas

Ainda precisamos investigar:

-   Quantidade de usuários cadastrados, ativos e simultâneos.
-   Diferenças de uso entre empresas.
-   Frequência e duração das rotinas de conciliação.
-   Perfis de acesso e permissões necessárias.
-   Necessidade de segregação de funções, como solicitar, aprovar e
    executar ações.
-   Quais clientes utilizarão a plataforma diretamente.
-   Quais atividades continuarão sendo realizadas por equipes internas
    ou por terceiros.

------------------------------------------------------------------------

## 4. Processo atual --- AS-IS

### 4.1 Fluxo conhecido

Com base nos relatos simulados, o processo atual pode ser resumido da
seguinte forma:

1.  A equipe financeira consulta vendas registradas no sistema comercial
    do cliente.
2.  Busca os pagamentos correspondentes nos provedores.
3.  Relaciona os registros e verifica valores e estados.
4.  Quando encontra diferenças, consulta detalhes da movimentação, como
    taxas, estornos e valores disponibilizados.
5.  Dependendo da situação, entra em contato com o cliente ou com outras
    pessoas para obter esclarecimentos.
6.  Algumas ocorrências são resolvidas rapidamente; outras permanecem
    pendentes por vários dias.
7.  Cada analista pode controlar suas pendências de uma maneira
    diferente, pois não foi identificado um procedimento único de
    registro e acompanhamento.

### 4.2 Dificuldades observadas

-   Alternância entre diferentes sistemas e painéis.
-   Exportação e consolidação de planilhas.
-   Dificuldade para identificar divergências.
-   Falta de critérios e procedimentos uniformes para registrar e
    acompanhar ocorrências.
-   Dependência de conhecimento individual dos analistas.
-   Dependência de terceiros para determinadas correções.
-   Ausência de indicadores confiáveis sobre o tempo gasto no processo.

### 4.3 Informações que ainda faltam

O fluxo acima é parcial. Ainda não conhecemos:

-   Todas as etapas, desde o início até o encerramento de uma
    conciliação.
-   Critérios efetivamente utilizados para relacionar registros.
-   Como são priorizadas as ocorrências.
-   Como se decide que uma divergência está resolvida.
-   Como são tratadas divergências sem evidências suficientes.
-   Quem pode corrigir cada tipo de informação.
-   Como são solicitadas, aprovadas e verificadas correções.
-   Frequência, duração, volume e retrabalho de cada atividade.

É necessário comparar o procedimento formal, caso exista, com o trabalho
efetivamente realizado pelos analistas. Observação direta de rotinas e
análise de ocorrências anteriores podem complementar as entrevistas.

------------------------------------------------------------------------

## 5. Processo desejado --- TO-BE

### 5.1 Resultados esperados pelos stakeholders

Os resultados desejados mencionados durante as simulações incluem:

-   Visão consolidada das movimentações financeiras.
-   Relatórios consolidados.
-   Identificação facilitada de possíveis divergências.
-   Redução do trabalho manual.
-   Melhor rastreabilidade das informações e ocorrências.

A diretoria também manifestou interesse em que o Atomic ajude a equipe a
resolver divergências, e não seja apenas um painel de consulta.

### 5.2 Limites ainda indefinidos

A expressão "ajudar a resolver divergências" é ampla e precisa ser
decomposta em necessidades concretas.

Possíveis níveis de atuação:

1.  Reunir e apresentar informações e evidências.
2.  Identificar registros sem correspondência e possíveis divergências.
3.  Sugerir possíveis causas, quando houver dados e regras suficientes.
4.  Registrar ocorrências, responsáveis, pendências e resultados.
5.  Centralizar solicitações de correção, mantendo a execução no sistema
    de origem.
6.  Alterar diretamente informações em sistemas comerciais.
7.  Executar operações financeiras, como estornos.

Esses níveis não são equivalentes. Cada um possui dependências, riscos,
requisitos de autorização e responsabilidades diferentes.

### 5.3 Distinções importantes

**Centralizar informações:** reunir dados de diferentes fontes e
apresentar uma visão consolidada.

**Centralizar acompanhamento:** registrar ocorrências, responsáveis,
solicitações, pendências e resultados.

**Centralizar execução:** realizar alterações ou operações nos sistemas
de origem.

O produto pode oferecer os dois primeiros níveis sem necessariamente
assumir o terceiro. A escolha depende dos problemas prioritários e das
responsabilidades que os stakeholders estão dispostos a atribuir ao
Atomic.

------------------------------------------------------------------------

## 6. Fontes de dados e dependências externas

### 6.1 Fontes identificadas

  -----------------------------------------------------------------------
  Fonte                   Uso esperado            Situação conhecida
  ----------------------- ----------------------- -----------------------
  Mercado Pago            Informações de          Possui APIs e
                          pagamentos, estornos e  mecanismos de
                          valores                 notificação, conforme
                          disponibilizados.       relato da equipe de
                                                  tecnologia.

  Pagar.me                Informações de          Possui APIs e
                          pagamentos, estornos e  mecanismos de
                          movimentações           notificação, conforme
                          financeiras.            relato da equipe de
                                                  tecnologia.

  Sistemas comerciais     Registros de vendas e   Heterogeneidade entre
  próprios                informações comerciais. clientes.

  ERPs de terceiros       Dados comerciais e      Capacidades e formatos
                          possivelmente           variam conforme o
                          financeiros.            produto e a
                                                  configuração.

  Planilhas               Dados de clientes sem   Podem conter dados
                          integração disponível   incompletos,
                          ou como fonte           duplicados, incorretos
                          complementar.           ou desatualizados.
  -----------------------------------------------------------------------

### 6.2 Questões de integração ainda abertas

Não basta conhecer o formato dos dados. Precisamos entender também:

-   Semântica e significado de cada campo.
-   Autoridade de cada fonte sobre determinada informação.
-   Granularidade dos registros.
-   Identificadores disponíveis para relacionar vendas e pagamentos.
-   Disponibilidade de histórico.
-   Frequência de atualização.
-   Limites de consulta e autenticação.
-   Versões e mudanças nas APIs.
-   Qualidade e responsabilidade pelos dados fornecidos.
-   Alternativas para clientes sem APIs ou integrações.

### 6.3 Disponibilidade e operação degradada

A equipe de tecnologia relatou que já houve indisponibilidade de APIs de
provedores e que a disponibilidade dessas fontes não é controlada pela
empresa.

Ainda precisamos descobrir:

-   Quanto tempo de indisponibilidade é tolerável.
-   Qual atraso de atualização é aceitável para cada informação.
-   Quais atividades podem continuar durante uma indisponibilidade.
-   Como os usuários devem perceber dados desatualizados ou incompletos.
-   Como e quando informações pendentes serão recuperadas.
-   Qual impacto uma falha de integração causa no processo financeiro.

A solução técnica para essas situações pertence a etapas posteriores.
Neste momento, o objetivo é compreender os impactos e as expectativas do
negócio.

------------------------------------------------------------------------

## 7. Regras de negócio e conceitos identificados

As regras abaixo são princípios e questões identificados durante os
exercícios. Não constituem uma especificação completa nem regras
formalmente aprovadas.

### 7.1 Pagamento, liquidação e recebimento

Um pagamento aprovado pelo provedor não significa necessariamente que o
valor já foi liquidado, disponibilizado para saque ou recebido na conta
bancária.

É necessário distinguir, conforme a fonte e o contexto:

-   Valor bruto da operação.
-   Taxas e descontos.
-   Reservas ou retenções.
-   Valor líquido.
-   Valor disponibilizado.
-   Valor efetivamente recebido.
-   Estornos e outras movimentações posteriores.

### 7.2 Correspondência entre registros

A conciliação não deve se basear exclusivamente na igualdade de valores.

A análise pode exigir, conforme a disponibilidade e as regras do
negócio:

-   Identificadores internos e externos.
-   Referências de venda, pedido ou pagamento.
-   Valores e componentes financeiros.
-   Datas e horários.
-   Status e histórico.
-   Dados do provedor e da conta recebedora.
-   Relações entre múltiplos registros.

As relações podem ser 1:1, 1:N ou N:1, dependendo das regras comerciais
e financeiras. Não se deve presumir que vários pagamentos associados a
uma venda sejam duplicidade ou erro sem investigar o contexto.

### 7.3 Divergências e ocorrências

Um registro sem correspondência é inicialmente uma situação a
investigar, não necessariamente um erro.

Uma diferença entre valores pode decorrer de taxas, reservas, estornos,
liquidações parciais, regras contratuais ou outras condições legítimas.

É necessário distinguir:

-   Situação identificada.
-   Ocorrência em investigação.
-   Divergência confirmada.
-   Ocorrência pendente.
-   Ocorrência resolvida.

Essas categorias são possibilidades para investigação, não estados
definitivos já aprovados.

### 7.4 Evidências e causas

O Atomic pode reunir e apresentar evidências, mas isso não significa que
sempre será capaz de determinar a causa de uma divergência.

Devem ser diferenciadas as capacidades de:

1.  Identificar uma diferença.
2.  Reunir informações relacionadas.
3.  Apresentar evidências.
4.  Sugerir uma causa provável.
5.  Confirmar a causa.
6.  Executar ou acompanhar a resolução.

Cada capacidade exige dados, regras e níveis de confiança diferentes.

### 7.5 Correções operacionais e operações financeiras

Uma correção operacional altera uma informação ou relação, como o
vínculo entre um pagamento e uma venda. Ela não movimenta dinheiro
diretamente, embora possa afetar relatórios e decisões financeiras.

Uma operação financeira, como um estorno, produz uma consequência
financeira real e depende de autorização, regras do provedor e controles
específicos.

As duas categorias não devem ser tratadas como uma única operação
genérica. A autoridade para alterar dados de origem também não deve ser
presumida.

------------------------------------------------------------------------

## 8. Escopo preliminar e responsabilidades

### 8.1 Capacidades alinhadas à proposta inicial

As capacidades abaixo estão alinhadas às necessidades relatadas, mas
ainda dependem de validação e priorização formal:

-   Consultar informações financeiras dos provedores.
-   Obter informações de vendas dos sistemas comerciais, quando
    disponíveis.
-   Consolidar informações de diferentes fontes.
-   Identificar registros sem correspondência.
-   Identificar possíveis divergências entre valores.
-   Reunir e apresentar evidências disponíveis.

### 8.2 Capacidades que precisam de validação

-   Sugerir possíveis causas para divergências.
-   Registrar e acompanhar ocorrências.
-   Centralizar solicitações de correção.
-   Alterar informações diretamente nos sistemas de origem.
-   Oferecer fluxos de aprovação.
-   Executar operações financeiras autorizadas.

### 8.3 Limite inicial recomendado para investigação

A execução de operações financeiras, como estornos, não deve ser
assumida como responsabilidade inicial do Atomic sem uma justificativa
de negócio, avaliação de riscos e definição formal de autoridade e
responsabilidade.

Isso não representa uma decisão definitiva de que a capacidade nunca
fará parte do produto.

### 8.4 Responsabilidades a esclarecer

Para cada ação potencial, será necessário identificar:

-   Quem solicita.
-   Quem pode executar.
-   Quem aprova.
-   Qual sistema é a autoridade sobre o dado ou operação.
-   Quem verifica o resultado.
-   Quem responde por falhas ou alterações indevidas.
-   Como o histórico e as evidências são preservados.

------------------------------------------------------------------------

## 9. MVP e critérios de sucesso

### 9.1 Expectativas identificadas

A gestão deseja lançar uma primeira versão rapidamente, evitar
funcionalidades desnecessárias e, possivelmente, começar com um grupo
menor de clientes antes de ampliar a disponibilização.

A gestão mencionou uma intenção de atender até 500 empresas, mas não
definiu critérios para selecionar os primeiros clientes nem indicadores
confiáveis de sucesso.

### 9.2 Hipótese preliminar de valor

Uma hipótese a validar é que reunir informações comerciais e financeiras
e facilitar a identificação de possíveis divergências reduz o esforço
manual da equipe financeira e melhora a capacidade de detectar e
investigar situações que exigem atenção.

Essa hipótese ainda não foi validada com usuários reais.

### 9.3 Indicadores candidatos

  -----------------------------------------------------------------------
  Indicador                           O que pode ajudar a avaliar
  ----------------------------------- -----------------------------------
  Tempo médio de conciliação          Se o processo ficou mais rápido.

  Tempo gasto consultando diferentes  Se houve redução da alternância
  fontes                              entre sistemas.

  Volume de registros conciliados     Alcance do processo apoiado pelo
                                      produto.

  Registros sem correspondência       Capacidade de revelar situações que
  identificados                       exigem análise.

  Ocorrências identificadas e         Utilidade dos alertas e critérios
  confirmadas                         de identificação.

  Tempo de resolução de ocorrências   Se o acompanhamento melhora o fluxo
                                      de trabalho.

  Retrabalho                          Se diminuíram verificações e
                                      atividades repetidas.
  -----------------------------------------------------------------------

Os indicadores precisam ser definidos com fórmula, fonte, período e
responsável. Também será necessário estabelecer uma baseline do processo
atual, mesmo que inicialmente por amostragem ou medição manual.

### 9.4 Seleção de clientes piloto

Critérios a investigar:

-   Representatividade dos diferentes provedores.
-   Diversidade de sistemas comerciais e fontes de dados.
-   Volume de operações.
-   Complexidade das rotinas financeiras.
-   Disponibilidade para participar de testes e fornecer feedback.
-   Qualidade e acessibilidade dos dados.
-   Capacidade de comparar o processo atual com o processo apoiado pelo
    Atomic.

Não há critérios de seleção aprovados até o momento.

### 9.5 Priorização

A priorização deverá considerar:

-   Valor esperado para o usuário e para o negócio.
-   Impacto de não implementar determinada capacidade.
-   Esforço e incerteza.
-   Dependências externas.
-   Riscos operacionais e financeiros.
-   Capacidade de validar a hipótese de valor.

O MVP deve ser a menor solução capaz de validar uma hipótese relevante,
e não simplesmente uma lista reduzida de funcionalidades.

------------------------------------------------------------------------

## 10. Riscos, restrições e incertezas

### 10.1 Riscos identificados

  -----------------------------------------------------------------------
  Risco                               Possível impacto
  ----------------------------------- -----------------------------------
  Heterogeneidade das fontes          Dificuldade de relacionar e
                                      interpretar dados.

  Dados incompletos ou incorretos     Correspondências e divergências
                                      identificadas de forma inadequada.

  Indisponibilidade de provedores     Atraso ou interrupção na
                                      atualização de informações.

  Notificações duplicadas, atrasadas  Estado apresentado diferente do
  ou fora de ordem                    estado atual na origem.

  Ausência de integração em alguns    Limitação da automação e
  clientes                            necessidade de alternativas de
                                      entrada de dados.

  Critérios de conciliação não        Resultados inconsistentes entre
  documentados                        analistas e clientes.

  Falta de rastreabilidade das        Dificuldade para reconstruir
  ocorrências                         decisões e resoluções.

  Alterações em sistemas de origem    Risco de inconsistência,
                                      concorrência, autorização indevida
                                      e responsabilidade indefinida.

  Execução de operações financeiras   Risco de duplicidade, prejuízo,
                                      execução indevida e falhas de
                                      confirmação.

  Ausência de indicadores             Dificuldade de demonstrar o valor
                                      do produto.
  -----------------------------------------------------------------------

### 10.2 Restrições conhecidas

-   A disponibilidade dos provedores externos não é controlada pela
    empresa.
-   Os clientes utilizam sistemas comerciais diferentes.
-   Nem todos os clientes possuem mecanismos de integração.
-   As rotinas financeiras variam entre empresas.
-   A qualidade e a completude dos dados podem variar.
-   A gestão deseja lançar uma primeira versão sem funcionalidades
    desnecessárias.

### 10.3 Incertezas prioritárias

1.  Quais processos financeiros devem ser atendidos primeiro?
2.  Quais dados são indispensáveis para cada tipo de conciliação?
3.  Quais fontes são autoridade para cada informação?
4.  Quais regras determinam correspondências e divergências?
5.  Como são resolvidas as principais ocorrências?
6.  Quais responsabilidades o Atomic deve assumir?
7.  O produto deverá apenas acompanhar correções ou também executá-las?
8.  Quais clientes formarão o grupo piloto?
9.  Como será medida a redução de trabalho manual?
10. Quais requisitos de atualização e disponibilidade são necessários?

------------------------------------------------------------------------

## 11. Decisões pendentes

As seguintes decisões ainda não foram formalmente tomadas:

  -----------------------------------------------------------------------
  Tema                                Decisão necessária
  ----------------------------------- -----------------------------------
  Público e acesso                    Definir quais perfis utilizarão
                                      diretamente o Atomic e quais serão
                                      atendidos por equipes internas.

  Escopo de integração                Definir fontes prioritárias e
                                      alternativas para clientes sem
                                      APIs.

  Regras de conciliação               Aprovar critérios de
                                      correspondência e tratamento de
                                      exceções.

  Gestão de ocorrências               Decidir se o Atomic terá registro,
                                      atribuição, acompanhamento e
                                      encerramento de ocorrências.

  Correções                           Definir se o produto apenas
                                      apresentará ou também solicitará e
                                      executará alterações em sistemas de
                                      origem.

  Operações financeiras               Definir se qualquer operação
                                      financeira ficará fora do escopo
                                      inicial ou será considerada
                                      futuramente.

  Autorizações                        Definir responsáveis por solicitar,
                                      aprovar, executar e verificar
                                      ações.

  MVP                                 Aprovar capacidades prioritárias e
                                      hipótese de valor.

  Piloto                              Definir critérios e clientes
                                      participantes.

  Métricas                            Aprovar indicadores, baseline e
                                      metas.

  Disponibilidade e atualização       Definir expectativas de
                                      atualização, tolerância a
                                      indisponibilidade e operação
                                      degradada.

  Governança                          Definir responsáveis pelas decisões
                                      de negócio e pelo encerramento de
                                      ocorrências.
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## 12. Avaliação de saída do Discovery

### 12.1 Situação atual

  -----------------------------------------------------------------------
  Área                    Avaliação               Justificativa
  ----------------------- ----------------------- -----------------------
  Entendimento do         Bem encaminhado         Problemas de consulta,
  problema                                        consolidação e
                                                  investigação foram
                                                  identificados. Falta
                                                  quantificar impacto e
                                                  prioridade.

  Stakeholders            Parcialmente            Principais grupos
                          consolidado             identificados;
                                                  autoridade e
                                                  responsabilidades ainda
                                                  precisam de
                                                  confirmação.

  Usuários e perfis       Parcial                 Quantidade aproximada
                                                  foi mencionada, mas
                                                  perfis, permissões e
                                                  uso direto não foram
                                                  esclarecidos.

  Processo AS-IS          Parcial                 Há um fluxo resumido,
                                                  mas faltam etapas,
                                                  exceções, tempos e
                                                  critérios reais.

  Processo TO-BE          Parcial                 Resultados desejados
                                                  conhecidos, mas níveis
                                                  de atuação ainda não
                                                  definidos.

  Fontes e dependências   Parcial                 Fontes principais
                                                  identificadas; dados,
                                                  semântica, qualidade e
                                                  limitações precisam ser
                                                  detalhados.

  Regras de negócio       Parcial                 Conceitos importantes
                                                  identificados, mas
                                                  regras de
                                                  correspondência e
                                                  exceções não foram
                                                  formalizadas.

  Responsabilidades e     Parcial                 Limites foram
  escopo                                          discutidos, mas não
                                                  aprovados pelos
                                                  stakeholders.

  MVP e priorização       Pendente                Não há escopo inicial
                                                  aprovado nem critérios
                                                  suficientes de
                                                  priorização.

  Critérios de sucesso    Pendente                Indicadores candidatos
                                                  identificados, mas sem
                                                  baseline, metas ou
                                                  responsáveis.

  Riscos e restrições     Parcialmente            Principais riscos
                          consolidado             conhecidos, mas
                                                  impactos e tratamentos
                                                  precisam ser avaliados.
  -----------------------------------------------------------------------

### 12.2 Critério para avançar

O Discovery não precisa eliminar todas as incertezas. Entretanto, antes
de iniciar a especificação dos requisitos, é necessário:

-   Confirmar o problema prioritário e os usuários envolvidos.
-   Validar os processos mais relevantes.
-   Formalizar as principais regras de negócio conhecidas.
-   Delimitar responsabilidades e limites preliminares do produto.
-   Identificar as fontes e dependências essenciais.
-   Definir uma hipótese de valor e uma abordagem de validação do MVP.
-   Estabelecer indicadores ou um plano concreto para criar uma
    baseline.
-   Registrar incertezas, riscos, responsáveis e decisões pendentes.

### 12.3 Parecer

**Status: pronto para consolidação e validação com stakeholders; ainda
não aprovado para encerramento formal do Discovery.**

O material já permite iniciar a preparação de Requirements Engineering
de forma controlada, desde que as lacunas sejam tratadas como questões
em aberto e não como decisões tomadas.

A recomendação é realizar uma validação final com representantes de
negócio, equipe financeira e tecnologia. Essa validação deve confirmar o
problema prioritário, os processos, as responsabilidades, o escopo
inicial e os critérios de sucesso.

Após essa validação, o documento poderá ser revisado e o gate de saída
do Discovery formalmente aprovado.

------------------------------------------------------------------------

## 13. Próximas atividades

1.  Validar este documento com os stakeholders.
2.  Corrigir informações que não representem a realidade do negócio.
3.  Resolver ou atribuir responsáveis às decisões pendentes.
4.  Definir hipótese de valor, grupo piloto e indicadores.
5.  Revisar e aprovar o escopo preliminar.
6.  Formalizar a saída do Discovery.
7.  Iniciar Requirements Engineering, identificando e especificando
    requisitos funcionais e não funcionais.

------------------------------------------------------------------------

## Histórico de revisão

  -----------------------------------------------------------------------
  Versão                  Data                    Descrição
  ----------------------- ----------------------- -----------------------
  0.1                     13/11/2026              Primeira consolidação
                                                  do Discovery a partir
                                                  das entrevistas e
                                                  exercícios simulados.

  -----------------------------------------------------------------------
