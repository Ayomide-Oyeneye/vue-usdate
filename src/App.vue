<template>
  <div>
    {{ value }}
    <br />
    Date: {{ date.toString() }}
    <br />
    Day: {{ getDay() }}
    <br />
    Month: {{ getMonth() }}
    <br />
    <input type="text" v-model="input" @input="handleChange" />
    <button @click="changeTheWorld">Change The World</button>
  </div>
  </template>
  
  <script>
  export default {
  data() {
    return {
      input: '',
      value: 'Helloworld',
      date: new Date(),
    };
  },
  methods: {
    handleChange(event) {
      this.input = event.target.value;
    },
    changeTheWorld() {
      this.value= this.input;
    },
    getDay() {
      return this.date.getDate();
    },
    getMonth() {
      return this.date.getMonth();
    },
  },
  watch: {
    input(newValue) {
      console.log('Input changed', newValue);
    },
  },
  };
  </script>
  <style>
  *{
    font-size: xx-large;
  }
  input{
    width: 100%;
  }
</style>
  