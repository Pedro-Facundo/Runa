# Changelog público

Este arquivo registra mudanças relevantes na documentação pública e marcos de desenvolvimento que podem ser divulgados sem expor detalhes internos.

## 2026-09

### Rastreabilidade e Runtime

- primeiro estágio observacional do Runtime implantado e estabilizado;
- execuções passaram a possuir correlação técnica interna para melhorar diagnóstico ponta a ponta;
- o tracing permanece em modo observacional e não muda autorização, decisão de negócio ou conteúdo exibido ao usuário;
- regressão pós-implantação confirmou estabilidade das capacidades cobertas e cleanup dos dados de teste;
- próximo estágio definido: Execution Ledger em shadow mode, com metadados mínimos e sem armazenar conteúdo privado desnecessário;
- Capability Registry e Policy Engine continuam em adoção progressiva, depois da fundação observacional.

### Identidade e segurança

- reforçado o princípio de que confirmação não equivale a autorização;
- campos recebidos por mensagem, payload ou interpretação de IA não devem elevar privilégios por si só;
- fronteiras entre integrações privilegiadas passam a exigir autenticação própria antes de serem usadas para decisões administrativas;
- reconciliação futura de uma mesma pessoa em múltiplos canais foi aprofundada como design seguro, com prova de posse e sem merge automático por identificadores coincidentes.

### Novas capacidades em preparação

- obrigação recorrente e lembrete recorrente passaram a ter direção própria, separando compromisso futuro de gasto realizado e de tarefa comum;
- Status da Runa evolui para distinguir informação funcional de usuário e diagnóstico técnico de audiência administrativa autenticada;
- essas frentes continuam em validação privada e não devem ser interpretadas como funcionalidades já liberadas.

### Reorganização pública

- criação de um repositório público limpo para apresentação da Runa;
- separação entre documentação pública e núcleo privado de produção;
- revisão da política de publicação para evitar dados operacionais e pessoais;
- arquitetura pública simplificada;
- roadmap e visão revisados;
- posição de direitos autorais e uso comercial documentada;
- nova página `docs/STATUS.md` criada para refletir o estado público mais recente.

### Direção técnica

- memória persistente tratada como combinação de dados estruturados e conhecimento interligado;
- Obsidian incluído como direção planejada para memória associativa;
- multimodalidade, voz e casa inteligente mantidas no roadmap de longo prazo;
- observabilidade, autorização e recuperação continuam como prioridades estruturais;
- ordem arquitetural atualizada para tracing, Execution Ledger, Registry/Policy e primeira capability governada antes das expansões mais sensíveis.

### Hardening do núcleo conversacional

- regressão ampliada separou falhas reais de falsos positivos da suíte de testes;
- tarefas e idempotência financeira foram reconfirmadas sem regressão funcional;
- corrigido o tratamento de exclusão de lembretes identificados por data e hora em determinadas construções de linguagem natural;
- ampliado o reconhecimento de variantes naturais de comandos explícitos de memória, preservando deduplicação;
- validação de negócio fim a fim e diagnóstico do estágio real da falha passam a orientar correções antes de mudanças arquiteturais;
- permanecem em consolidação os cenários de família/grafo, edição de lembretes e validações externas controladas.
