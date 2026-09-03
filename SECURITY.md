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

## Princípio de publicação

Documentação pública deve usar exemplos genéricos, nomes fictícios, identificadores de teste e diagramas de alto nível.

Quando um recurso técnico exigir credenciais, a documentação deve mostrar apenas o nome da variável ou do mecanismo de configuração, nunca o valor real.

## Repositório de produção

Código de produção, workflows completos, scripts internos, configurações reais e histórico operacional são mantidos fora deste repositório público.

## Relato de problema de segurança

Caso alguém encontre uma informação sensível publicada por engano, o ideal é não reproduzir o dado em uma issue pública. O problema deve ser comunicado diretamente ao responsável pelo projeto por um canal privado.

Quando uma credencial real for exposta, removê-la do Git não é suficiente. A credencial também deve ser revogada ou rotacionada no serviço correspondente.
