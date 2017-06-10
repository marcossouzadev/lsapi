## lsapi
Um simples gerenciador de local storage do HTML5.

## Como funciona
Há 5 funcões básicas que podem ser chamadas passando um objeto de configurações,
para lidar com um CRUD semelhante as api convencionais de banco de dados.

## Funções do CRUD
* getObeject(cfg)
  - Retorna todos os objetos de determinada chave no local storage
* getOjectByFilter(cfg)
  - Retorna um objeto de um array de objetos de determinada chave no local storage
* saveObject(cfg)
  - Insere dados enviados no array de objetos do local storage
* updateObject(cfg)
  - Atualiza determinado objeto no array de objetos do local storage
* delObject(cfg)
  - Deleta determinado objeto no array de objetos do local storage

## Parametros de configurações
### Todos as chamadas de funções da api recebem um objeto de configurações sendo possível as seguintes chaves dependo da função chamada.

- *key*
- *typeResponse*
- *filter*
- *data*
- *create*
 
