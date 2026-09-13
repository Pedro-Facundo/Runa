# Direção de evolução da Runa

Data: 13/09/2026

A Runa evolui como uma inteligência pessoal persistente, multimodal e local-first. O objetivo não é depender de um único modelo, provedor ou canal, mas reunir memória, contexto, voz, visão, capabilities e execução governada em um único núcleo.

## Princípios públicos

- local-first, com cloud opcional para escalada de capacidade;
- um único Runtime para texto, voz, imagem e futuras modalidades;
- memória persistente governada e contextual;
- Supabase/PostgreSQL como fonte canônica, pgvector para recuperação semântica e Obsidian como projeção humana reconstruível;
- voz e visão usam a mesma identidade, autorização e capabilities do texto;
- latência e naturalidade de interação são requisitos de produto;
- pesquisa externa não vira memória permanente automaticamente;
- fine-tuning é posterior, controlado, versionado e reversível;
- Conclave é um modo de raciocínio sob demanda, não a arquitetura padrão;
- Skills e capabilities reutilizáveis têm prioridade sobre uma grande quantidade de agentes permanentes;
- MCP pode ser suportado como protocolo de integração, sem se tornar dependência estrutural;
- novos bancos vetoriais só entram diante de necessidade comprovada.

## Próxima direção de experiência

A evolução será incremental:

1. estabilizar e canonizar o estado atual da Memory V1;
2. introduzir voz usando o mesmo Runtime;
3. evoluir para conversa com baixa latência, sessões e interrupção natural;
4. adicionar visão sob demanda;
5. consolidar Context Fusion entre pessoa, sessão, projeto, memória e observações;
6. introduzir wake word somente depois do voice loop estar estável;
7. ampliar Skills, Capability Registry e roteamento inteligente entre modelos locais e cloud opcional;
8. usar Conclave apenas para problemas que realmente se beneficiem de múltiplas perspectivas;
9. permitir pesquisa e consolidação de conhecimento com proveniência e validação;
10. avaliar fine-tuning apenas quando houver dados reais suficientes e ganho mensurável.

## Marco multimodal

Um dos marcos de experiência será permitir uma interação como:

> “Runa, olha isso. É o modelo que a gente tinha escolhido para aquele projeto?”

Para responder corretamente, a Runa precisa combinar percepção visual, identidade, memória, contexto de projeto, raciocínio e resposta natural, sem criar um pipeline paralelo ao Runtime principal.

A implementação privada, os gates operacionais, riscos e detalhes de infraestrutura permanecem no `Runa-Core` e no `Accio-Infra`.
