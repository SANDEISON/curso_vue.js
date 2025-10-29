# Vue CLI

O Vue CLI (Command Line Interface) é uma poderosa ferramenta oficial do Vue.js que facilita a criação, configuração e desenvolvimento de aplicações Vue modernas.
Com ele, você pode criar projetos rapidamente, adicionar bibliotecas, configurar o ambiente de desenvolvimento e gerar builds otimizadas para produção.

### 1. Noções Básicas do Vue.js

Antes de usar o Vue CLI, entenda os fundamentos do Vue:

- O Vue é um framework progressivo para construção de interfaces.

- Trabalha com o conceito de componentes reativos.

- Usa data binding e diretivas (como v-if, v-for, v-bind, v-model).
 
     
      <div id="app">
         <h1>{{ mensagem }}</h1>
         <button @click="inverterMensagem">Inverter</button>
      </div>

      <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
      <script>
         const app = Vue.createApp({
         data() {
            return {
               mensagem: "Olá Vue!"
            };
         },
         methods: {
            inverterMensagem() {
               this.mensagem = this.mensagem.split('').reverse().join('');
            }
         }
         });
         app.mount('#app');
      </script>

### 2. Instalação do Vue CLI

Requisitos:

- Node.js (versão LTS recomendada)

   É um ambiente de execução que permite executar código JavaScript fora do navegador, no lado do servidor (backend).
- npm ou yarn

   Node Package Manager e é um gerenciador de pacotes para a linguagem JavaScript, utilizado em projetos com Node.js.


Para verificar a versão do Node
      
      node --version


Instalação do Vue:

      npm install -g @vue/cli

Verifique se foi instalado corretamente:

      vue --version


### 3. Criação de Projeto com Vue CLI

Crie um novo projeto:

      vue create meu-projeto

Durante a criação, o CLI perguntará:

Versão do Vue (Vue 2 ou Vue 3)

Ferramentas adicionais (Vue Router, Vuex, Linter, etc.)


Rodar o projeto:

      cd meu-projeto
      npm run serve


Abra o navegador em:

      http://localhost:8080


### 4. Interface Gráfica (Vue UI)

O Vue CLI oferece uma interface gráfica para gerenciar seus projetos.

No terminal digite : vue ui

Isso abrirá uma página em seu navegador onde é possível:

- Criar e configurar projetos

- Gerenciar dependências

- Executar e monitorar tarefas (serve, build, lint, etc.)

- Ver estatísticas de performance


### 5. Estrutura de Diretórios

Após criar o projeto, você verá algo como:

      meu-projeto/
     │
     ├── node_modules/
     ├── public/
     │   └── index.html
     ├── src/
     │   ├── assets/
     │   ├── components/
     │   ├── router/
     │   ├── store/
     │   ├── App.vue
     │   └── main.js
     ├── package.json
     └── babel.config.js

Principais diretórios:

src/ → código-fonte principal

components/ → componentes Vue reutilizáveis

router/ → configuração das rotas (caso use Vue Router)

store/ → gerenciamento de estado com Vuex

assets/ → imagens, CSS, fontes etc.


### 6. Serviço do CLI

O Vue CLI Service fornece comandos úteis pré-configurados.

| Comando         | Descrição                            |
| --------------- | ------------------------------------ |
| `npm run serve` | Inicia o servidor de desenvolvimento |
| `npm run build` | Gera versão otimizada para produção  |
| `npm run lint`  | Verifica e corrige problemas de lint |

Você pode personalizar o comportamento editando o arquivo vue.config.js.

### 7. Componentes

Os componentes são o coração do Vue.

Exemplo:
src/components/HelloWorld.vue
  
    <template>
      <div>
      <h2>{{ titulo }}</h2>
      <button @click="incrementar">Cliquei {{ contador }} vezes</button>
      </div>
    </template>

    <script>
      export default {
        data() {
          return {
            titulo: 'Componente Vue',
            contador: 0
          }
        },
        methods: {
          incrementar() {
            this.contador++
          }
        }
      }
    </script>

    <style scoped>
      h2 {
        color: #42b983;
      }
    </style>



Uso no App.vue:

    <template>
      <div id="app">
        <HelloWorld />
      </div>
    </template>
    
    <script>
        import HelloWorld from './components/HelloWorld.vue'
        
        export default {
          components: { HelloWorld }
        }
    </script>


### 8. Formulários e v-model

O v-model faz o data binding bidirecional entre o input e a variável.

    <template>
      <div>
        <input v-model="nome" placeholder="Digite seu nome" />
        <p>Olá, {{ nome }}</p>
      </div>
    </template>
    
    <script>
    export default {
      data() {
        return {
          nome: ''
        }
      }
    }
    </script>


###  9. Vue Router — Navegação entre Páginas

Instalação:

    npm install vue-router


Estrutura:

src/router/index.js

    import { createRouter, createWebHistory } from 'vue-router'
    import Home from '../views/Home.vue'
    import Sobre from '../views/Sobre.vue'
    
    const routes = [
      { path: '/', component: Home },
      { path: '/sobre', component: Sobre }
    ]
    
    export default createRouter({
      history: createWebHistory(),
      routes
    })


Uso no main.js:

    import { createApp } from 'vue'
    import App from './App.vue'
    import router from './router'
    
    createApp(App).use(router).mount('#app')


Exemplo de navegação:

    <template>
      <nav>
        <router-link to="/">Home</router-link> |
        <router-link to="/sobre">Sobre</router-link>
      </nav>
      <router-view />
    </template>



###  10. Gerenciamento de Estado Centralizado com Vuex

Quando vários componentes precisam compartilhar dados, usamos o Vuex.

Instalação:

    npm install vuex


Criação do Store:

src/store/index.js

    import { createStore } from 'vuex'
    
    export default createStore({
      state() {
        return {
          contador: 0
        }
      },
      mutations: {
        incrementar(state) {
          state.contador++
        }
      },
      actions: {
        incrementarAsync({ commit }) {
          setTimeout(() => commit('incrementar'), 1000)
        }
      }
    })

Uso no main.js:

    import store from './store'
    createApp(App).use(store).mount('#app')

Acesso nos componentes:

    <template>
      <div>
        <p>Contador: {{ contador }}</p>
        <button @click="incrementar">+</button>
      </div>
    </template>
    
    <script>
    import { mapState, mapMutations } from 'vuex'
    
    export default {
      computed: mapState(['contador']),
      methods: mapMutations(['incrementar'])
    }
    </script>


### Conclusão

Com o Vue CLI, você tem uma base sólida para desenvolver aplicações Vue.js escaláveis e modernas.

- Estrutura de projetos Vue

- Criação e uso de componentes

- Formulários reativos

- Rotas e navegação

- Estado centralizado com Vuex



| Aula	                                                 | Branch  |                                                 Clique no Link |
|:------------------------------------------------------|:-------:|---------------------------------------------------------------:|
| Aula 1 – Introdução ao Vue                              | aula_1  |              [Link](https://github.com/SANDEISON/curso_vue.js) |
| Aula 2 - Diretivas Vue.js              | aula_2  |  [Link](https://github.com/SANDEISON/curso_vue.js/tree/aula_2) |
| Aula 3 - Eventos Vue.js     | aula_3  |  [Link](https://github.com/SANDEISON/curso_vue.js/tree/aula_3) |
| Aula 4 - Vue CLI                          | aula_4  |  [Link](https://github.com/SANDEISON/curso_vue.js/tree/aula_4) |

















