<template>
  <div v-if="submit === ''" class="container-form">
    <h1>Personal Data</h1>
    <form @submit.prevent="onSubmit">
      <input
        v-model="name"
        class="__input"
        type="text"
        placeholder="Insert name"
      />
      <input
        v-model="lastName"
        class="__input"
        type="text"
        placeholder="Insert lastName"
      />
      <input
        v-model="city"
        class="__input"
        type="text"
        placeholder="Insert city"
      />
      <input
        v-model="age"
        class="__input"
        type="number"
        placeholder="Insert age"
      />
      <div>
        <button type="submit">Submit</button>
      </div>
    </form>
  </div>
  <div v-else>
    <nuxt-link v-if="submit !== ''" to="/resume">Resume</nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'Data',
  data() {
    return {
      name: '',
      lastName: '',
      city: '',
      age: '',
      submit: '',
    }
  },
  methods: {
    clearInput() {
      this.name = ''
      this.lastName = ''
      this.city = ''
      this.age = ''
    },
    onSubmit() {
      const obj = {
        name: this.name,
        lastName: this.lastName,
        city: this.city,
        age: this.age,
      }
      localStorage.setItem('data', JSON.stringify(obj))
      this.clearInput()
      this.submit = 'ok'
    },
  },
}
</script>

<style>
.container-form {
  width: 400px;
  height: 300px;
  border: 1px solid grey;
  border-radius: 10px;
  display: flex;
  align-items: center;
  flex-direction: column;
  justify-content: center;
}
.__input {
  margin-top: 20px;
  min-width: 200px;
}
</style>
