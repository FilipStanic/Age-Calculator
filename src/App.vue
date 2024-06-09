<script>
import AgeForm from './components/AgeForm.vue'
import AgeResult from './components/AgeResult.vue'

export default {
  name: 'App',
  components: {
    AgeForm,
    AgeResult
  },
  data() {
    return {
      calculatedAge: null
    }
  },
  methods: {
    ageCalc(birthdate) {
      const today = new Date()
      let years = today.getFullYear() - birthdate.getFullYear()
      let months = today.getMonth() - birthdate.getMonth()
      let days = today.getDate() - birthdate.getDate()

      if (days < 0) {
        months -= 1
        days += new Date(today.getFullYear(), today.getMonth(), 0).getDate()
      }
      if (months < 0) {
        years -= 1
        months += 12
      }

      this.calculatedAge = { years, months, days }
    }
  }
}
</script>

<template>
  <main>
    <div class="space-y-4 h-screen flex flex-col items-center justify-center">
      <AgeForm @calculate-age="ageCalc" />
      <AgeResult :age="calculatedAge" />
    </div>
  </main>
</template>

<style scoped></style>
