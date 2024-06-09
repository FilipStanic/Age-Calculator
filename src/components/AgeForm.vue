<script>
export default {
  data() {
    return {
      birthdate: ''
    }
  },
  methods: {
    calculateAge() {
      const birthdate = new Date(this.birthdate)
      this.$emit('calculate-age', birthdate)
    }
  }
}
</script>

<template>
  <form @submit.prevent="calculateAge">
    <div>
      <div class="space-y-4 w-[500px] flex flex-col items-center justify-center">
        <label for="birthdate" class="block mb-2 text-center text-3xl">Input your birth date</label>
        <input
          type="date"
          v-model="birthdate"
          id="birthdate"
          class="block border border-gray-300 rounded p-2 text-center w-full"
        />

        <button type="submit" class="border bg-blue-300 hover:bg-blue-400 p-2 rounded w-full">
          Check your Age!
        </button>
      </div>
    </div>
  </form>
</template>

<style scoped></style>
