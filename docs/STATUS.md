# Estado atual da Runa

Atualizado em 13/09/2026.

Esta página resume apenas marcos que podem ser divulgados publicamente. Detalhes operacionais, versões internas, identificadores, topologia, credenciais e dados reais permanecem no ambiente privado.

## Fundação

**Estado:** avançada.

A Runa já possui uma base validada de persistência, mensageria, recuperação, prevenção de duplicidade, supervisão e backup/restore. O trabalho continua em hardening, desempenho e cobertura de testes.

## Rastreabilidade do Runtime

**Estado:** tracing e Execution Ledger implantados, com uso ampliado pela Memory V1.

A Runa atribui correlação técnica estável às execuções para permitir diagnóstico ponta a ponta sem depender do conteúdo integral das mensagens. O Execution Ledger registra eventos causais mínimos e comprováveis, preservando a separação entre rastreabilidade e conteúdo privado.

A Memory V1 passou a utilizar essa fundação junto com Registry e Policy para operações de memória controladas.

## Núcleo conversacional

**Estado:** funcional em várias capacidades, ainda em evolução.

Agenda, tarefas, lembretes e confirmações continuam recebendo melhorias de contexto, confiabilidade, idempotência e testes de regressão.

## Identidade e segurança

**Estado:** em desenvolvimento.

A direção atual reforça que:

- confirmação não substitui autorização;
- relações pessoais não concedem acesso automático;
- afirmações de privilégio não devem ser aceitas apenas porque apareceram em uma mensagem ou payload;
- integrações que transportam contexto privilegiado devem provar sua origem por uma trust boundary autenticada;
- a IA pode interpretar intenção, mas não eleva privilégios.

Também está em design uma futura reconciliação de múltiplos canais pertencentes à mesma pessoa, sempre com prova de posse e sem merge automático por nome ou identificador coincidente.

## Memória persistente

**Estado:** Memory V1 implantada e estabilizada.

A primeira versão operacional da memória persistente entrou em produção com uma arquitetura híbrida e reversível:

- PostgreSQL/Supabase permanece como fonte canônica;
- operações de memória passam por Registry e Policy com autorização determinística;
- escrita e leitura possuem idempotência, tratamento de duplicatas, conflitos e supersessão;
- pgvector está disponível como base para recuperação semântica, sem tornar embeddings obrigatórios para leitura básica;
- recuperação híbrida aplica autorização antes de texto, similaridade ou ranking;
- Obsidian funciona como projeção humana reconstruível do conhecimento, e não como segundo banco operacional;
- backup e restore da camada de memória foram validados antes e depois da implantação.

A próxima evolução técnica é amadurecer a geração assíncrona de embeddings e observar volume e consultas reais antes de introduzir índices ou infraestrutura vetorial adicional.

## Obrigações recorrentes

**Estado:** em desenvolvimento privado, ainda não disponível como funcionalidade concluída.

O projeto está separando explicitamente obrigação futura, lembrete recorrente, gasto realizado e tarefa comum para evitar efeitos incorretos no financeiro e na agenda.

## Persona e audiência

**Estado:** em evolução.

A Runa mantém a regra de que o resultado real de uma operação existe antes da camada narrativa. A persona pode mudar o tom, mas não altera sucesso, falha, autorização ou estado real.

Também está em desenvolvimento a separação entre informação funcional para usuários comuns e diagnóstico técnico para uma audiência administrativa autenticada.

## Voz e multimodalidade

**Estado:** planejado para a sequência pós-Memory V1.

Voz deve reutilizar o mesmo runtime, identidade, políticas e memória das mensagens de texto. Imagens, documentos e outras entradas multimodais entram progressivamente depois dessa fundação.

## Próxima sequência pública

1. estabilizar e observar a Memory V1 em uso real;
2. amadurecer embeddings assíncronos e recuperação semântica sem criar dependência desnecessária;
3. continuar o hardening de identidade, autorização e trust boundaries;
4. ampliar gradualmente o uso de capabilities governadas;
5. iniciar voz com transcrição usando o mesmo núcleo e a mesma memória;
6. expandir capacidades recorrentes, multimodalidade e automações proativas com segurança.

Consulte também [`ROADMAP.md`](ROADMAP.md), [`MEMORY_ARCHITECTURE.md`](MEMORY_ARCHITECTURE.md) e [`ARCHITECTURE.md`](ARCHITECTURE.md).
