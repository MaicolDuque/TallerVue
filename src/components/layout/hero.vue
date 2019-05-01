<template>

    <section class="hero">
    <figure>
        <img v-bind:src="person.data[0].picture.large" alt="Imagen Hero">
    </figure>
    </section>

</template>
<script>
export default {
  props: {
    person: { type: Object, required: true}
  },
  data () {
    return {
    }
  }
}
</script>

<style>
.hero {
  display: flex;
  height: 400px;
  width: 100%;
  flex-direction: row;
  justify-content: center;
}
.hero  figure img{
  display: flex;
  height: 350px;
  width: 350px;
  object-fit: cover;
  border-radius: 50%;
}
</style>
