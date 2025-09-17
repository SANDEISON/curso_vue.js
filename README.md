# Introdução ao Vue

O Vue.js é um framework JavaScript progressivo para construção de interfaces de usuário.
Ele permite criar aplicações web reativas, ou seja, a interface se atualiza automaticamente sempre que os dados mudam.

Características principais:

- Fácil integração em projetos já existentes.

- Simples e intuitivo para iniciantes.

- Poderoso para aplicações complexas (com Vue Router, Vuex, Pinia, etc.).

### 1. Minha primeira página

Agora aprenderemos como criar nossa primeira página web Vue em 5 etapas básicas:

1.1 Comece com um arquivo HTML básico.

1.2 Adicione uma < div > tag com id="app"para o Vue se conectar.

1.3 Diga ao navegador como lidar com o código Vue adicionando uma < script >tag com um link para o Vue.

1.4 Adicione uma < script > tag com a instância do Vue dentro.

1.5 Conecte a instância do Vue à < div id= " app " > tag.


#### 1.1 página HTML

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

#### 2 Interpolação de texto

A interpolação de texto ocorre quando o texto é retirado da instância do Vue para ser exibido na página da web.

O navegador recebe a página com este código dentro:

<div id="app"> {{ message }} </div>

Em seguida, o navegador encontra o texto dentro da propriedade 'message' da instância do Vue e traduz o código do Vue para isto:

< div id="app">Hello World! < /div >