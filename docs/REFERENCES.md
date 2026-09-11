# Referências técnicas

Esta página reúne tecnologias e projetos que servem como referência para a evolução da Runa.

A presença de um projeto nesta lista não significa que seu código faça parte da Runa. Cada componente permanece sujeito à sua própria licença e aos seus próprios termos.

## Orquestração e automação

- [n8n](https://github.com/n8n-io/n8n): referência para workflows e automações.

## IA local

- [Ollama](https://github.com/ollama/ollama): execução e gerenciamento de modelos locais.

## Mensageria

- [Baileys](https://github.com/WhiskeySockets/Baileys): integração com WhatsApp.

## Banco e persistência

- [Supabase](https://github.com/supabase/supabase): PostgreSQL, APIs, autenticação e políticas de acesso.
- [pgvector](https://github.com/pgvector/pgvector): extensão PostgreSQL escolhida para embeddings e recuperação semântica do Memory V1, preservando o banco existente como fonte canônica.

## Voz e multimodalidade

- [Whisper](https://github.com/openai/whisper): reconhecimento e transcrição de fala.
- [Piper](https://github.com/OHF-Voice/piper1-gpl): referência para síntese de voz local. A licença deve ser analisada antes de qualquer distribuição comercial.

## Casa inteligente

- [Home Assistant](https://github.com/home-assistant/core): referência para automação residencial e integração de dispositivos.
- [Alexa Skills Kit SDK for Node.js](https://github.com/alexa/alexa-skills-kit-sdk-for-nodejs): referência oficial para possíveis integrações futuras com Alexa.

## Containers e infraestrutura

- [Docker Compose](https://github.com/docker/compose): composição de serviços containerizados.
- [Portainer](https://github.com/portainer/portainer): referência para gestão de ambientes Docker.

## Conhecimento e memória

- [Obsidian](https://obsidian.md/): camada humana e interligada de conhecimento em Markdown. No Memory V1 ele funciona como projeção navegável, não como banco operacional nem como fonte primária de cada memória atômica.
- [Mem0](https://github.com/mem0ai/mem0): referência conceitual para extração, retenção e recuperação de memória. Não é a camada canônica escolhida para a Runa.

A arquitetura escolhida está descrita em [`MEMORY_ARCHITECTURE.md`](MEMORY_ARCHITECTURE.md).

## Critério de adoção

Uma dependência externa deve ser incorporada somente quando trouxer benefício técnico claro. Antes da adoção, devem ser avaliados licença, manutenção, segurança, impacto comercial, portabilidade e risco de dependência excessiva.

Para memória, um banco vetorial dedicado só deve ser reconsiderado se PostgreSQL + pgvector demonstrar limites reais de volume, latência ou filtragem. A especialização de uma ferramenta, sozinha, não é motivo suficiente para aumentar a stack.
