# Descrição

A api está funcionando no endereço http://45.179.89.6:6610/.
As rotas existentes são as:

## Registro de usuários
- #### Metodo Post

- /auth/register


__Parâmetros:__

```
 {
    "nome": "example",
    "email": "email@example.com",
    "senha": "12345",
    "funcao" : "admin"
 }
 
 ```
 OBS: a função pode ser qualquer, desde que tenha duas, uma que tenha total permissão e outra apenas de requisitar equipamentos.
 
  ### Return 
 
 ``` 
   {
      "user": {
          "nome": "example",
          "email": "email@example.com",
          "funcao": "admin",
          "_id": "mongodbID",
          "createdAt": "timeStamp",
          "__v": 0
      },
      "token": "token"
  }
 ```
 
 ## Login
 - #### Metodo Post
 
 - /auth/authenticate

__Parâmetros:__

```
 {
    "email": "email@example.com",
    "senha": "12345"
 }
 
 ```

### Return 
 
 ``` 
 {
    "user": {
          "nome": "example",
          "email": "email@example.com",
          "funcao": "admin",
          "_id": "mongodbID",
          "createdAt": "timeStamp",
        "__v": 0
    },
    "token": "token"
}
 ```
 
 ## Cadastro de Equipamentos
 - #### Metodo Post

 -  /cadastrar-equipamento

__Parâmetros:__

```
{
    "nome": "nomeEquipamento",
    "responsavel": "example",
    "categoria": "categoriaEquipamento",
    "quantidade": "2",
    "referencia": "refEquipamento"
},
  {
    headers: `${token}`
  }
 
 ```
 
 ### Return 
 
 ``` 
{
    "equipamento": {
        "nome": "nomeEquip",
        "responsavel": "example",
        "categoria": "categoriaEquipamento",
        "quantidade": "1",
        "referencia": "refEquipamento",
        "_id": "mongodbID",
        "createdAt": "timeStamp",
        "__v": 0
    }
}

 ```


## Cadastro de requisição
- #### Metodo Post
- /requisicao

__Parâmetros:__

```
{
    "nomeRequisitante": "example",
    "refEquipamento": "refEquipamento",
    "quantidadeEquipamento": "2"  
},
  {
    headers: `${token}`
  }
 
 ```
 
  ### Return 
 
 ``` 
 
 {
    "requisicao": {
        "nomeRequisitante": "example",
        "refEquipamento": "refEquipamento",
        "quantidadeEquipamento": "2",
        "_id": "mongodbID",
        "dataReq": "timestamp",
        "__v": 0
    }
}

 ```



## Requisoes

- #### Metodo Get
- /requisicoes

__Parâmetros:__

```
{
    "nomeRequisitante": "example",
    "refEquipamento": "refEquipamento",
    "quantidadeEquipamento": "2"  
},
  {
    headers: `${token}`
  }
 
 ```
 
### Return 
 
 ``` 
 
[
    {
        "_id": "613616673bdcd75122365723",
        "nomeRequisitante": "example",
        "refEquipamento": "refEquipamento",
        "quantidadeEquipamento": "2",
        "dataReq": "timeStamp",
        "__v": 0
    }
]
 ```




## Equipamentos

- #### Metodo Get
- /equipamentos

__Parâmetros:__

```
{
    "nomeRequisitante": "example",
    "refEquipamento": "refEquipamento",
    "quantidadeEquipamento": "2"  
},
  {
    headers: `${token}`
  }
 
 ```
 
   ### Return 
 
 ``` 
 
[
    {
        "_id": "61340b0f1d13a3d5032cd988",
        "nome": "nomeEquip",
        "responsavel": "example",
        "categoria": "categoriaEquipamento",
        "quantidade": "1",
        "referencia": "refEquip",
        "createdAt": "timeStamp",
        "__v": 0
    },
    {
        "_id": "613615a63bdcd75122365720",
        "nome": "nomeEquip",
        "responsavel": "example",
        "categoria": "categoriaEquipamento",
        "quantidade": "1",
        "referencia": "refEquip1",
        "createdAt": "timeStamp",
        "__v": 0
    }
]
 ```



 
