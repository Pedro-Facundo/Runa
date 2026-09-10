# Estado atual da Runa

Atualizado em 10/09/2026.

Esta página resume apenas marcos que podem ser divulgados publicamente. Detalhes operacionais, versões internas, identificadores, topologia, credenciais e dados reais permanecem no ambiente privado.

## Fundação

**Estado:** avançada.

A Runa já possui uma base validada de persistência, mensageria, recuperação, prevenção de duplicidade, supervisão e backup/restore. O trabalho continua em hardening, desempenho e cobertura de testes.

## Rastreabilidade do Runtime

**Estado:** primeiro marco observacional implantado.

A Runa passou a atribuir uma correlação técnica estável às execuções para permitir diagnóstico ponta a ponta sem mudar o comportamento funcional percebido pelo usuário.

Esse primeiro estágio opera em modo observacional. Ele não concede autorização, não decide ações e não aparece nas mensagens do usuário.

O próximo passo é um Execution Ledger em shadow mode para registrar, com metadados mínimos, etapas comprováveis do ciclo de uma execução.

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

## Obrigações recorrentes

**Estado:** em preparação privada, ainda não disponível como funcionalidade concluída.

O projeto está separando explicitamente:

- obrigação futura;
- lembrete recorrente;
- gasto realizado;
- tarefa comum.

Essa distinção evita registrar uma dívida futura como gasto já ocorrido ou transformar qualquer compromisso financeiro em tarefa genérica.

## Persona e audiência

**Estado:** em evolução.

A Runa mantém a regra de que o resultado real de uma operação existe antes da camada narrativa. A persona pode mudar o tom, mas não altera sucesso, falha, autorização ou estado real.

Também está em desenvolvimento a separação entre informação funcional para usuários comuns e diagnóstico técnico para uma audiência administrativa autenticada.

## Memória e voz

Memória persistente seletiva, com uma camada de conhecimento interligado, continua como grande frente funcional futura. Depois do MVP de memória, voz deve usar o mesmo runtime, identidade e políticas das mensagens de texto.

## Próxima sequência pública

1. ampliar rastreabilidade com Execution Ledger em shadow;
2. reforçar trust boundaries e identidade/autorização;
3. introduzir Capability Registry e Policy Engine de forma gradual;
4. validar uma primeira capability read-only governada;
5. avançar memória persistente + conhecimento interligado;
6. iniciar voz com transcrição usando o mesmo núcleo;
7. expandir capacidades recorrentes, multimodalidade e automações proativas com segurança.

Consulte também [`ROADMAP.md`](ROADMAP.md) e [`ARCHITECTURE.md`](ARCHITECTURE.md).
