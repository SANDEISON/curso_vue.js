# Diretivas Vue.js

### 1. v-bind
   
Conecta um atributo em uma tag HTML a uma variável de dados dentro da instância do Vue.

Exemplo

    <!DOCTYPE html>
    <html>
    <head>
      <title>'v-bind' Image Source Example</title>
      <style>
        #app {
          border: dashed black 1px;
          width: 250px;
          padding: 0 10px 10px 10px;
        }
    
        img {
          width: 100%;
        }
      </style>
    </head>
    <body>
    
    <h1>'v-bind' Image Source Example</h1>
    
    <div id="app">
      <p>The browser finds the 'src' attribute value from the Vue instance with the use of 'v-bind'.</p>
      <img v-bind:src="url">
    </div>
    
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
    <script>
      const app = Vue.createApp({
       data() {
        return {
          url: "img_beach3.jpg"
        }
       }
      })
      app.mount('#app')
    </script>
    
    </body>
    </html>


### 2. v-if

Cria tags HTML dependendo de uma condição. As diretivas v-else-ife v-elsesão usadas em conjunto com a diretiva v-if.

Exemplo

    <!DOCTYPE html>
    <html>
    <head>
      <title>Typewriters</title>
      <style>
        #app {
          border: dashed black 1px;
          width: 130px;
          padding-left: 20px;
          font-weight: bold;
          background-color: lightgreen;
        }
      </style>
    </head>
    <body>
    
    <h1>Example with 'v-if' and 'v-else'</h1>
    
    <p>Try changing the 'typewritersInStock' value in the Vue instance from 'true' to 'false' and run the code again.</p>
    
    <div id="app">
      <p v-if="typewritersInStock">
        in stock
      </p>
      <p v-else>
        not in stock
      </p>
    </div>
    
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
    <script>
      const app = Vue.createApp({
       data() {
        return {
          typewritersInStock: true
        }
       }
      })
      app.mount('#app')
    </script>
    
    </body>
    </html>


### 3. v-show

Especifica se um elemento HTML deve ser visível ou não, dependendo de uma condição.

Exemplo

    <div id="app">
      <div v-show="showDiv">This div tag can be hidden</div>
    </div>
    
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
    <script>
      const app = Vue.createApp({
        data() {
          return {
            showDiv: true
          }
        }
      })
      app.mount('#app')
    </script>

### 4. v-for

Cria uma lista de tags com base em uma matriz na instância do Vue usando um loop for.

Exemplo

    <!DOCTYPE html>
    <html>
    <head>
      <title>My first Vue page</title>
      <style>
        #app > div {
          display: inline-block;
          border: dashed black 1px;
          padding: 10px;
          background-color: lightgreen;
        }
        #app p {
          font-weight: bold;
          margin: 5px 0;
        }
      </style>
    </head>
    <body>
    
    <h1>Example: Get the array element index with 'v-for'</h1>
    <p>The 'v-for' directive is used to get the index of objects inside the 'manyFoods' array, together with the name and url of each food object.</p>
    
    <div id="app">
      <div>
        <p v-for="(x, index) in manyFoods">
          {{ index }}: "{{ x.name }}", url: "{{ x.url }}" <br>
        </p>
      </div>
    </div>
    
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
    <script>
      const app = Vue.createApp({
       data() {
        return {
          manyFoods: [
            {name: 'Burrito', url: 'img_burrito.svg'},
            {name: 'Salad', url: 'img_salad.svg'},
            {name: 'Cake', url: 'img_cake.svg'},
            {name: 'Soup', url: 'img_soup.svg'},
            {name: 'Fish', url: 'img_fish.svg'},
            {name: 'Pizza', url: 'img_pizza.svg'},
            {name: 'Rice', url: 'img_rice.svg'}
          ]
        }
       }
      })
      app.mount('#app')
    </script>
    
    </body>
    </html>

### 5. v-on

Conecta um evento em uma tag HTML a uma expressão JavaScript ou a um método de instância do Vue. Também podemos definir mais especificamente como nossa página deve reagir a um determinado evento usando modificadores de evento .

Exemplo

    <div id="app">
      <div id="lightDiv">
        <div v-show="lightOn"></div>
        <img src="img_lightBulb.svg">
      </div>
      <button v-on:click="lightOn = !lightOn">Switch light</button>
    </div>
    
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
    <script>
      const app = Vue.createApp({
        data() {
          return {
            lightOn: false
          }
        }
      })
      app.mount('#app')
    </script>


| Aula	                                                 | Branch  |                                                 Clique no Link |
|:------------------------------------------------------|:-------:|---------------------------------------------------------------:|
| Aula 1 – Introdução ao Vue                              | aula_1  |              [Link](https://github.com/SANDEISON/curso_vue.js) |
| Aula 2 - Diretivas Vue.js              | aula_2  |  [Link](https://github.com/SANDEISON/curso_vue.js/tree/aula_2) |
| Aula 3 - Eventos Vue.js     | aula_3  |  [Link](https://github.com/SANDEISON/curso_vue.js/tree/aula_3) |
| Aula 4 - Vue CLI                          | aula_4  |  [Link](https://github.com/SANDEISON/curso_vue.js/tree/aula_4) |


