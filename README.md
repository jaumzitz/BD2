# BD2

#UNIVALI - UNIVERSIDADE DO VALE DO ITAJAÍ
#CST SISTEMAS PARA INTERNET
#BANCO DE DADOS II
#JOAO VICTOR FIORINI DE SOUZA


Esse projeto tem o objetivo de facilitar a comunicação entre duas partes (clientes e empresas). Os clientes fazem o envio de documentos solicitados pela empresa, e os armazena de forma eletrônica. Imagine um cenário onde a empresa necessita que os clientes façam envio de qualquer documentação, por exemplo, documento de identificação de maneira fácil e que esse documento fique a disposição da empresa sempre que necessitar. Para atingir este objetivo, será utilizado a plataforma de chat TAKE BLIP, junto a linguagem JavaScript e o banco de dados MongoDB.

Atualmente a tecnologia permite que os clientes façam o envio de documentos de forma eletrônica de maneira extremamente simples, porém, devemos garantir que os documentos sejam armazeados de forma fácil e segura. Os clientes poderiam fazer o envio via e-mail por exemplo, ou entregar fisicamente o documento indo presencialmente a um núcleo ou enviando por correio. 

O envio por email pode fazer com que o fator humano afete negativamente o objetivo que é: manter o documento salvo em segurança. E o envio físico pode fazer com que o documento seja extraviado, danificado, ou destruído por inteiro.

Visando contornar esses problemas e facilitar ainda mais esse processo, utilizei um mensageiro instantâneo (WhatsApp) que é o principal serviço de comunicação usado pelos brasileiros, para que os clientes façam o envio de uma forma que já estão habituados. Sem a necessidade de interagir com uma plataforma desconhecida. Assim, até um cliente com pouca instrução ou debilitado (idosos ou pessoas com deficiências) conseguem realizar essa atividade.

A comunicação entre o cliente e a empresa deve ser simples e objetiva, o cliente deve conseguir enviar os dados necessários de forma rápida e a empresa deve conseguir atingir o maior número de clientes. 

-----

APIs de CRUD:


CREATE
POST: https://data.mongodb-api.com/app/data-avzcn/endpoint/data/v1/action/insertOne
Header: Content-Type: application/json
Header:api-key: OwOEmgyRfUJbtuBSmQ6hT9y7oq8a8F7H3Of0MTxqOJ701p7w3TIhooS0Z3ScZRtE
Body: {
    "dataSource": "Cluster0",
    "database": "BDII",
    "collection": "doc_cliente",
    "document": {
        "ticket": 1,
        "cpf": "123456",
        "nome":"Joao",
        "timestamp": "08/08/2022 18:00",
        "file": "https://blipmediastore.blob.core.windows.net/secure-medias/Media_8037fdf6-6fdd-4710-bd52-7c818fc6e618?sv=2019-07-07&st=2022-07-08T22%3A46%3A41Z&se=2022-07-08T23%3A16%3A41Z&sr=b&sp=r&sig=lXbdFt8d4v0O9zRyf8q9s16A%2BzrSWhNkof0CJGDTbXw%3D&secure=true"
    }
}

READ
POST: https://data.mongodb-api.com/app/data-avzcn/endpoint/data/v1/action/find
Header: Content-Type: application/json
Header:api-key: OwOEmgyRfUJbtuBSmQ6hT9y7oq8a8F7H3Of0MTxqOJ701p7w3TIhooS0Z3ScZRtE
Body: {
    "collection":"doc_cliente",
    "database":"BDII",
    "dataSource":"Cluster0",
    "filter":{"cpf":"123456"}
    
}

UPDATE
POST: https://data.mongodb-api.com/app/data-avzcn/endpoint/data/v1/action/updateOne
Header: Content-Type: application/json
Header:api-key: OwOEmgyRfUJbtuBSmQ6hT9y7oq8a8F7H3Of0MTxqOJ701p7w3TIhooS0Z3ScZRtE
Body: {
    "collection":"doc_cliente",
    "database":"BDII",
    "dataSource":"Cluster0",
    "filter":{"cpf":"123456"},
     "update": {
         "$set": { "nome": "Eduardo" }
     }
}

DELETE
POST: https://data.mongodb-api.com/app/data-avzcn/endpoint/data/v1/action/deleteOne
Header: Content-Type: application/json
Header:api-key: OwOEmgyRfUJbtuBSmQ6hT9y7oq8a8F7H3Of0MTxqOJ701p7w3TIhooS0Z3ScZRtE
Body:{
      "dataSource": "Cluster0",
      "database": "BDII",
      "collection": "doc_cliente",
      "filter":{"cpf":"123456"}
}

Link do vídeo de apresentação:
