# json-server-homepets

Esse é o repositório com a API utilizada no projeto Home Pets, capstone do Q2 do grupo 4 do Samuel, composto pelos devs Victor Varela, Christian Ferreira, Gyl Monteiro e Julio Marodin.

## Endpoints

Assim como a documentação do JSON-Server-Auth traz (https://www.npmjs.com/package/json-server-auth), existem 3 endpoints que podem ser utilizados para cadastro e 2 endpoints que podem ser usados para login.

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

Endpoint para cadastro de usuários, empresas e ONGs.
Qualquer um desses 3 endpoints irá cadastrar o usuário na lista de "Users", sendo que os campos obrigatórios são os de email e password, tanto para pessoa física quanto para ONGs e empresas, os outros ítens devem ser preenchidos quando o usuário for editar o seu cadastro.
No corpo da requiseção passar o email, password e name.

### Update Cadastro

PATCH /users/${idUsuario}

Os ítens não especificados se são para pessoas físicas, empresas ou ONGs são para ambos.
No corpo da requisição passar foundationDate (ONGs e empresas), birthDate (pessoa física), city, cnpj (empresas), donor (boolean), type (ONG, empresa ou pessoa física), weNeed (ONGs), description (ONGs e empresas), residence (pessoa física), financialRent (renda mensal para pessoa física), hasAPet (pessoa física), animalSpecies, numberOfCats (empresas e ONGs), numberofDogs (empresas e ONGs).

### Login

POST /login <br/>
POST /signin

Qualquer um desses 2 endpoints pode ser usado para realizar login com um dos usuários cadastrados na lista de "Users"

### Products

GET /products

Qualquer um pode fazer o get dos produtos, não é necessário token de acesso. O objeto de retorno contém o id, title, description, img, price, category, species e userId.

### Cart

POST /cart <br/>
GET /cart

Para fazer o post (adiconar produto ao carrinho) o usuário precisa estar logado e passar o token de accesso pelo headers/bearer. No corpo da requisição passar o id, title, description, img, price, category, species e userId.
Para fazer o get (ver os produtos no carrinho) é necessário passar o token de acesso no corpo da requisição, pelo headers/bearer.

### Animals

POST /petDonation <br />
GET /petDonation

Para fazer o post (cadastrar um animal para a adoção) o usuário precisa estar logado e passar o token de acesso pelo headers/bearer. No corpo da requisição passar o foundLocation (onde achou o animal), city (cidade), state (estado), animalSize (porte do animal), breed (raça), fur (pelagem), age (idade), infirmity (doença, dificuldade), personBehaviour (comportamento com outras pessoas), personality (personalidade), sex (sexo), vaccinated (vacinado boolean), castrated (castrado boolean), description (descrição), img, id, userId.
Para fazer o get não é necessário o token, já que todos tem acesso..
