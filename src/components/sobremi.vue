<template> 
      <section class="sobre">
        <h2 class="sobre-titulo">Sobre mi</h2>
          <p>{{ person.data[0].sobre}}</p>
      </section>
</template>
<script>
export default {
  props: {
    person: Object , required: true 
  },
  data () {
    return {
    }
  }
}
</script>
<style>
.sobre {
  padding-top: 90px;
  width: 600px;
  margin: 0 auto;
}
.sobre p {
  font-size: 20px;
  margin: 10px 0 10px 0;
  padding: 10px;
}

</style>

