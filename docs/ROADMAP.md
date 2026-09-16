# Roadmap da Runa

Este roadmap mostra apenas a direção pública do projeto. Datas, detalhes operacionais e informações de produção podem mudar sem aviso.

## Fundação e infraestrutura

**Estado:** avançado.

A base de persistência, backup, recuperação, supervisão e health checks possui validações reais. O trabalho restante se concentra em hardening, retenção segura, desempenho e cobertura de testes.

## Recovery, ordem e idempotência

**Estado:** base validada.

A Runa possui mecanismos para persistir mensagens, evitar duplicidades, retomar processamento e reenviar respostas sem repetir efeitos já concluídos. Essa fundação é preservada nas próximas etapas do Runtime.

## Núcleo conversacional

**Estado:** em desenvolvimento, com roteamento determinístico já aplicado a operações reconhecíveis.

Prioridades incluem interpretação de linguagem natural, agenda, tarefas, lembretes, confirmações, continuidade de contexto, solicitações compostas e respostas naturais após automações.

A arquitetura reduz a dependência de classificação por modelo de linguagem para comandos operacionais explícitos. Operações reconhecíveis podem ser resolvidas deterministicamente, com contratos e autorização próprios, enquanto casos sem evidência suficiente devem falhar de forma segura para conversa ou clarificação. Modelos de IA permanecem desacoplados dessa camada e são usados onde interpretação, raciocínio e composição conversacional agregam valor.

O grounding das respostas também passa a ser uma prioridade explícita: recomendações devem permanecer apoiadas nos fatos e critérios fornecidos pelo usuário, sem acrescentar propriedades ou preferências não sustentadas. Critério insuficiente deve levar à solicitação de contexto adicional, não à fabricação de justificativas.

## Runtime modular

**Estado:** fundação observável ativa e primeira aplicação governada em produção.

Tracing e Execution Ledger fornecem correlação e evidência causal mínima. Capability Registry e Policy Engine passaram a ser usados operacionalmente pela Memory V1, preservando autorização determinística e separação entre conteúdo privado e rastreabilidade.

Próximos objetivos:

- observar o comportamento em uso real;
- ampliar capabilities governadas de forma gradual;
- manter contratos explícitos de risco, autorização, idempotência e efeitos;
- preservar rollback e comparação com comportamento validado.

## Identidade, autorização e segurança

**Estado:** em desenvolvimento.

Prioridades:

- identidade por interlocutor e canal;
- isolamento de dados;
- permissões por contexto;
- auditoria;
- confirmação de operações sensíveis;
- aliases e relações sem concessão automática de acesso;
- trust boundaries autenticadas entre componentes privilegiados;
- futura reconciliação multicanal com prova de posse.

## Família e múltiplos usuários

**Estado:** parcialmente implementado e em consolidação.

A direção continua separar contexto, relações, agenda e permissões por pessoa, distinguindo relação conhecida de acesso autorizado.

## Obrigações e lembretes recorrentes

**Estado:** em desenvolvimento privado.

A arquitetura representa obrigações futuras e recorrência sem confundir obrigação, gasto realizado, lembrete e tarefa. Essa capacidade ainda não deve ser tratada como funcionalidade pública concluída.

## Memória persistente

**Estado:** Memory V1 implantada e estabilizada.

A primeira versão operacional combina:

- PostgreSQL/Supabase como memória canônica;
- Registry e Policy para controlar operações;
- idempotência, deduplicação, conflitos e supersessão;
- pgvector como base semântica derivada;
- recuperação híbrida com autorização antes de relevância;
- Obsidian como projeção humana reconstruível;
- backup e restore validados.

Próximas prioridades:

- observar qualidade e latência em uso real;
- amadurecer geração assíncrona de embeddings, retry e versionamento;
- reindexar de forma controlada quando necessário;
- avaliar otimizações de índice somente com volume e planos de consulta reais;
- evoluir relações e conhecimento sem transformar o Obsidian em segunda fonte de verdade.

## Voz e multimodalidade

**Estado:** voz priorizada na sequência pós-Memory V1.

Primeira etapa:

- receber áudio;
- transcrever;
- normalizar a entrada;
- encaminhar ao mesmo núcleo usado por texto;
- preservar identidade, contexto, autorização, memória, rastreabilidade e prevenção de duplicidade.

Etapas posteriores incluem imagens, documentos, OCR quando necessário, síntese de voz e persona vocal consistente.

## Persona, Status e experiência

**Estado:** em evolução.

A identidade narrativa permanece independente do modelo de IA. Resultado operacional e autorização existem antes da composição narrativa. A mesma persona deve futuramente continuar em voz e outras interfaces.

## Financeiro pessoal

**Estado:** em evolução e expansão planejada.

Prioridades incluem registro por linguagem natural, categorização, consultas, edição/exclusão controladas, resumos e integração futura com obrigações recorrentes sem confundir previsão com gasto realizado.

## Observabilidade, Recovery e autorrecuperação

**Estado:** Recovery validado, tracing + Ledger ativos, evolução contínua.

A evolução continua em health checks, classificação de falhas, histórico de disponibilidade, alertas, recuperação controlada, fallback e rastreabilidade ponta a ponta.

## Casa inteligente

**Estado:** planejado.

Alexa e outros dispositivos podem funcionar como interfaces da mesma Runa, enquanto memória, contexto, políticas, orquestração e personalidade permanecem na camada central.

## Inteligência operacional preditiva

**Estado:** planejado.

A Runa poderá usar históricos e padrões para antecipar necessidades e sugerir ações, sempre separando fatos observados, estimativas e recomendações.

## Sequência atual em alto nível

1. observar e consolidar o roteamento determinístico e o grounding das respostas;
2. estabilizar e observar a Memory V1 em produção;
3. amadurecer embeddings assíncronos e recuperação híbrida;
4. continuar hardening de identidade, autorização e trust boundaries;
5. ampliar gradualmente capabilities governadas;
6. iniciar voz reutilizando Runtime, Policy e Memory V1;
7. expandir obrigações recorrentes, multimodalidade e automações proativas de forma gradual;
8. avançar integrações de ambiente e casa inteligente quando os controles de identidade e autorização estiverem maduros.

Algumas frentes podem avançar em paralelo quando forem independentes e tiverem testes, rollback e gates próprios.

## Direção de longo prazo

A Runa pretende evoluir de uma assistente baseada em mensagens para uma plataforma pessoal de assistência e automação contextual, proativa, integrada ao ambiente e com continuidade, inspirada na experiência de um assistente estilo JARVIS sem copiar personagem ou identidade.

A Runa mantém identidade, persona e personalidade próprias e independentes do modelo de IA utilizado. A regra de evolução é incorporar princípios que tragam ganho real de confiabilidade ou capacidade, sem trocar a stack por complexidade desnecessária.
