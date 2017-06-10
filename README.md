## lsapi
Um simples manipulador de local storage do HTML5.

## Vantagens
Essa api facilita manipilação do locastorage provendo também validações que são necessarias em todas as iterações com localstorage.

## Como funciona
Há 5 funcões básicas que podem ser chamadas passando um objeto de configurações,
para lidar com um CRUD semelhante as APIs convencionais de banco de dados.

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
##### Todos as chamadas de funções da api recebem um objeto de configurações sendo possível as seguintes chaves dependo da função chamada.

- *key* refere-se a chave no local storage
- *typeResponse* refere-se a que tipo de resposta deseja receber podendo ser um objeto ou string
- *filter* refere-se a um array contendo 3 indices paramanipular especifico dado do localstorage
- *data* refere-se a dados enviados para serem persistidos no local storage
- *create* refere-se a instrução de criar a chave caso ela não exista
