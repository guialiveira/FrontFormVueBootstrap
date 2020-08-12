<template>
  <div>
    <form id="formularioPessoa">
      <div class="container">
        <h1>Desafio iRancho</h1>
        <div class="form-group">
          <label>Nome</label>
          <input type="text" class="form-control" id="name" name="name" v-model="pessoa.nome" />
        </div>

        <div class="form-check form-check-inline">
          <input type="checkbox" class="form-chack-input" v-model="pessoa.ativo" />
          <label class="form-check-label">Pessoa ativa</label>
        </div>

        <div class="form-group">
          <label>Email</label>
          <input
            type="email"
            class="form-control"
            id="email"
            aria-describedby="emailHelp"
            placeholder="Exemple@email.com"
            v-model="pessoa.email"
          />
        </div>

        <div class="form-group">
          <label>Endereco</label>
          <input
            type="text"
            class="form-control"
            id="endereco"
            name="endereco"
            v-model="pessoa.endereco"
          />
        </div>

        <div class="form-group">
          <p>Gênero:</p>

          <div class="form-check form-check-inline">
            <input
              type="radio"
              name="sexo"
              class="form-check-input"
              value="M"
              v-model="pessoa.sexo"
            />
            <label class="form-check-label">Masculino</label>
          </div>

          <div class="form-check form-check-inline">
            <input
              type="radio"
              name="sexo"
              class="form-check-input"
              value="F"
              v-model="pessoa.sexo"
            />
            <label class="form-check-label">Feminino</label>
          </div>
        </div>

        <button type="button" class="btn btn-primary">Salvar</button>
      </div>

      <div class="card-header">Model:</div>
      <div class="card-body">
        <pre>
          <code> 
            {{ pessoa }}
          </code>
        </pre>
      </div>
    </form>
  </div>
</template>

<script>
import "bootstrap/dist/css/bootstrap.css";
import pessoaListadas from './../services/listaPessoas'
export default {
  mounted(){
      pessoaListadas.listar().then(resposta => {
        console.log(resposta)
      })
  },
  data() {
    return {
      pessoa: {
        nome: "",
        email: "",
        endereco: "",
        sexo: "M",
        ativo: false,
      },
    };
  },
  methods: {
    
   
  }
};
</script>

<style>
</style>
