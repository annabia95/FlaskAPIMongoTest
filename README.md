# Perguntas
## 1) Você acha que este código está estruturado, legível e escalável?

Não, pelo fato de todas as rotas estarem localizadas no arquivo api.py. Isso 
fará com que o código seja de difícil manutenção, caso sejam criadas mais rotas futuramente, e 
cada vez mais difícil de identificar o tipo de método utilizado (GET, POST, DELETE, PUT). 

## 2) O que você mudaria nos arquivos e na estrutura de pastas para melhorá-lo nesse sentido?

Criaria uma pasta somente para as rotas (routes), uma com as extensões do projeto (extensions) com o intuito de armazenar as informações do banco de dados (database.py) e configurações (configurations.py). 

Outra pasta com as models do banco de dados que seria destinada a armazenar as tabelas criadas.

Estrutura final:
>>src
  >models
   >animals.py
  >routes
   >animals.routes.py
  >extensions
   >configurations.py
   >database.py
 >app.py
 >docker-compose.yml
 >Dockerfile


## 3) Quanto a arquitetura API e sua conteinerização, liste as brechas de segurança que você identificou neste código? Como você as resolveria?

Não foi feita nenhuma autenticação ou validação dos dados ao acessar/manipular as informações do banco de dados. Para isso, implementaria a autenticação por tokens (PyJWT) e middlewares de erro para cada requisição, protegendo as informações do usuário e as informações do banco. 

