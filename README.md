## lsapi
Um simples manipulador de local storage do HTML5.

## Vantagens
Essa api facilita manipulação do locastorage provendo também validações que são necessarias em todas as iterações com localstorage.

## Como funciona
Há 5 funcões básicas que podem ser chamadas passando um objeto de configurações,
para lidar com um CRUD semelhante as APIs convencionais de banco de dados.

## Funções do CRUD
* **getObject(cfg)**
  - Retorna todos os objetos de determinada chave no local storage
* **getObjectByFilter(cfg)**
  - Retorna um objeto de um array de objetos de determinada chave no local storage
* **saveObject(cfg)**
  - Insere dados enviados no array de objetos do local storage
* **updateObject(cfg)**
  - Atualiza determinado objeto no array de objetos do local storage
* **delObject(cfg)**
  - Deleta determinado objeto no array de objetos do local storage

## Parametros de configurações
##### Todos as chamadas de funções da api recebem um objeto de configurações sendo possível as seguintes chaves dependo da função chamada.

- **key** refere-se a chave no local storage
- **typeResponse** refere-se a que tipo de resposta deseja receber podendo ser um objeto ou string
- **filter** refere-se a um array contendo 3 indices paramanipular especifico dado do localstorage
- **data** refere-se a dados enviados para serem persistidos no local storage
- **create** refere-se a instrução de criar a chave caso ela não exista

## Chamadas de funções

#### getObeject
  ```javascript
  var cfg = {key:'*chave do local storage*', typeResponse:'*object ou string*'}

**Exemplo da chamada**
  getObeject(cfg)
```

#### getObjectByFilter

  Essa função recebe tambem uma chave chamada filter contendo 3 indices
  *primeiro indice* é o valor único do objeto á ser retornado, por exemplo *ID*

  *segundo indice* pode conter dois valores *id* ou *prop*, onde ID quer dizer para retornar o objeto,e prop diz para retornar uma propriedade do objeto.

  *terceiro indece* refere-se ao nome da propriedade que deseja retornar.caso segundo indice seja *id* deve-se setar esse valor para *null*.

  ```javascript
  var cfg = {key:'*chave do local storage*', typeResponse:'*object ou string*', filter:['*id*','*id ou prop*','*null ou nome da prop*']}

**Exemplo da chamada**
  getObejectByFilter(cfg)
```

#### saveObeject

  Essa função recebe tambem uma chave chamada *data* que deve conter os dados a serem persistidos no localstorage e tambem outra chave *create* que deve ser setada para true caso queira criar uma nova chave no localstorage se a mesma não existir.

```javascript
  var cfg = {key:'*chave do local storage*', typeResponse:'*object ou string*', data:{'*objeto*'}, create:'true'}

**Exemplo da chamada**
  saveObeject(cfg)
```

#### updateObeject

  Essa função tambem recebe chave *filter* e *data* no entanto no *filter* apenas o primeiro indice é requerido com o *ID* do objeto do localstorage a ser alterado, e o data deve conter o objeto a ser persistido.

  **IMPORTANTE** Deve ser enviado o objeto completo pois ele deleta o objeto com esse *ID* e recria novamente persistido o valor contido em *data*.

```javascript
  var cfg = {key:'*chave do local storage*', typeResponse:'*object ou string*', filter:['*ID*', '*null*', '*null*'], data:{*objeto*}}

**Exemplo da chamada**
  updateObeject(cfg)
```

#### delObeject

  Essa função recebe *filter* com apenas *primeiro indice* contendo o *ID* do objeto a ser excluído.

```javascript
  var cfg = {key:'*chave do local storage*', typeResponse:'*object ou string*', filter:['*ID*', '*null*', '*null*']}

**Exemplo da chamada**
  delObeject(cfg)
```

**Erros e retornos das funções**
 - Todoas as funções retornam ou o recurso solicitado ou um objeto contendo uma chave chamada *err*.
