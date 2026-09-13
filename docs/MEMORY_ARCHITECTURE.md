# Arquitetura de memória da Runa

A memória persistente da Runa combina dados estruturados, recuperação híbrida, relações entre entidades e uma camada humana de conhecimento.

A **Memory V1 já foi implantada e estabilizada**. O objetivo continua não sendo armazenar todas as conversas, mas preservar informações úteis para continuidade e execução segura, com proprietário, origem, visibilidade, retenção e tratamento de conflitos.

## Arquitetura atual

```text
Runa Runtime
        |
        v
Capability Registry + Policy
        |
        v
PostgreSQL / Supabase
        |
        +-- memória persistente e metadados
        +-- pgvector e ciclo de embeddings
        |
        +--> recuperação híbrida autorizada
        |
        +--> Obsidian
             projeção humana reconstruível
```

Responsabilidades:

- **PostgreSQL/Supabase:** fonte canônica da memória persistente e dos metadados de segurança;
- **Registry e Policy:** definem capabilities e aplicam autorização antes da operação de memória;
- **pgvector:** base para similaridade semântica dentro do banco já existente;
- **recuperação híbrida:** combina sinais determinísticos, textuais e semânticos somente depois do filtro de autorização;
- **Execution Ledger:** registra evidência causal mínima das operações sem transformar rastreabilidade em arquivo de conversas;
- **Obsidian:** projeção humana e interligada do conhecimento, reconstruível a partir da camada canônica.

## Segurança antes de relevância

A ordem é fixa: **autorização antes de relevância**.

Busca textual, similaridade vetorial, ranking e relações nunca devem ampliar o conjunto de dados que o interlocutor já está autorizado a consultar.

A primeira versão operacional também trata idempotência, duplicatas, conflitos e supersessão para reduzir efeitos repetidos ou memória contraditória.

## Embeddings são derivados

Embeddings são índices semânticos, não a memória em si.

A memória canônica continua utilizável mesmo sem vetor disponível. A arquitetura permite gerar ou regenerar embeddings de forma assíncrona e versionada. A próxima evolução é amadurecer esse worker e suas métricas antes de escolher otimizações de índice com base em volume e planos de consulta reais.

## Obsidian como projeção

O Obsidian materializa uma representação humana da memória e do conhecimento. O vault prioriza notas consolidadas e relações navegáveis, sem transformar Markdown em um segundo banco operacional.

Conceitualmente, notas podem ser vistas como nós e links como conexões de uma rede de conhecimento. Isso é uma analogia de organização e memória associativa, não uma rede neural de IA.

A projeção possui tratamento para conteúdo obsoleto e links seguros e pode ser reconstruída a partir da fonte canônica.

## Backup e recuperação

Memory V1 entrou em produção somente depois de validações de backup e restore. A estratégia protege a memória canônica e os artefatos necessários para reconstruir as camadas derivadas, mantendo rollback e recuperação como requisitos da arquitetura.

## Por que não usar um banco vetorial separado agora

Soluções dedicadas como Qdrant, Pinecone, Chroma, Weaviate ou Milvus podem ser úteis em outras escalas, mas acrescentariam infraestrutura, sincronização, backup e operação sem limite comprovado na stack atual.

A estratégia permanece PostgreSQL + pgvector primeiro. Um banco vetorial dedicado só deve ser reconsiderado se métricas reais mostrarem limites de volume, latência ou filtragem.

Mem0 continua sendo uma referência conceitual para desenho de memória, não uma fonte canônica do projeto.

## Memória não substitui fontes de verdade

A memória conecta contexto, mas não copia indiscriminadamente dados mantidos por outros sistemas.

- identidade e autorização permanecem estruturadas;
- agenda externa continua pertencendo ao sistema de agenda correspondente;
- código e estado de projetos permanecem nos repositórios canônicos;
- eventos de execução pertencem à camada de rastreabilidade;
- memória pode guardar contexto e referências sem substituir essas fontes.

## Próximas evoluções

1. observar a Memory V1 em uso real;
2. amadurecer geração assíncrona, retry e versionamento de embeddings;
3. medir qualidade e latência da recuperação híbrida;
4. evoluir a projeção Obsidian conforme relações reais de conhecimento aparecerem;
5. ampliar capabilities de memória somente com políticas e testes correspondentes;
6. reutilizar a mesma memória em voz e futuros canais.

## Princípio de evolução

A Runa evita adicionar uma tecnologia apenas porque ela é popular ou especializada. Uma nova dependência deve resolver um limite real e mensurável que a stack atual não consiga atender.
