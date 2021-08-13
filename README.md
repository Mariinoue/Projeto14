Sobre o Projeto On12-s14-ProjetoGuiado-BBD
O MinoueFilmes é um sistema de gerenciamento de catálogos de filmes dos diretores Akira Kurosawa, Ingmar Bergman, Martin Scorcesese e Sofia Coppola.

Onde receberemos cadastros de títulos(filmes) referenciando cada diretor.

"Relacionamento" no MongoDB? Como é isso?
- ref no model
- populate do find (eager loading)
Tecnologias que vamos usar:
Ferramenta	Descrição
javascript	Linguagem de programação
nodejs	Ambiente de execução do javascript
express	Framework NodeJS
mongoose	Dependência que interage com o MongoDB para a conexão da database, criação do model e das collections
nodemon	Dependência que observa as atualizações realizadas nos documentos para rodar o servidor automaticamente
npm Gerenciador de pacotes
MongoDb	Banco de dado não relacional orietado a documentos
Robo 3T	Interface gráfica para verificar se os dados foram persistidos
Postman	Interface gráfica para realizar os testes

📁 Arquitetura
 📁 filmes-db
   |
   |-  📁 src
   |    |
   |    |- 📁 data
   |         |- 📄 database.js
   |
   |    |- 📁 controllers
   |         |- 📄 tituloController.js
   |         |- 📄 diretorController.js
   |         |- 📄 diretorDelController.js
   |         |- 📄 diretorUpdateController.js
   |         |- 📄 diretorPostController.js
   |
   |    |- 📁 models
   |         |- 📄 titulo.js
   |         |- 📄 diretor.js
   |
   |    |- 📁 routes
   |         |- 📄 tituloRoutes.js 
   |         |- 📄 diretorRoutes.js 
   |
   |
   |
   |- 📄 .gitignore
   |- 📄 package
   |- 📄 server.js





Requisitos
 "/titulos/akira" Deverá retornar todos os títulos com o diretor Akira Kurosawa

 "/titulos/ingmar" Deverá retornar todos os títulos com o diretor Ingmar Bergman

 "/titulos/scorcesese" Deverá retornar todos os títulos com o diretor Martin Scorcesese

 "/titulos/sofia" Deverá retornar todos os títulos com o diretor Sofia Coppola

 "/diretor" Deverá retornar todos os estudios cadastrados

 "/titulos" Deverá retornar todos os títulos cadastrados, cada um fazendo referencia ao seu respectivo estudio

 "/diretor" Deverá criar um estudio

 "/titulos" Deverá criar um título

 "/titulos/[ID]" Deverá deletar titulo por id específico e retorna mensagem amigável

 "/diretor/[ID]" Deverá deletar estudio por id específico e retorna mensagem amigável

 "/titulos/[ID]" Deverá alterar informação específica dentro de um titulo por id específico e retorna o título alterado

 "/diretor/[ID]" Deverá alterar informação específica dentro de um estudio por id específico e retorna o título alterado

Regras de negócio
 Não deverá ser possível criar estudio com o mesmo nome
 Não deverá ser possível criar título com o mesmo nome
 Para criar um novo título, deverá vincular no momento da criação a um estudio já existente no sistema, utilizando o numero do id do estudio correspondente no corpo da requisição


Dados para Collection Diretor
id: autogerado e obrigatório
nome: texto e obrigatório
criadoEm: data gerada automaticamente e obrigatório
API deve retornar seguinte JSON:
[
    {
    "_id" : ObjectId("6115565d9b82f148cc825871"),
    "criadoEm" : ISODate("2021-08-12T17:04:39.767Z"),
    "nome" : "Akira Kurosawa",
    "__v" : 0
    },
    {
    "_id" : ObjectId("6115554f9b82f148cc825865"),
    "criadoEm" : ISODate("2021-08-12T17:04:39.767Z"),
    "nome" : "Martin Scorsese",
    "__v" : 0
    },
    {
    "_id" : ObjectId("6115560c9b82f148cc82586e"),
    "criadoEm" : ISODate("2021-08-12T17:04:39.767Z"),
    "nome" : "Igmar Bergman",
    "__v" : 0
    },
    {
        "_id" : ObjectId("611554fc9b82f148cc825862"),
        "criadoEm" : ISODate("2021-08-12T17:04:39.767Z"),
        "nome" : "Sofia Coppola",
        "__v" : 0
    }
]


Dados para Collection Titulos
id: autogerado e obrigatório
nome: texto e obrigatório
genero: texto e obrigatório
descricao: texto e obrigatório
criadoEm: data gerada automaticamente e obrigatório
estudio: referencia do estudio cadastrado previamente obrigatório
API deve retornar seguinte JSON:
[
  {
    "_id" : ObjectId("611584cbb8e52b0a8c36e7d8"),
    "criadoEm" : ISODate("2021-08-12T20:14:58.611Z"),
    "nome" : "Rashômon ",
    "genero" : "drama · suspense",
    "descricao" : "No Japão do século XI, um lenhador, um camponês e um sacerdote abrigam-se de uma forte tempestade nas ruínas do Portão de Rashomon. O sacerdote então começa a contar sobre um julgamento no qual foi testemunha, de um bandido que estuprara uma mulher e assassinara o marido dela. Nesse julgamento, os depoimentos são conflitantes, pondo em choque a verdade de cada um",
    "diretor" : ObjectId("6115565d9b82f148cc825871"),
    "__v" : 0
 }
]

Desenvolvida por: Mariana Inoue 
Contato: https://www.linkedin.com/in/mariana-inoue-89279450/

Orientadora Simara 
