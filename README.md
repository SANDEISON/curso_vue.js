# Introdução ao Vue

O Vue.js é um framework JavaScript progressivo para construção de interfaces de usuário.
Ele permite criar aplicações web reativas, ou seja, a interface se atualiza automaticamente sempre que os dados mudam.

Características principais:

- Fácil integração em projetos já existentes.

- Simples e intuitivo para iniciantes.

- Poderoso para aplicações complexas (com Vue Router, Vuex, Pinia, etc.).


### 1. Como podemos usaar o Vue.js
Você pode usar Vue.js de forma isolada em um projeto web adicionando-o via CDN para integrar a lógica Frontend, 
Ou usando o Vue CLI (Command Line Interface) para criar projetos Single Page Application (SPAs) com um ambiente de desenvolvimento completo, ou construindo Componentes de Web para reutilização em qualquer página HTML. 

As abordagens mais comuns são integrar via CDN para projetos simples ou usar o Vue CLI para SPAs e projetos mais complexos. 

#### 1.1 Usando Vue.js (CDN)

Esta é a forma mais simples e rápida de começar, ideal para projetos com HTML já pré-renderizado ou lógica não complexa. 

- Inclua a tag < script >: 

    Adicione um script apontando para o CDN do Vue.js em seu arquivo HTML.

- Crie um contêiner < div >: Adicione um elemento <div> com um ID, 
que será o local onde o Vue.js vai renderizar os componentes.

- Instancie o Vue: Crie uma instância do Vue, passando um objeto de configuração onde a propriedade el aponta para o < div > contêiner.

- Use data e {{}}: Armazene os dados da aplicação na propriedade data da instância do Vue. Os dados podem ser exibidos na tela usando a sintaxe de chaves duplas {{ }}.
        
    Código

        <!DOCTYPE html>
        <html>
        <head>
            <title>Meu App Vue</title>
            <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
        </head>
        <body>
            <div id="app">
                <h1>{{ message }}</h1>
            </div>
            <script>
                const { createApp } = Vue;
                createApp({
                    data() {
                        return {
                            message: 'Olá, Vue!'
                        }
                    }
                }).mount('#app');
            </script>
        </body>
        </html>

#### 1.2 Criando uma SPA com Vue CLI

Para aplicações mais complexas e interativas, o Vue CLI oferece uma estrutura de projeto completa. 

- Instale o Node.js e npm/yarn: 
    
    Você precisará do Node.js e seu gerenciador de pacotes para instalar as ferramentas do Vue. 

- Instale o Vue CLI: 

    Use o comando npm install -g @vue/cli para instalar o Vue CLI globalmente.

- Crie um novo projeto:

    Use o comando vue create nome-do-projeto para gerar um novo projeto com um template padrão ou um template de sua escolha. 

- Navegue até a pasta do projeto: 

    Use cd nome-do-projeto para entrar no diretório. 

- Instale as dependências: 

  Rode npm install para baixar todas as dependências necessárias. 

- Inicie o servidor de desenvolvimento: 

    Execute npm run dev para subir a aplicação e começar a desenvolver. 


### 2 .Ferramentas para o desenvolvimento

-    [Visual Studio Code](https://code.visualstudio.com/)
        
        Extensões

            - Vetur
            - Live Server


### 3. Minha primeira página

Agora aprenderemos como criar nossa primeira página web Vue em 5 etapas básicas:

3.1 Comece com um arquivo HTML básico.

3.2 Adicione uma < div > tag com id="app"para o Vue se conectar.

3.3 Diga ao navegador como lidar com o código Vue adicionando uma < script >tag com um link para o Vue.

3.4 Adicione uma < script > tag com a instância do Vue dentro.

3.5 Conecte a instância do Vue à < div id= " app " > tag.


#### 3.1 página HTML

    <!DOCTYPE html>
    <html lang="en">
    <head>
      <title>My first Vue page</title>
    </head>
    <body>
    
      <div id="app">
        {{ message }}
      </div>
    
      <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
    
      <script>
        const app = Vue.createApp({
          data() {
            return {
              message: "Hello World!"
            }
          }
        })
    
       app.mount('#app')
    
      </script>
    </body>
    </html>

#### 4 Interpolação de texto

A interpolação de texto ocorre quando o texto é retirado da instância do Vue para ser exibido na página da web.

O navegador recebe a página com este código dentro:

<div id="app"> {{ message }} </div>

Em seguida, o navegador encontra o texto dentro da propriedade 'message' da instância do Vue e traduz o código do Vue para isto:

< div id="app">Hello World! < /div >

    <!DOCTYPE html>
    <html lang="pt-BR">
    <head>
      <title>Minha primeira página Vue</title>
    </head>
    <body>
    
      <div id="app">
        {{ message }}<br/>
        {{ valorTotal }}<br/>    
        {{ logado }}<br/>
        {{ passatempos }}<br/>
        {{ passatempos[2] }}<br/>
        {{ perfil }}<br/>
        {{ perfil.nome }}<br/>
        {{ perfil.cursos }}<br/>
        {{ perfil.cursos[0] }}<br/>
         {{ perfil.cursos[0].nome }}<br/>
      </div>
    
      <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
    
      <script>
        const app = Vue.createApp({
          data() {
            return {
              message: "Hello World!",
              valorTotal: 1500,
              logado: false,
              passatempos:[
                'Correr',
                'Tocar instrumentos',
                'Praia',
                'Cinema'
              ],
              perfil:{
                nome: 'Sandeison Fernandes',
                idade: 39,
                cursos:[
    
                  {
                    nome: 'Residência em Robótica e Inteligência Artificial',
                    carga_horaria: '420 horas'
                  },
                  {
                    nome: 'Análise e Desenvolvimento de Sistemas',
                    carga_horaria: '2520 horas'
                  }
    
                ]
    
              }
    
            }
          }
        })
    
       app.mount('#app')
    
      </script>
    </body>
    </html>