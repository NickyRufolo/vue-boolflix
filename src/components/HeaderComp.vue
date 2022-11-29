<template>
  <header class="d-flex justify-content-end">
    <div class="input-group my-3 d-flex w-auto me-3">
      <input type="text" class="form-control" v-model="InputUtente" placeholder="Tonight I wanna see..." aria-label="Recipient's username"
        aria-describedby="button-addon2">
      <button @click="$emit(`emitSearch`, InputUtente)" class="btn btn-outline-secondary" type="button" id="button-addon2">Search</button>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderComp',
  data(){
    return{
      InputUtente: `` //associato al v-model quando scrive l'utente
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
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
