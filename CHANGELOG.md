# Changelog público

Este arquivo registra mudanças relevantes na documentação pública e marcos de desenvolvimento que podem ser divulgados sem expor detalhes internos.

## 2026-09

### Núcleo conversacional e grounding

- roteamento de operações reconhecíveis avançou para uma abordagem predominantemente determinística, reduzindo dependência de classificação por modelo de linguagem no caminho operacional;
- modelo conversacional permanece desacoplado do roteamento e concentrado onde interpretação, raciocínio ou composição agregam valor;
- recomendações passaram por hardening de grounding para permanecerem apoiadas nos critérios e fatos fornecidos pelo usuário;
- respostas não devem acrescentar atributos, preferências ou justificativas não sustentadas apenas para tornar a recomendação mais completa;
- quando os dados fornecidos não forem suficientes para decidir, a direção é solicitar contexto adicional em vez de preencher lacunas por suposição;
- gates de regressão e rollback continuam sendo requisito para mudanças no comportamento conversacional.

### Memory V1

- primeira versão operacional da memória persistente implantada e estabilizada;
- PostgreSQL/Supabase consolidado como fonte canônica da memória;
- Registry e Policy passam a governar operações de memória com autorização determinística;
- leitura e escrita incorporam idempotência, deduplicação, tratamento de conflitos e supersessão;
- pgvector incorporado como base para recuperação semântica, mantendo embeddings como dados derivados e regeneráveis;
- recuperação híbrida preserva a regra de autorização antes de texto, vetor ou ranking;
- Obsidian passa de direção planejada para projeção humana reconstruível da memória e do conhecimento;
- backup e restore da camada de memória foram validados antes e depois da implantação;
- próxima evolução prioriza geração assíncrona e observabilidade de embeddings antes de qualquer infraestrutura vetorial adicional.

### Rastreabilidade e Runtime

- primeiro estágio observacional do Runtime implantado e estabilizado;
- execuções passaram a possuir correlação técnica interna para melhorar diagnóstico ponta a ponta;
- Execution Ledger dedicado registra somente eventos técnicos comprováveis e metadados mínimos, sem depender do conteúdo integral das mensagens;
- tracing e Ledger formam a fundação observável utilizada também pela Memory V1;
- Capability Registry e Policy Engine começaram a assumir responsabilidade operacional em uma capability sensível de forma controlada.

### Identidade e segurança

- reforçado o princípio de que confirmação não equivale a autorização;
- campos recebidos por mensagem, payload ou interpretação de IA não devem elevar privilégios por si só;
- fronteiras entre integrações privilegiadas passam a exigir autenticação própria antes de serem usadas para decisões administrativas;
- reconciliação futura de uma mesma pessoa em múltiplos canais foi aprofundada como design seguro, com prova de posse e sem merge automático por identificadores coincidentes.

### Novas capacidades em preparação

- obrigação recorrente e lembrete recorrente passaram a ter direção própria, separando compromisso futuro de gasto realizado e de tarefa comum;
- respostas de obrigações recorrentes foram humanizadas para apresentar antecedência e datas em linguagem natural e no contexto temporal adequado ao usuário, sem alterar regras de negócio, recorrência ou persistência;
- falhas de formatação desse retorno devem degradar de forma segura, sem inventar horários nem expor representações técnicas desnecessárias;
- Status da Runa evolui para distinguir informação funcional de usuário e diagnóstico técnico de audiência administrativa autenticada;
- voz passa a ser uma das próximas grandes frentes após a estabilização da Memory V1, reutilizando o mesmo runtime, identidade, políticas e memória.

### Reorganização pública

- criação de um repositório público limpo para apresentação da Runa;
- separação entre documentação pública e núcleo privado de produção;
- revisão da política de publicação para evitar dados operacionais e pessoais;
- arquitetura pública simplificada;
- roadmap e visão revisados;
- posição de direitos autorais e uso comercial documentada;
- página `docs/STATUS.md` mantida como resumo público do estado mais recente.

### Direção técnica

- memória persistente consolidada como combinação de dados estruturados, recuperação híbrida e conhecimento interligado;
- Obsidian consolidado como projeção humana reconstruível, sem substituir o banco canônico;
- multimodalidade, voz e casa inteligente mantidas no roadmap de longo prazo;
- observabilidade, autorização e recuperação continuam como prioridades estruturais;
- novas dependências vetoriais só devem ser introduzidas quando métricas reais demonstrarem necessidade.

### Hardening do núcleo conversacional

- regressão ampliada separou falhas reais de falsos positivos da suíte de testes;
- tarefas e idempotência financeira foram reconfirmadas sem regressão funcional;
- corrigido o tratamento de exclusão de lembretes identificados por data e hora em determinadas construções de linguagem natural;
- ampliado o reconhecimento de variantes naturais de comandos explícitos de memória, preservando deduplicação;
- validação de negócio fim a fim e diagnóstico do estágio real da falha passam a orientar correções antes de mudanças arquiteturais;
- permanecem em consolidação os cenários de família/grafo, edição de lembretes e validações externas controladas.
