# Segurança e privacidade

A documentação pública da Runa segue uma regra simples: mostrar como o projeto funciona sem expor detalhes que possam comprometer pessoas, contas ou infraestrutura.

## Nunca publicar

Este repositório não deve receber:

- senhas, tokens, chaves de API ou chaves privadas;
- arquivos `.env` ou configurações de produção;
- credenciais de banco de dados;
- dumps, backups ou logs privados;
- números de telefone reais usados na operação;
- identificadores privados de usuários;
- mensagens reais de usuários;
- endereços internos ou externos da infraestrutura quando não forem necessários para documentação pública;
- URLs administrativas;
- nomes de clientes ou informações comerciais confidenciais;
- caminhos locais que revelem detalhes desnecessários da estrutura de produção;
- exports de workflows contendo dados reais ou referências operacionais sensíveis.

## Princípios de autorização

A arquitetura da Runa separa interpretação, identidade e autorização.

- linguagem natural não concede privilégio;
- um modelo de IA não deve elevar o nível de acesso de um usuário;
- confirmação de uma ação não substitui autorização para acessar o recurso;
- relação familiar ou pessoal não concede acesso automático a dados de outra pessoa;
- campos administrativos recebidos em payloads não são confiáveis apenas porque estão presentes;
- integrações que transportam contexto privilegiado precisam provar sua origem por uma trust boundary autenticada;
- quando a origem privilegiada não puder ser comprovada, o comportamento deve ser conservador.

Os mecanismos concretos de autenticação usados no ambiente real não são publicados aqui.

## Identidade multicanal

Uma mesma pessoa pode futuramente usar mais de um canal ou número. A Runa não deve mesclar identidades automaticamente apenas porque encontrou nome, e-mail ou outro identificador coincidente.

Reconciliações desse tipo devem exigir prova de posse, política explícita, proteção contra enumeração de contas, auditoria e estratégia de rollback.

## Observabilidade com privacidade

Tracing e futuros registros de execução devem armazenar somente os metadados necessários para diagnóstico e causalidade.

O objetivo não é copiar conversas inteiras para logs. Sempre que um evento puder ser comprovado por identificadores, estado, timestamp e reason code, o conteúdo privado deve permanecer fora da telemetria.

## Princípio de publicação

Documentação pública usa exemplos genéricos, nomes fictícios, identificadores de teste e diagramas de alto nível.

Quando um recurso técnico exigir credenciais, a documentação mostra apenas o conceito ou mecanismo de configuração necessário, nunca valores reais ou detalhes que facilitem exploração do ambiente.

## Repositório de produção

Código de produção, workflows completos, scripts internos, configurações reais e histórico operacional são mantidos fora deste repositório público.

Uma funcionalidade descrita como planejada, em preparação ou em validação privada não deve ser interpretada como disponível em produção.

## Relato de problema de segurança

Caso alguém encontre uma informação sensível publicada por engano, o ideal é não reproduzir o dado em uma issue pública. O problema deve ser comunicado diretamente ao responsável pelo projeto por um canal privado.

Quando uma credencial real for exposta, removê-la do Git não é suficiente. A credencial também deve ser revogada ou rotacionada no serviço correspondente.
