<template>
  <div class="container col-10">
    <div
      class="row justify-content-center align-items-between"
      style="height: calc(100vh - 128px)"
    >
      <div
        id="brand"
        class="teste col-10 col-md-4 d-flex justify-content-center align-items-center"
      >
        <img class="logo" alt="Wake Up!" src="./assets/Logo.svg" />
      </div>
      <div
        id="message-display"
        class="col-10 col-md-12 d-flex justify-content-center align-items-center"
      >
        <p class="message">{{ message }}</p>
      </div>
      <div
        id="action-button"
        class="col-auto d-flex justify-content-center align-items-center"
      >
        <button type="button" class="btn btn-primary" @click="getMessage">
          <span class="btn-label"> Nova frase </span>
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: "none",
      messages: [
        {
          message: "“Acorda e tira a bunda da cama!”",
          author: "ROCK, The",
        },
        {
          message: "“O sucesso nasce do querer, da determinação e … mínimo fará coisas admiráveis”",
          author: "José de Alencar"
        },
        {
          message: "“Se você quer ser bem-sucedido precisa de dedi…limite e dar o melhor de si mesmo”",
          author: "Ayrton Senna"
        },
        {
          message: "“Não crie limites para si mesmo. Você deve ir …cê mais quer pode ser conquistado”",
          author: "Mary Kay Ash"
        },
        {
          message: "“Nenhum obstáculo será grande se a sua vontade de vencer for maior”",
          author: "Autor desconhecido"
        },
        {
          message: "“Dificuldades preparam pessoas comuns para destinos extraordinários”",
          author: "C.S Lewis"
        },
        {
          message: "“Nenhum homem será um grande líder se quiser f… todo o crédito por fazer isso”",
          author: "Andrew Carnegie"
        },
        {
          message: "“Bom mesmo é ir à luta com determinação, abraç…curta, para ser insignificante”",
          author: "Charlie Chaplin"
        },
        {
          message: "“Pessoas vencedoras não são aquelas que não fa…o aquelas que não desistem”",
          author: "Autor desconhecido"
        },
        {
          message: "“Só existem dois dias do ano em que você não p…a: um se chama ontem e outro amanhã”",
          author: "Dalai Lama"
        },
        {
          message: "“A vida é um constante recomeço. Não se dê po…ã enfeitarão a sua estrada”",
          author: "Autor desconhecido"
        },
        {
          message: "“Ouse ir além, ouse fazer diferente e o poder lhe será dado!”",
          author: "José Roberto Marques"
        },
        {
          message: "“Ouse, arrisque, não desista jamais e saiba v…sou de restos para ser feliz”",
          author: "Clarice Lispector"
        },
        {
          message: "“Para ser um campeão você tem que acreditar e…esmo quando ninguém mais acredita”",
          author: "Muhammad Ali"
        },
        {
          message: "“No fim tudo dá certo, e se não deu certo é porque ainda não chegou ao fim”",
          author: "Fernando Sabino"
        },
        {
          message: "“Você nunca sabe que resultados virão da sua … nada, não existirão resultados”",
          author: "Mahatma Gandhi"
        },
        {
          message: "“O pessimista vê dificuldade em toda oportuni…tunidade em toda dificuldade”",
          author: "Winston Churchill"
        },
        {
          message: "“A paciência é um elemento fundamental do sucesso”",
          author: "Bill Gates"
        },
        {
          message: "“Reclamar não é uma estratégia. É necessário …ão como gostaríamos que ele fosse”",
          author: "Jeff Bezos"
        },
        {
          message: "“O sucesso não tem a ver com o lugar de onde …e você está disposto a investir”",
          author: "Michelle Obama"
        },
        {
          message: "“Você pode encarar um erro como uma besteira …sultado que aponta uma nova direção”",
          author: "Steve Jobs"
        },
        {
          message: "“Você não pode ser uma pessoa difícil, tímida…o seu foco e em que você acredita”",
          author: "Anna Wintour"
        },
        {
          message: "“Eu posso aceitar a falha, todos falham em al…eu não posso aceitar não tentar”",
          author: "Michael Jordan"
        },
        {
          message: "“Gostaria que você soubesse que existe dentro… e aguarde um novo amanhecer”",
          author: "Margaret Thatcher"
        },
        {
          message: "“Inteligência é a capacidade de se adaptar às mudanças”",
          author: "Stephen Hawking"
        },
        {
          message: "“É preciso ser protagonista. Não dá para fica…passar, temos de ser parte da banda”",
          author: "Sônia Hess"
        }
      ],
    };
  },
  methods: {
    getMessage() {
      var brand = document.getElementById("brand");
      var message = document.getElementById("message-display");
      var button = document.getElementById("action-button");
      message.classList.add("minimize");
      button.classList.add("minimize");
      brand.classList.replace("col-md-2", "col-md-4");
      setTimeout(() => {
        let sort = Math.floor(Math.random() * this.messages.length);
        brand.classList.replace("col-md-4", "col-md-2");
        this.message = `" ${this.messages[sort].message} " - ${this.messages[sort].author}.`;
        message.classList.remove("minimize");
        button.classList.remove("minimize");
      }, 1500);
    },
  },
  beforeMount() {
    let sort = Math.floor(Math.random() * this.messages.length);
    this.message = `" ${this.messages[sort].message} " - ${this.messages[sort].author}.`;
  },
  mounted() {
    this.getMessage();
  },
};
</script>

<style>
@import url("./assets/bootstrap-grid.min.css");

:root {
  --light: #f6f6f6;
  --color: #98ded9;
}

body {
  background: var(--color);
}

#app {
  font-family: Poppins, Roboto, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: var(--light);
  padding-top: 60px;
}

#brand {
  transition: transform 1s ease-in-out, width 0.6s ease-in-out,
    margin 0.5s ease-in-out;
}

#brand.col-md-4 {
  margin-top: 8rem;
}

.logo {
  width: 100%;
}

#message-display {
  transition: all 0.8s ease-in-out, transform 0.3s ease-in-out;
}

.message {
  font-size: 1.5rem;
  text-shadow: 3px 5px 5px rgba(0, 0, 0, 0.6);
  line-height: 2.5rem;
}

#action-button {
  transition: all 0.8s ease-in-out, transform 0.3s ease-in-out;
}

.btn {
  position: relative;
  z-index: 2;
  display: inline-block;
  font-weight: 900;
  line-height: 1.5;
  text-align: center;
  text-decoration: none;
  vertical-align: middle;
  cursor: pointer;
  -webkit-user-select: none;
  -moz-user-select: none;
  user-select: none;
  background-color: transparent;
  border: 1px solid transparent;
  padding: 0.375rem 0.75rem;
  font-size: 1rem;
  border-radius: 0.25rem;
  transition: color 0.15s ease-in-out, background-color 0.15s ease-in-out,
    border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out,
    transform 0.15s ease-in-out;
  color: var(--color);
  background-color: var(--light);
  border-color: var(--light);
}

.btn:hover {
  color: var(--color);
  background-color: var(--light);
  border-color: var(--light);
  box-shadow: 3px 5px 5px rgba(0, 0, 0, 0.1);
  transform: scale(1.02);
}

.btn:focus {
  z-index: 3;
}

.btn-check:focus + .btn,
.btn:focus {
  outline: 0;
  color: var(--color);
  background-color: var(--light);
  border-color: var(--light);
  box-shadow: 0 0 0 0.15rem rgba(0, 0, 0, 0);
}

.btn:disabled,
.btn.disabled {
  pointer-events: none;
  opacity: 0.65;
  color: var(--color);
  background-color: var(--light);
  border-color: var(--light);
}

.btn-check:checked + .btn,
.btn-check:active + .btn,
.btn:active,
.btn.active {
  color: var(--color);
  background-color: var(--light);
  border-color: var(--light);
}

.btn-check:checked + .btn:focus,
.btn-check:active + .btn:focus,
.btn:active:focus,
.btn.active:focus {
  box-shadow: 0 0 0 0.15rem rgba(0, 0, 0, 0);
}

.btn-label {
  font-weight: 900;
  color: var(--color);
  text-shadow: 1px 1px #f6f6f6, -1px -1px rgba(0, 0, 0, 0.5);
  -webkit-background-clip: text;
  -moz-background-clip: text;
  background-clip: text;
}

.minimize {
  transform: scale(0);
}
</style>
