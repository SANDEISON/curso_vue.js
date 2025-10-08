# Eventos Vue.js

O tratamento de eventos no Vue é feito com a diretiva v-on , para que possamos fazer algo acontecer quando, por exemplo, um botão é clicado.

O tratamento de eventos ocorre quando elementos HTML são configurados para executar um determinado código quando um determinado evento acontece.

Os eventos no Vue são fáceis de usar e tornarão nossa página realmente responsiva.

Os métodos do Vue são códigos que podem ser configurados para serem executados quando um evento acontece.

Com os modificadores v-on , você pode descrever com mais detalhes como reagir a um evento.

Exemplo : 

Vamos começar com um exemplo para mostrar como podemos clicar em um botão para contar alces em uma floresta.

Precisamos:

1. Um botão
2. v-on na tag < button > para ouvir o evento 'click'
3. Código para aumentar o número de alces
4. Uma propriedade (variável) na instância Vue para conter o número de alces
5. Chaves duplas {{ }} para mostrar o aumento do número de alces

        <!DOCTYPE html>
        <html>
        <head>
          <title>Count Moose</title>
        
        </head>
        <body>
        
        <h1>Exemplo de contar</h1>  
        
        <div id="app">
          <p>{{ "Total: " + count }}</p>
          <button v-on:click="count++">Adicionando Item</button>
        </div>
        
        <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
        <script>
          const app = Vue.createApp({
            data() {
              return {
                count: 0
              }
            }
          })
         app.mount('#app')
        </script>
        
        </body>
        </html>



### 1. Métodos Vue

Os métodos do Vue são funções que pertencem à instância do Vue na propriedade 'methods'.

Os métodos Vue são ótimos para usar com manipulação de eventos ( v-on) para fazer coisas mais complexas.

Os métodos do Vue também podem ser usados ​​para fazer outras coisas além do tratamento de eventos.

Já usamos uma propriedade, a propriedade 'data', onde podemos armazenar valores.

Existe outra propriedade do Vue chamada "métodos", onde podemos armazenar funções que pertencem à instância do Vue. 

Um método pode ser armazenado na instância do Vue assim:

    const app = Vue.createApp({
      data() {
        return {
          text: ''
        }
      },
      methods: {
        writeText() {
          this.text = 'Hello World!'
        }
      }
    })

Exemplo
    
    <!DOCTYPE html>
    <html>
    <head>
      <title>Click para executar o metodo </title>
      <style>
        #app {
          border: black dashed 1px;
          width: 200px;
          padding: 0 20px 20px 20px;
        }
        #app > div {
          width: 140px;
          height: 60px;
          background-color: lightgreen;
          padding: 20px;
          font-weight: bold;
          font-family: 'Courier New', Courier, monospace;
        }
      </style>
    </head>
    <body>
    
    <h1>Exemplo: Click para executar o metodo</h1>
    
    <div id="app">
      <p>Clique na caixa abaixo:</p>
      <div v-on:click="changeText">
        {{ text }}
      </div>
    </div>
    
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
    <script>
      const app = Vue.createApp({
        data() {
          return {
            text: ''
          }
        },
        methods: {
          changeText() {
            this.text = 'Hello World!'
          }
        }
      })
     app.mount('#app')
    </script>
    
    </body>
    </html>


