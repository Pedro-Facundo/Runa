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
- validação recorrente de recuperação.

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

A regressão recente confirmou o funcionamento de tarefas e da idempotência financeira e resultou em correções pontuais no tratamento de exclusão de lembretes por data/hora e no reconhecimento de variantes naturais de comandos de memória. Esses cenários passaram a integrar a validação do núcleo, sem alterar a arquitetura pública do projeto.

## Identidade, autorização e segurança

**Estado:** em desenvolvimento

Prioridades:

- identidade por interlocutor;
- isolamento de dados;
- permissões por contexto;
- auditoria;
- confirmação de operações sensíveis;
- tratamento contextual de relações e apelidos;
- políticas antes da execução de ações.

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

## Memória persistente

**Estado:** próxima grande frente funcional

Prioridades:

- preferências duráveis;
- contexto pessoal útil;
- relações entre pessoas;
- retenção seletiva;
- distinção entre memória e compromisso;
- aliases contextuais;
- conhecimento interligado;
- Obsidian como camada complementar de memória associativa e conhecimento humano-legível.

A memória transacional e as permissões continuarão em armazenamento estruturado. A camada Obsidian não deve substituir o banco operacional.

## Voz e multimodalidade

**Estado:** planejado, com voz priorizada após o MVP de memória

Primeira prioridade multimodal:

- receber áudio;
- transcrever com Whisper;
- encaminhar a transcrição ao mesmo núcleo usado por mensagens de texto;
- preservar identidade, contexto, autorização e prevenção de duplicidade.

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

## Policy Engine

**Estado:** planejado

Prioridades:

- identidade do solicitante;
- recurso afetado;
- nível de risco;
- autorização;
- necessidade de confirmação;
- simulação versus execução;
- dados permitidos na resposta.

## Observabilidade, Recovery e autorrecuperação

**Estado:** base de Recovery validada, evolução contínua

A camada de Recovery, ordem e prevenção de efeitos duplicados já possui uma base validada. A evolução continua em:

- health checks mais completos;
- classificação de falhas;
- histórico de disponibilidade;
- alertas relevantes;
- recuperação controlada;
- fallback entre recursos locais e externos;
- diagnóstico e relatórios de saúde.

## Voz, persona e casa inteligente

**Estado:** planejado

Prioridades de longo prazo:

- identidade de voz consistente;
- respostas faladas;
- integração com ambientes domésticos;
- futura integração com Alexa e outras interfaces compatíveis;
- automações residenciais com autorização explícita.

## Inteligência operacional preditiva

**Estado:** planejado

A Runa poderá futuramente usar históricos e padrões para antecipar necessidades, sugerir ações e criar lembretes preventivos. Previsões deverão continuar explicáveis, separando fatos observados, estimativas e recomendações.

## Sequência atual em alto nível

1. concluir a regressão externa controlada de integrações e consolidar os problemas conhecidos de família/grafo e edição de lembretes;
2. iniciar o MVP de memória persistente com Obsidian;
3. iniciar o MVP de voz com Whisper;
4. expandir multimodalidade, políticas e comportamento proativo gradualmente.

## Direção de longo prazo

A Runa pretende evoluir de uma assistente baseada em mensagens para uma plataforma pessoal de assistência e automação presente em diferentes interfaces, mantendo privacidade, rastreabilidade, reversibilidade e controle humano.
