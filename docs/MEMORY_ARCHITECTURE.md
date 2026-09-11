# Arquitetura de memória da Runa

A memória persistente da Runa é planejada como uma combinação de dados estruturados, recuperação semântica, relações entre entidades e uma camada humana de conhecimento.

O objetivo não é armazenar todas as conversas. A Runa deve preservar apenas informações úteis para continuidade, personalização e execução segura, com proprietário, origem, visibilidade, retenção e tratamento de conflitos.

## Arquitetura escolhida

A primeira versão será construída sobre a stack já adotada pelo projeto:

```text
Runa Runtime e políticas
        |
        v
PostgreSQL / Supabase
        |
        +-- memória persistente e metadados
        +-- pgvector para embeddings e busca semântica
        |
        +--> Obsidian
             visão humana e grafo navegável
```

Responsabilidades:

- **PostgreSQL/Supabase:** fonte canônica da memória persistente e dos metadados de segurança;
- **pgvector:** busca por similaridade semântica dentro do banco já existente;
- **Runtime e políticas:** controlam o que pode ser salvo, consultado e retornado;
- **Obsidian:** camada humana e interligada de conhecimento, sem substituir o banco operacional.

## Por que não usar um banco vetorial separado no MVP

Soluções dedicadas como Qdrant, Pinecone, Chroma, Weaviate ou Milvus podem ser úteis em outras escalas, mas acrescentariam nova infraestrutura, sincronização, backup e operação antes de existir necessidade comprovada.

A estratégia da Runa é aproveitar PostgreSQL + pgvector primeiro e reconsiderar um banco vetorial dedicado somente se métricas reais mostrarem limites de volume, latência ou filtragem.

Mem0 continua sendo uma referência conceitual para desenho de memória, não uma fonte canônica do projeto.

## Memória não substitui fontes de verdade

A memória conecta contexto, mas não deve copiar indiscriminadamente dados mantidos por outros sistemas.

Exemplos:

- identidade e autorização permanecem estruturadas no banco;
- agenda externa continua pertencendo ao sistema de agenda correspondente;
- código e estado de projetos permanecem nos repositórios canônicos;
- eventos de execução pertencem à camada de rastreabilidade;
- memória pode guardar contexto e referências a essas fontes sem substituí-las.

Isso reduz o risco de a assistente lembrar corretamente uma informação que já deixou de ser verdadeira na fonte original.

## Recuperação híbrida

A consulta de memória poderá combinar:

- filtros determinísticos de proprietário e visibilidade;
- busca textual;
- similaridade vetorial;
- relações entre entidades;
- confiança;
- atualidade;
- status e supersessão.

A ordem de segurança é fixa:

**autorização antes de relevância.**

Uma busca semanticamente próxima nunca pode expor dados fora do escopo autorizado.

## Embeddings

Embeddings são índices semânticos, não a memória em si.

A memória canônica deve continuar utilizável mesmo que um vetor ainda não exista ou precise ser regenerado. O sistema deve registrar qual modelo e versão produziram cada embedding para permitir reindexação futura.

A disponibilidade de um computador pessoal ou de um modelo local específico não deve ser requisito para a leitura básica da memória.

## Obsidian

O Obsidian será usado como uma representação humana da memória e do conhecimento.

Em vez de criar obrigatoriamente um arquivo para cada fato atômico, o vault deve priorizar notas consolidadas por entidades, como:

```text
Pessoas/
Projetos/
Decisoes/
Lugares/
Conhecimento/
```

Isso permite navegar pelas relações e decisões sem transformar Markdown em um segundo banco operacional.

## Capabilities de memória

A direção arquitetural prevê capacidades separadas:

```text
memory.read
memory.propose
memory.save
memory.supersede
```

Um modelo pode sugerir que uma informação parece útil para memória. Persistir de fato continua sujeito às políticas de propriedade, sensibilidade, visibilidade, retenção, duplicata e conflito.

## Sequência de implantação

1. estabilizar os gates do Runtime que antecedem memória;
2. evoluir o schema de memória para o contrato completo;
3. implementar escrita e leitura estruturadas;
4. adicionar pgvector e embeddings;
5. implementar recuperação híbrida;
6. criar a projeção Obsidian por entidades;
7. validar backup e restore;
8. ampliar gradualmente para novos contextos e projetos.

## Princípio de evolução

A Runa evita adicionar uma tecnologia apenas porque ela é popular ou especializada. Uma nova dependência deve resolver um limite real e mensurável que a stack atual não consiga atender.
