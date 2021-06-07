<template>
  <div class="container">
    <div class="container__resume">
      <h1>Resume Data</h1>
      <p>Name:{{ name }}</p>
      <p>LastName:{{ lastName }}</p>
      <p>city:{{ city }}</p>
      <p>age:{{ age }}</p>
    </div>
  </div>
</template>

<script>
const dataFromLocalStorage = JSON.parse(localStorage.getItem('data'))
console.log(dataFromLocalStorage)
export default {
  name: 'ResumeData',
  data() {
    return {
      name: dataFromLocalStorage.name,
      lastName: dataFromLocalStorage.lastName,
      city: dataFromLocalStorage.city,
      age: dataFromLocalStorage.age,
    }
  },
}
</script>

<style>
.container {
  display: flex;
  justify-content: start;
  flex-direction: column;
  width: 100vw;
}
.container__resume {
  margin-top: 50px;
  display: flex;
  align-items: start;
  flex-direction: column;
  width: 15%;
}
p {
  margin-top: 10px;
}
</style>
