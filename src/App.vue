<template>
  <h1 class="label-title">Calculo do IMC</h1>
  <h2 class="label-subtitle">Digite seu peso e altura para calcular o seu IMC</h2>
  
  <div class="div-imc">
      <span class="p-float-label">
        <InputText id="input-weight" type="text" v-model="weight" />
        <label for="input-weight">Peso</label>
      </span>
  </div>

  <div class="div-imc">
      <span class="p-float-label">
        <InputText id="input-height" type="text" v-model="height" />
        <label for="input-height">Altura</label>
      </span>
  </div>

  <div class="div-imc">
      <Button label="Calcular" @click="calculate" />
  </div>

  <div>
    <p>Seu IMC é: {{imc}}</p>
  </div>
</template>

<script>
export default {
  data(){
    return {
      height: null,
      weight: null,
      imc: null
    }
  }, 
methods: {
  calculate: function(){
    this.imc = (this.weight / (this.height * this.height)).toFixed(2);
    console.log(this.imc);
  }
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.div-imc{
  margin-top: 2rem ;
}
.label-title {
  font-size: 2rem;
}
.label-subtitle {
  font-size: 1.1rem;
}
</style>
