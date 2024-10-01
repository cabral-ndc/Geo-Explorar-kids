<template>
  <div>
    <h2>{{ pais.name }}</h2>
    <p>Capital: {{ pais.capital }}</p>
    <p>População: {{ pais.population }}</p>
  </div>
</template>

<script>
export default {
  props: {
    pais: Object
  }
}
</script>
