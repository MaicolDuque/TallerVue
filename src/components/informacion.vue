<template>
    <section class="information">
      <h1> {{person.data[0].nombre.nombre | capitalize}} {{person.data[0].nombre.apellido | capitalize}}</h1>
      <h2> {{person.data[0].area}}</h2>
      <h2> {{person.data[0].location.departamento}} {{person.data[0].location.pais}}</h2>
    </section>
</template>
<script>
export default {
  props: {
    person: { type: Object, required : true}
  },
  data () {
    return {
    }
  },
  filters: {
  capitalize: function (value) {
    value = value.toString()
    return value.charAt(0).toUpperCase() + value.slice(1)
  }
}
}
</script>
<style>
.information {
  padding-top: 50px;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 50px;
}
</style>


