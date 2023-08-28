<script setup>
import  axios  from  'axios' ;
import { normalizeClass, ref } from 'vue';

const email = ref('');
const senha = ref('');

const cadastrarUsuario = async () => {
    try {
      console.log("Dados antes da submissão:", email.value, senha.value);
      const response = await axios.post("http://localhost/apiphp/api.php", {
        email: email.value,
        senha: senha.value
      })

      console.log(response.data)
      email.value = ""
      senha.value = ""

    } catch (error) {
       console.error("erro ao cadastrar: ", error)
    }
};
</script>

<template>
   <div class="bg-slate-500">
    <form @submit.prevent="cadastrarUsuario">
      <div>
        <label for="email">Email</label>
        <input type="text" name="email" id="email" v-model="email">
      </div>
      <div>
        <label for="senha">senha</label>
        <input type="password" name="senha" id="senha" v-model="senha">
      </div>
      <div>
        <button type="submit">Enviar</button>
      </div>
    </form>
   </div>
</template>