<template>
  <header class="d-flex justify-content-between">
    <div class="netflix text-danger py-3 px-3"> <strong><H1>NETFLIX</H1></strong></div>
    <div class="input-group my-3 w-auto me-3">
      <input type="text" class="form-control" v-model="InputUtente" placeholder="Tonight I wanna see..." aria-label="Recipient's username"
        aria-describedby="button-addon2">
      <button @click="$emit(`emitSearch`, InputUtente)" class="btn btn-outline-danger" type="button" id="button-addon2">Search</button>
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
header{
  height: 10%;
}
</style>
