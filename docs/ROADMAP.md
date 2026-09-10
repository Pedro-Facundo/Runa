# Roadmap da Runa

Este roadmap mostra apenas a direção pública do projeto. Datas, detalhes operacionais e informações de produção podem mudar sem aviso.

## Fundação e infraestrutura

**Estado:** avançado.

Prioridades:

- infraestrutura local e híbrida;
- isolamento de serviços;
- persistência estruturada;
- backups e recuperação;
- supervisão de serviços;
- testes de saúde;
- hardening progressivo;
- validação recorrente de recuperação;
- proteção progressiva contra exposição acidental de segredos.

A base de backup e recuperação já possui validações reais. O trabalho restante se concentra em hardening, retenção segura, desempenho e cobertura de testes.

## Recovery, ordem e idempotência

**Estado:** base validada.

A Runa já possui mecanismos para persistir mensagens, evitar duplicidades, retomar processamento e reenviar respostas sem repetir efeitos já concluídos.

Essa fundação é preservada nas próximas etapas do Runtime.

## Núcleo conversacional

**Estado:** em desenvolvimento.

Prioridades:

- interpretação de linguagem natural;
- criação e consulta de tarefas;
- agenda e lembretes;
- confirmação de ações sensíveis;
- continuidade de contexto;
- correlação correta entre entrada, ação e resposta;
- prevenção de duplicidades;
- suporte a solicitações compostas;
- respostas mais naturais após automações.

## Runtime modular

**Estado:** tracing e Execution Ledger observacionais implantados.

A Runa está evoluindo para descrever suas ações como capabilities com contratos explícitos. A adoção é progressiva para não reescrever a stack existente nem introduzir governança sem capacidade de diagnóstico.

### Etapa concluída: tracing observacional

A primeira camada de correlação técnica já foi implantada em modo observacional.

Ela permite acompanhar uma execução internamente sem mudar autorização, negócio ou conteúdo exibido ao usuário.

### Etapa concluída: Execution Ledger

Um Execution Ledger dedicado também opera em shadow mode.

Ele registra eventos causais mínimos apenas quando a etapa pode ser comprovada por uma fonte técnica adequada, usando metadados mínimos e sem transformar rastreabilidade em arquivo de conversas.

Objetivos:

- relacionar etapas comprováveis de uma mesma execução;
- distinguir retry de nova ação;
- ajudar a investigar respostas fora de contexto;
- registrar estados sem depender de conteúdo privado integral;
- criar base para métricas de produto e futura governança.

### Capability Registry

Depois da estabilização da fundação observacional, a Runa passa a catalogar capabilities com risco, permissões, confirmação, idempotência e efeitos declarados.

### Policy Engine

Em seguida, decisões de autorização são comparadas em shadow mode antes de governar uma primeira capability read-only de baixo risco.

## Identidade, autorização e segurança

**Estado:** em desenvolvimento.

Prioridades:

- identidade por interlocutor e canal;
- isolamento de dados;
- permissões por contexto;
- auditoria;
- confirmação de operações sensíveis;
- tratamento contextual de relações e aliases;
- separação entre confirmação e autorização;
- trust boundaries autenticadas entre componentes privilegiados.

A IA pode ajudar a interpretar linguagem, mas permissões e decisões de risco permanecem determinísticas sempre que possível.

## Identidade multicanal

**Estado:** design em evolução.

Uma pessoa pode futuramente usar mais de um canal ou número sem perder continuidade. A reconciliação deve ser segura:

- nenhum merge automático apenas por nome ou identificador coincidente;
- prova de posse dos canais;
- política explícita;
- prevenção de enumeração de contas;
- conflitos de permissões ou integrações bloqueiam o merge até resolução;
- rollback e auditoria fazem parte do desenho.

## Família e múltiplos usuários

**Estado:** parcialmente implementado e em consolidação.

Prioridades:

- contexto separado por pessoa;
- relações familiares;
- agenda individual e compartilhada;
- aliases contextuais;
- permissões diferentes por interlocutor;
- distinção entre relação conhecida e acesso autorizado;
- regras claras para informação privada e compartilhada.

## Obrigações e lembretes recorrentes

**Estado:** em desenvolvimento privado.

A arquitetura representa obrigações futuras e recorrência sem confundir conceitos.

Objetivos:

- obrigação futura não vira gasto realizado antes da ocorrência;
- lembrete recorrente não vira tarefa comum;
- recorrência possui regra própria e materialização controlada;
- retries não duplicam ocorrências;
- meses com menos dias têm política explícita;
- edição, pausa e cancelamento são rastreáveis.

Essa capacidade ainda não deve ser tratada como funcionalidade pública concluída.

## Rastreabilidade e observabilidade de produto

**Estado:** tracing e Ledger ativos em modo observacional.

Além de health checks e métricas da infraestrutura, a Runa consegue correlacionar execuções e registrar eventos técnicos mínimos do ciclo de uma solicitação.

Objetivos seguintes:

- ampliar eventos somente quando houver fonte técnica comprovável;
- melhorar diagnóstico de retries e recovery;
- medir latência real das funções;
- detectar respostas fora de contexto;
- acompanhar falhas por integração;
- medir atraso de lembretes;
- evitar armazenar conteúdo privado além do necessário.

OpenTelemetry pode ser avaliado no futuro, mas não é requisito da fundação atual.

## Memória persistente

**Estado:** próxima grande frente funcional depois da fundação do Runtime.

Prioridades:

- preferências duráveis;
- contexto pessoal útil;
- relações entre pessoas;
- retenção seletiva;
- distinção entre memória e compromisso;
- aliases contextuais;
- conhecimento interligado;
- proprietário e proveniência explícitos;
- políticas de sensibilidade e visibilidade;
- tratamento de conflitos e informações substituídas;
- Obsidian como camada complementar de memória associativa e conhecimento humano-legível.

A memória transacional e as permissões continuam em armazenamento estruturado. A camada de conhecimento não substitui o banco operacional.

## Voz e multimodalidade

**Estado:** planejado, com voz priorizada após o MVP de memória.

Primeira prioridade multimodal:

- receber áudio;
- transcrever;
- normalizar a entrada;
- encaminhar a transcrição ao mesmo núcleo usado por texto;
- preservar identidade, contexto, autorização, rastreabilidade e prevenção de duplicidade.

Etapas posteriores:

- interpretação de imagens;
- documentos;
- OCR quando necessário;
- síntese de voz;
- persona vocal consistente.

## Persona, Status e experiência

**Estado:** em evolução.

Prioridades:

- identidade coerente em respostas normais, erros e estados degradados;
- linguagem adequada ao contexto;
- resultado operacional antes da composição narrativa;
- informação funcional para usuário comum;
- diagnóstico técnico somente para audiência administrativa autenticada;
- suporte ao usuário sem compartilhamento automático de contexto privado;
- futura continuidade da persona em voz e outras interfaces.

## Financeiro pessoal

**Estado:** em evolução e expansão planejada.

Prioridades:

- registro por linguagem natural;
- categorização;
- consultas por período;
- edição e exclusão controladas;
- resumos e relatórios;
- integração futura com obrigações recorrentes sem confundir previsão com gasto realizado.

## Observabilidade, Recovery e autorrecuperação

**Estado:** Recovery validado, tracing + Ledger ativos, evolução contínua.

A evolução continua em:

- health checks mais completos;
- classificação de falhas;
- histórico de disponibilidade;
- alertas relevantes;
- recuperação controlada;
- fallback entre recursos locais e externos;
- diagnóstico e relatórios de saúde;
- rastreabilidade ponta a ponta.

## Casa inteligente

**Estado:** planejado.

Prioridades de longo prazo:

- integração com ambientes domésticos;
- interfaces compatíveis;
- automações residenciais com autorização explícita;
- contexto e privacidade adequados a ambientes compartilhados.

## Inteligência operacional preditiva

**Estado:** planejado.

A Runa poderá usar históricos e padrões para antecipar necessidades, sugerir ações e criar lembretes preventivos. Previsões devem continuar explicáveis, separando fatos observados, estimativas e recomendações.

## Sequência atual em alto nível

1. preservar Recovery, tracing e Execution Ledger já implantados;
2. estabilizar o baseline observacional pós-Ledger;
3. reforçar trust boundaries, identidade e autorização;
4. executar Capability Registry e Policy Engine em shadow;
5. promover uma capability read-only de baixo risco;
6. avançar memória persistente + conhecimento interligado;
7. iniciar voz usando o mesmo runtime;
8. expandir obrigações recorrentes, multimodalidade e automações proativas de forma gradual.

Algumas frentes podem avançar em paralelo quando forem independentes e tiverem testes, rollback e gates próprios.

## Direção de longo prazo

A Runa pretende evoluir de uma assistente baseada em mensagens para uma plataforma pessoal de assistência e automação presente em diferentes interfaces, mantendo privacidade, rastreabilidade, reversibilidade e controle humano.

A regra de evolução é incorporar princípios que tragam ganho real de confiabilidade ou capacidade, sem trocar a stack por complexidade desnecessária.
