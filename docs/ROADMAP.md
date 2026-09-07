# Roadmap da Runa

Este roadmap mostra apenas a direção pública do projeto. Datas, detalhes operacionais e informações de produção podem mudar sem aviso.

## Fundação e infraestrutura

**Estado:** avançado

Prioridades:

- infraestrutura local e híbrida;
- isolamento de serviços;
- persistência estruturada;
- backups e recuperação;
- supervisão de serviços;
- testes de saúde;
- hardening progressivo;
- validação recorrente de recuperação;
- proteção progressiva contra exposição acidental de segredos em repositórios.

A base de backup e recuperação da Runa já possui validações reais. O trabalho restante está concentrado em hardening, retenção segura, desempenho e cobertura de testes.

## Núcleo conversacional

**Estado:** em desenvolvimento, com hardening pós-regressão validado

Prioridades:

- interpretação de linguagem natural;
- criação e consulta de tarefas;
- agenda e lembretes;
- confirmação de ações sensíveis;
- continuidade de contexto;
- correlação correta entre entrada, ação e resposta;
- prevenção de duplicidades;
- respostas mais naturais após automações.

## Runtime modular de capabilities

**Estado:** preparação arquitetural

A Runa está evoluindo para descrever suas ações como capabilities com contratos explícitos.

Objetivos:

- evitar regras duplicadas entre diferentes interfaces;
- separar interpretação, autorização e execução;
- declarar risco, permissões, confirmação e efeitos de cada capacidade;
- permitir migração gradual sem reescrever a stack existente;
- fazer texto, voz e futuras modalidades utilizarem o mesmo núcleo de ações.

A adoção será progressiva, começando em modo observacional antes de governar ações reais.

## Identidade, autorização e segurança

**Estado:** em desenvolvimento

Prioridades:

- identidade por interlocutor;
- isolamento de dados;
- permissões por contexto;
- auditoria;
- confirmação de operações sensíveis;
- tratamento contextual de relações e apelidos;
- políticas antes da execução de ações;
- separação explícita entre confirmação e autorização.

## Policy Engine

**Estado:** promovido a frente estrutural

Prioridades:

- identidade do solicitante;
- capability solicitada;
- recurso afetado;
- proprietário e contexto de compartilhamento;
- nível de risco;
- autorização;
- necessidade de confirmação;
- simulação versus execução;
- dados permitidos na resposta.

A IA pode ajudar a interpretar linguagem, mas permissões e decisões de risco devem permanecer determinísticas sempre que possível.

## Família e múltiplos usuários

**Estado:** parcialmente implementado e em consolidação

Prioridades:

- contexto separado por pessoa;
- relações familiares;
- agenda individual e compartilhada;
- apelidos contextuais;
- permissões diferentes por interlocutor;
- distinção entre relação conhecida e acesso autorizado;
- regras claras para informação privada e compartilhada.

## Rastreabilidade e observabilidade de produto

**Estado:** preparação arquitetural

Além de health checks e métricas da infraestrutura, a Runa evolui para rastrear de forma segura o ciclo de uma solicitação.

Objetivos:

- relacionar entrada, interpretação, decisão, execução e resposta;
- melhorar diagnóstico de retries e recovery;
- medir latência real das funções;
- detectar respostas fora de contexto;
- acompanhar falhas por integração;
- medir atraso de lembretes;
- evitar armazenar conteúdo privado além do necessário.

## Memória persistente

**Estado:** próxima grande frente funcional após o contrato de memória

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

A memória transacional e as permissões continuarão em armazenamento estruturado. A camada Obsidian não deve substituir o banco operacional.

## Voz e multimodalidade

**Estado:** planejado, com voz priorizada após o MVP de memória

Primeira prioridade multimodal:

- receber áudio;
- transcrever com Whisper;
- normalizar a entrada;
- encaminhar a transcrição ao mesmo núcleo usado por mensagens de texto;
- preservar identidade, contexto, autorização, rastreabilidade e prevenção de duplicidade.

Etapas posteriores:

- interpretação de imagens;
- documentos;
- OCR quando necessário;
- síntese de voz;
- persona vocal consistente.

## Financeiro pessoal

**Estado:** planejado

Prioridades:

- registro por linguagem natural;
- categorização;
- consultas por período;
- edição e exclusão controladas;
- resumos e relatórios.

## Observabilidade, Recovery e autorrecuperação

**Estado:** base de Recovery validada, evolução contínua

A camada de Recovery, ordem e prevenção de efeitos duplicados já possui uma base validada. A evolução continua em:

- health checks mais completos;
- classificação de falhas;
- histórico de disponibilidade;
- alertas relevantes;
- recuperação controlada;
- fallback entre recursos locais e externos;
- diagnóstico e relatórios de saúde;
- rastreabilidade ponta a ponta das solicitações.

## Persona e experiência

**Estado:** em evolução

Prioridades:

- identidade coerente em respostas normais, erros e estados degradados;
- linguagem adequada ao contexto;
- composição de mensagens sem mascarar o resultado real da operação;
- futura continuidade da persona em voz e outras interfaces.

## Casa inteligente

**Estado:** planejado

Prioridades de longo prazo:

- integração com ambientes domésticos;
- futura integração com Alexa e outras interfaces compatíveis;
- automações residenciais com autorização explícita;
- contexto e privacidade adequados a ambientes compartilhados.

## Inteligência operacional preditiva

**Estado:** planejado

A Runa poderá futuramente usar históricos e padrões para antecipar necessidades, sugerir ações e criar lembretes preventivos. Previsões deverão continuar explicáveis, separando fatos observados, estimativas e recomendações.

## Sequência atual em alto nível

1. concluir a consolidação das regressões atuais de contexto, confirmação, identidade e integrações;
2. introduzir contratos e rastreabilidade em modo observacional;
3. validar uma primeira capability de baixo risco através da nova camada de políticas;
4. fechar o contrato de memória e iniciar o MVP de memória persistente com Obsidian;
5. iniciar o MVP de voz com Whisper usando o mesmo runtime;
6. expandir multimodalidade, políticas e comportamento proativo gradualmente.

## Direção de longo prazo

A Runa pretende evoluir de uma assistente baseada em mensagens para uma plataforma pessoal de assistência e automação presente em diferentes interfaces, mantendo privacidade, rastreabilidade, reversibilidade e controle humano.

A regra de evolução é incorporar princípios que tragam ganho real de confiabilidade ou capacidade, sem trocar a stack por complexidade desnecessária.
