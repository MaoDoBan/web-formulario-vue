<template>
  <form @submit.prevent="handleSubmit">
    <label>Email:</label>
    <input type="email" required v-model="email">
    
    <label>Senha:</label>
    <input type="password" required v-model="senha">
    <div v-if="erroSenha" class="erro">{{ erroSenha }}</div>

    <label>Cargo:</label>
    <select v-model="cargo">
      <option value="webdev">Desenvolvedor Web</option>
      <option value="webdedigner">Web Designer</option>
    </select>

    <label>Skills:</label>
    <input type="text" v-model="tempSkill" @keyup="addSkill">
    <div v-for="skill in skills" :key="skill" class="pill">
      <span @click="deleteSkill(skill)">{{ skill }}</span>
    </div>

    <div class="terms">
      <input type="checkbox" required v-model="termos">
      <label>Aceito os termos de uso</label>
    </div>

    <div class="submit">
      <button>Criar uma conta</button>
    </div>
  </form>
  <p>Email: {{ email }}</p>
  <p>Senha: {{ senha }}</p>
  <p>Cargo: {{ cargo }}</p>
  <p>Termos: {{ termos }}</p>
</template>

<script>
export default {
  data(){
    return {
      email: "",
      senha: "",
      cargo: "webdev",
      termos: false,
      tempSkill: "",
      skills: [],
      erroSenha: ""
    };
  },
  methods: {
    addSkill(e){
      if(e.key === "Enter" && this.tempSkill){
        if(!this.skills.includes(this.tempSkill)) this.skills.push(this.tempSkill);
        this.tempSkill = "";
      }
    },
    deleteSkill(skill){
      this.skills = this.skills.filter((item) => item !== skill);
    },
    handleSubmit(){
      this.erroSenha = this.senha.length < 13 ? "A senha precisa ter ao menos 13 caracteres!" : "";
      if(this.passwordError) return;

      console.log("email: ", this.email);
      console.log("senha: ", this.senha);
      console.log("cargo: ", this.cargo);
      console.log("skills: ", this.skills);
      console.log("aceitou os termos: ", this.termos);
    }
  }
}
</script>

<style>
form{
  max-width: 420px;
  margin: 30px auto;
  background: white;
  text-align: left;
  padding: 40px;
  border-radius: 10px;
}
label{
  color: #aaa;
  display: inline-block;
  margin: 25px 0 15px;
  font-size: 0.6em;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: bold;
}
input, select{
  display: block;
  padding: 10px 6px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid #ddd;
  color: #555;
}
input[type="checkbox"]{
  display: inline-block;
  width: 16px;
  margin: 0 10px 0 0;
  position: relative;
  top: 2px;
}
.pill{
  display: inline-block;
  margin: 20px 10px 0 0;
  padding: 6px 12px;
  background:#eee;
  border-radius: 20px;
  font-size: 12px;
  letter-spacing: 1px;
  font-weight: bold;
  color: #777;
  cursor: pointer;
}
button{
  background: #0b6dff;
  border: 0;
  padding: 10px 20px;
  margin-top: 20px;
  color: white;
  border-radius: 20px;
}
.submit{
  text-align: center;
}
.erro{
  color: #ff0062;
  margin-top: 10px;
  font-size: 0.8em;
  font-weight: bold;
}
</style>