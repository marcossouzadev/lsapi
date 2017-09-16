## lsapi
Um simples manipulador de local storage do HTML5.

## Tecnologias usadas
![HTML5](https://d14nx13ylsx7x8.cloudfront.net/platforms/images/000/000/004/thumb/HTML5_Logo_512.png)
![Javascript](https://frontendmasters.com/wp-content/themes/frontendmasters/assets/images/workshop/logo-js.png)

## Vantagens
Essa api facilita manipulação do locastorage provendo também validações que são necessarias em todas as iterações com localstorage.

## Como funciona
Há 5 funcões básicas que podem ser chamadas passando um objeto de configuração,
para lidar com um CRUD semelhante as APIs convencionais de banco de dados.

## Funções do CRUD
* **getObject(cfg)**
  - Retorna todos os objetos de determinada chave no local storage.
* **getObjectByFilter(cfg)**
  - Retorna um objeto de um array de objetos de determinada chave no local storage.
* **saveObject(cfg)**
  - Insere dados enviados no array de objetos do local storage.
* **updateObject(cfg)**
  - Atualiza determinado objeto no array de objetos do local storage.
* **delObject(cfg)**
  - Deleta determinado objeto no array de objetos do local storage.

## Parametros de configurações
##### Todos as chamadas de funções da api recebem um objeto de configurações sendo possível as seguintes chaves depedendo da função chamada.

- **key** refere-se a chave no local storage.
- **typeResponse** refere-se a que tipo de resposta deseja receber podendo ser um objeto ou string.
- **filter** refere-se a um array contendo 3 indices para manipular específico dado do localstorage.
- **data** refere-se a dados enviados para serem persistidos no local storage.
- **create** refere-se a instrução de criar a chave caso ela não exista.

## Chamadas de funções

#### getObject
  ```javascript
  var cfg = {key:'*chave do local storage*', typeResponse:'*object ou string*'};

//Exemplo da chamada
  getObject(cfg)
```

#### getObjectByFilter

  Essa função recebe também uma chave chamada filter contendo 3 indices:

  **Primeiro indice** é o valor único do objeto á ser retornado, por exemplo *ID*.

  **Segundo indice** pode conter valores *ID* ou *PROP*, onde *ID* quer dizer para retornar o objeto,e *PROP* diz para retornar uma propriedade do objeto.

  **Terceiro indice** refere-se ao nome da *propriedade* que deseja retornar.caso segundo indice seja *ID* deve-se setar esse valor para *NULL*.

  ```javascript
  var cfg = {key:'*chave do local storage*', typeResponse:'*object*', filter:['*id*','*id ou prop*','*null ou nome da prop*']}

//Exemplo da chamada
  getObjectByFilter(cfg)
```

#### saveObject

  Essa função recebe também uma chave chamada *DATA* que deve conter os dados a serem persistidos no localstorage e também outra chave *create* que deve ser setada para true caso queira criar uma nova chave no localstorage se a mesma não existir.

```javascript
  var cfg = {key:'*chave do local storage*', typeResponse:'*object ou string*', data:{'*objeto*'}, create:'true'}

//Exemplo da chamada
  saveObject(cfg)
```

#### updateObject

  Essa função também recebe chave *FILTER* e *DATA* no entanto no *FILTER* apenas o primeiro indice é requerido com o *ID* do objeto do localstorage a ser alterado, e o *DATA* deve conter o objeto a ser persistido.

  **IMPORTANTE** Deve ser enviado o objeto completo pois ele deleta o objeto com esse *ID* e recria novamente persistido o valor contido em *DATA*.

```javascript
  var cfg = {key:'*chave do local storage*', typeResponse:'*object*', filter:['*ID*', '*null*', '*null*'], data:{*objeto*}}

//Exemplo da chamada
  updateObject(cfg)
```

#### delObject

  Essa função recebe *FILTER* com apenas *primeiro indice* contendo o *ID* do objeto a ser excluído.

```javascript
  var cfg = {key:'*chave do local storage*', typeResponse:'*object*', filter:['*ID*', '*null*', '*null*']}

//Exemplo da chamada**
  delObject(cfg)
```

**Erros e retornos das funções**
 - Todas as funções retornam ou o recurso solicitado ou um objeto contendo uma chave chamada *err* contendo o erro.



### Todo feedback sobre errors de português ou programação são bem vindos
