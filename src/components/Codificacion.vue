<template>
  <div class="codificacion">
    <div class="jumbotron">
    <h4><u>Input</u></h4>     
        <input type="text" :value="string" @input="actualizar($event)"> <br>
        <br>
        <h4>cantidad: {{ string.length }}</h4>
        <br>
        <h4> {{ string | codificar }} (codificado)</h4>
        <br>
        <h4> {{ string | capitalize }} (Mayuscula)</h4>
        <br>
        <h4> {{ string | decapitalize }} (Minuscula)</h4>
        <br>
        <h4> {{ string | alternarMayus }} (Mayuscula/Minuscula)</h4>
        <br>
        <h4> {{ string | alternarMinus }} (Minuscula/Mayuscula)</h4>
  
    <br>
    <hr>
    <p>Respuestas: 1:b, 2:b , 3:c, 4:b, 5:b,c </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Codificacion',
  data() {
    return {
        string:"Hola Mundo!",

             
    }
  },
  methods: {
    actualizar(e) {
          let dato = e.target.value      
          this.string = dato   
      }
    },
  computed: {
    
    },
  filters: {
    capitalize: function (value) {
      if (!value) return ''
      value = value.toString()
      return value.toUpperCase()
    },
    decapitalize: function (value) {
      if (!value) return ''
      value = value.toString()
      return value.toLowerCase()
    },
    codificar: function(value){
      if (!value) return ''
      let rta = value.split("a").map(s => s.split("u").join("a")).join("u").split("e").map(s => s.split("o").join("e")).join("o")

      return rta
    },
    alternarMayus: function(value){
      if (!value) return ''
      var chars = value.toLowerCase().split("");
      for (var i = 0; i < chars.length; i += 2) {
        chars[i] = chars[i].toUpperCase();
      }
      return chars.join("");
    },
    alternarMinus: function(value){
      if (!value) return ''
      var chars = value.toLowerCase().split("");
      for (var i = 1; i < chars.length; i += 2) {
        chars[i] = chars[i].toUpperCase();
      }
      return chars.join("");
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
