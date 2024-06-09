<script>
export default {
  props: {
    age: Object
  }
}
</script>

<template>
  <div v-if="age">
    <p class="italic font-medium">
      You are {{ age.years }} years, {{ age.months }} months, and {{ age.days }} days old!
    </p>
  </div>
</template>

<style scoped></style>
