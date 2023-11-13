# TestedeUI

Repositório referente ao exercício de Teste de UI com cypress da disciplina de qualidade de software.

Este projeto foi desenvolvido por Ana Luiza Taveira e Pedro Hugo Coura com objetivo de testar algumas funcionalidades do site Amazon. Para o desenvolvimento dessa aplicação, foram utilizadas a IDE VSCode e a uma ferramenta de testes Cypress. 


## Instalação dos ambientes de desenvolvimento:
1. IDE VSCode (code):
https://code.visualstudio.com/

2. JDK (java):
https://www.oracle.com/java/technologies/javase-downloads.html

3. Maven (mvn)
https://maven.apache.org


## Instalação - Cypress (Teste de UI):

1. Faça a instalação do cypress via linha de comando. Abra o terminal e digite

```
npm install cypress

```

2. Download cypress direto do site: https://www.cypress.io/

Link para download direto: https://download.cypress.io/desktop

Basta baixar, extrair, executar o Cypress.exe e apontar para o diretório do projeto desejado na interface do cypress.
Utilize a IDE para editar o código.



### Comandos úteis cypress

Criar o diretório inicial e indicar para o node que o diretório é um projeto

npm init

Baixar as dependencias do projeto 

npm install

Abrir cypress pela linha de comando:
./node_modules/.bin/cypress open


## Gerando um report 

1. Adicionando as dependências necessárias para gerar o reporte de testes:
npm i --save-dev cypress-mochawesome-reporter
	
2. Modificar o arquivo cypress.config.js:
const { defineConfig } = require('cypress');

module.exports = defineConfig({
  reporter: 'cypress-mochawesome-reporter',
  e2e: {
    setupNodeEvents(on, config) {
      require('cypress-mochawesome-reporter/plugin')(on);
    },
  },
});

3. Adicionar em cypress/support/e2e.js:
import 'cypress-mochawesome-reporter/register';

4. Rodar specs pela linha de comando:
./node_modules/.bin/cypress run --spec 'cypress/e2e/**/'

