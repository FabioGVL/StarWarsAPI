# Escopo do Projeto

Os testes abaixo visam garantir a funcionalidade correta e a integridade dos dados fornecidos pela API.
*Todos os testes foram realizados utilizando a ferramenta de automação CYPRESS*

## Escopo do Teste

### 1. Mapeamento de Features:
* **Enciclopédia SWAPI:** Consulta de dados sobre personagens, planetas, naves e filmes da franquia Star Wars.

### 2. Features Testadas:
* **Busca de Entidades:** Validação de retorno de dados específicos (como atributos de personagens e planetas).
* **Consistência de Resposta:** Verificação se os IDs consultados trazem as informações corretas e íntegras.

### 3. Massa de Dados para Teste:
* **IDs Específicos:** Lista de identificadores de personagens e planetas conhecidos para validar a precisão dos dados retornados.

### 4. Tipos de Testes Utilizados:
* **Testes de Funcionalidade:** Garantir que os endpoints da API estão operando e retornando os dados conforme o esperado.
* **Testes de Integração:** Garantir que a comunicação entre o script de teste e a SWAPI ocorra sem falhas.
* **Testes de Contrato:** Verificar se o formato do JSON recebido está em conformidade com o padrão da API pública.

## 3. Tecnologias e ambientes utilizados para execução do projeto:
- Cypress v10.11.0
- Node JS v20.15.0
- Google Chrome v126.0.6478.126
- Windows 11 v23H2
- Postman
- GIT


## 1. **Testes/Validações**

### Recuperação e validação de informações de personagens

*Dado que acesso o endpoint `/people/{id}/`*

*Quando inserir ao final do endpoint um ID do número 1 ao 83 e realizar a busca*

*Então a API deverá retornar os dados unitários corretos do personagem de ID buscado*





### Recuperação e validação de espécies

*Dado que acesso o endpoint `/species/{id}/`*

*Quando inserir ao final do endpoint o ID da espécie associada a um personagem especifico e realizar a busca*

*Então a API deverá retornar os dados unitários corretos da espécie buscada*





### Recuperação e validação de veículos

*Dado que acesso o endpoint `/vehicles/{id}/`*

*Quando inserir ao final do endpoint o ID do veículo associado a um personagem específico e realizar a busca*

*Então a API deverá retornar os dados unitários corretos do veículo buscado*






### Recuperação e validação de espaçonaves

*Dado que acesso o endpoint `/starships/{id}/`*

*Quando inserir ao final do endpoint o ID da espaçonave associado a um personagem específico e realizar a busca*

*Então a API deverá retornar os dados unitários corretos do veículo buscado*





### Validação do comportamento da API com ID inexistente - Limite de entrada

*Dado que acesso o endpoint `/people/{id}/`*

*Quando inserir um ID inexistente e realizar a busca*

*Então a API deverá retornar a mensagem de erro `"Not found"`*





### Validação do comportamento da API com página inexistente - Limite de entrada

*Dado que acesso o endpoint `/people/?page={id}`*

*Quando inserir um ID inexistente e realizar a busca*

*Então a API deverá retornar a mensagem de erro `"Not found"`*





### Validação da paginação e listagem de personagens por página

*Dado que acesso o endpoint `/people/?page={id}`*

*Quando efetuar a busca e a API retornar as informações da página*

*Então as informações de paginação/personagens retornadas deverão estar de acordo com o resultado esperado*





## 2. Bugs encontrados

### Personagem inexistente

*Dado que efetuo a busca do endpoint "/people/83"*

*E a API retorna o usuário existente `Tion Medon`*

*E verifico que no campo COUNT constam 82 personagens*

*Quando realizo a contagem geral dos personagens*

*Então verifico que os personagens estão mapeados do ID 1 ao 83, porém, o personagem de ID número 17 não existe*





## Passos para reproduzir/encontrar o erro

*1. Acesse o site https://swapi.dev*
   
*2. Insira o endpoint `/people/?page=2`*
   
*3. Realize a busca*
   
*4. Aguarde a API retornar as informações*
   
*5. Gire o scroll do mouse para baixo*
    
*6. Verifique que os IDs passam do 16 para o 18*



---

### Dados inconsistentes - Personagem R2-D2

*Dado que insiro os dados do personagem R2-D2 presentes na documentação para execução do teste de validação das informações dos personagens*

*Quando executo o teste o mesmo falha devido a inconsistência de dados entre a API e a Documentação*

*Então verifico que as informações contidas no campo FILMS estão divergentes*





## Passos para reproduzir o erro

### Efetuando o download e descompactando o projeto
- No GitHub, clique em "code".
- Clique em "Download Zip" para fazer o download do arquivo deste teste.
- No seu computador, localize o download efetuado.
- Descompacte o arquivo.

### Configurando o projeto no VSCode e executando o teste
- Abra o VSCode.
- Clique em `Arquivo/File`.
- Clique em `Abrir pasta/Open folder`.
- Escolha a pasta do arquivo descompactado (`StarWarsAPI-master`).
- Após o projeto ser aberto no VSCode, navegue até `Cypress > E2E`.
- Os testes estarão dentro das pastas `UI`.
- No terminal do Cypress digite `npx cypress open`. Caso necessário, instale o Cypress através do comando `npm install cypress`.
- Aguarde o Cypress abrir.
- Selecione a opção `E2E Testing`.
- Na próxima página selecione o navegador desejado.
- Na próxima página selecione o teste que deseja executar e a automação será executada.
- Também é possível executar o teste através do comando `npx cypress run`. O teste rodará dentro do próprio VSCode e serão gerados vídeos dos resultados dos testes. Os vídeos ficarão armazenados no destino `Cypress > Vídeos`.
- Clique em testeStarWarsApi.cy.js
- Aguarde a conclusão dos testes
- Após a conclusão, o Cypress informará que o teste falhou
- Acesse https://swapi.dev/api/people/3/ através do seu navegador ou insira a url no Postman
- Faça o comparativo entre informações contidas no test crash do Cypress e na URL acima


---


### Dados inconsistentes - Personagem Leia Organa

*Dado que insiro os dados do personagem Leia Organa presentes na documentação para execução do teste de validação das informações dos personagens*

*Quando executo o teste o mesmo falha devido a inconsistência de dados entre a API e a Documentação*

*Então verifico que as informações contidas no campo CREATED estão divergentes*





## Passos para reproduzir o erro

### Efetuando o download e descompactando o projeto
- No GitHub, clique em "code".
- Clique em "Download Zip" para fazer o download do arquivo deste teste.
- No seu computador, localize o download efetuado.
- Descompacte o arquivo.

### Configurando o projeto no VSCode e executando o teste
- Abra o VSCode.
- Clique em `Arquivo/File`.
- Clique em `Abrir pasta/Open folder`.
- Escolha a pasta do arquivo descompactado (`StarWarsAPI-master`).
- Após o projeto ser aberto no VSCode, navegue até `Cypress > E2E`.
- Os testes estarão dentro das pastas `UI`.
- No terminal do Cypress digite `npx cypress open`. Caso necessário, instale o Cypress através do comando `npm install cypress`.
- Aguarde o Cypress abrir.
- Selecione a opção `E2E Testing`.
- Na próxima página selecione o navegador desejado.
- Na próxima página selecione o teste que deseja executar e a automação será executada.
- Também é possível executar o teste através do comando `npx cypress run`. O teste rodará dentro do próprio VSCode e serão gerados vídeos dos resultados dos testes. Os vídeos ficarão armazenados no destino `Cypress > Vídeos`.
- Clique em testeStarWarsApi.cy.js
- Aguarde a conclusão dos testes
- Após a conclusão, o Cypress informará que o teste falhou
- Acesse https://swapi.dev/api/people/3/ através do seu navegador ou insira a url no Postman
- Faça o comparativo entre informações contidas no test crash do Cypress e na URL acima


---


### Dados inconsistentes - Personagem Beru Whitesun lars

*Dado que insiro os dados do personagem Beru Whitesun lars presentes na documentação para execução do teste de validação das informações dos personagens*

*Quando executo o teste o mesmo falha devido a inconsistência de dados entre a API e a Documentação*

*Então verifico que as informações contidas no campo FILMS estão divergentes*





## Passos para reproduzir o erro

### Efetuando o download e descompactando o projeto
- No GitHub, clique em "code".
- Clique em "Download Zip" para fazer o download do arquivo deste teste.
- No seu computador, localize o download efetuado.
- Descompacte o arquivo.

### Configurando o projeto no VSCode e executando o teste
- Abra o VSCode.
- Clique em `Arquivo/File`.
- Clique em `Abrir pasta/Open folder`.
- Escolha a pasta do arquivo descompactado (`StarWarsAPI-master`).
- Após o projeto ser aberto no VSCode, navegue até `Cypress > E2E`.
- Os testes estarão dentro das pastas `UI`.
- No terminal do Cypress digite `npx cypress open`. Caso necessário, instale o Cypress através do comando `npm install cypress`.
- Aguarde o Cypress abrir.
- Selecione a opção `E2E Testing`.
- Na próxima página selecione o navegador desejado.
- Na próxima página selecione o teste que deseja executar e a automação será executada.
- Também é possível executar o teste através do comando `npx cypress run`. O teste rodará dentro do próprio VSCode e serão gerados vídeos dos resultados dos testes. Os vídeos ficarão armazenados no destino `Cypress > Vídeos`.
- Clique em testeStarWarsApi.cy.js
- Aguarde a conclusão dos testes
- Após a conclusão, o Cypress informará que o teste falhou
- Acesse https://swapi.dev/api/people/3/ através do seu navegador ou insira a url no Postman
- Faça o comparativo entre informações contidas no test crash do Cypress e na URL acima


---


### Dados inconsistentes - Personagem R5-D4

*Dado que insiro os dados do personagem R5-D4 presentes na documentação para execução do teste de validação das informações dos personagens*

*Quando executo o teste o mesmo falha devido a inconsistência de dados entre a API e a Documentação*

*Então verifico que as informações contidas no campo FILMS estão divergentes*





## Passos para reproduzir o erro

### Efetuando o download e descompactando o projeto
- No GitHub, clique em "code".
- Clique em "Download Zip" para fazer o download do arquivo deste teste.
- No seu computador, localize o download efetuado.
- Descompacte o arquivo.

### Configurando o projeto no VSCode e executando o teste
- Abra o VSCode.
- Clique em `Arquivo/File`.
- Clique em `Abrir pasta/Open folder`.
- Escolha a pasta do arquivo descompactado (`StarWarsAPI-master`).
- Após o projeto ser aberto no VSCode, navegue até `Cypress > E2E`.
- Os testes estarão dentro das pastas `UI`.
- No terminal do Cypress digite `npx cypress open`. Caso necessário, instale o Cypress através do comando `npm install cypress`.
- Aguarde o Cypress abrir.
- Selecione a opção `E2E Testing`.
- Na próxima página selecione o navegador desejado.
- Na próxima página selecione o teste que deseja executar e a automação será executada.
- Também é possível executar o teste através do comando `npx cypress run`. O teste rodará dentro do próprio VSCode e serão gerados vídeos dos resultados dos testes. Os vídeos ficarão armazenados no destino `Cypress > Vídeos`.
- Clique em testeStarWarsApi.cy.js
- Aguarde a conclusão dos testes
- Após a conclusão, o Cypress informará que o teste falhou
- Acesse https://swapi.dev/api/people/3/ através do seu navegador ou insira a url no Postman
- Faça o comparativo entre informações contidas no test crash do Cypress e na URL acima
