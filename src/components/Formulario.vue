<template>
  <form>
    <label>Email:</label>
    <input type="email" required v-model="email">
    
    <label>Password:</label>
    <input type="password" required v-model="password">

    <label>Cargo:</label>
    <select v-model="cargo">
      <option value="webdev">Desenvolvedor Web</option>
      <option value="webdedigner">Web Designer</option>
    </select>

    <div class="terms">
      <input type="checkbox" required v-model="termos">
      <label>Aceito os termos de uso</label>
    </div>

    <div>
      <input type="checkbox" value="luigi" v-model="nomes">
      <label>Luigi</label>
    </div>
    <div>
      <input type="checkbox" value="mario" v-model="nomes">
      <label>Mario</label>
    </div>
    <div>
      <input type="checkbox" value="ricardo" v-model="nomes">
      <label>Ricardo</label>
    </div>
  </form>
  <p>Email: {{ email }}</p>
  <p>Password: {{ password }}</p>
  <p>Cargo: {{ cargo }}</p>
  <p>Termos: {{ termos }}</p>
  <p>Nomes: {{ nomes }}</p>
</template>

<script>
export default {
  data(){
    return {
      email: "",
      password: "",
      cargo: "webdev",
      termos: false,
      nomes: []
    };
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
</style>