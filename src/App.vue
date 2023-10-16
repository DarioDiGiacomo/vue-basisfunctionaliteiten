<script>
export default {
  data() {
    return {
      titel: 'dit is een titel',
      intro: 'dit is een intro',
      monk: 'monk.png',
      name: 'Dario Di Giacomo',
      age: 19,
      website: 'https://vuejs.org/',
      showMe: false,
      monkey: 'monkey.png',
      buttonName: 'change picture'
      
    }
  },
  methods: {
    value() {
      let randomNumber = Math.random()

      if (randomNumber > 0.5) {
        return "Wie zoerk die vindt"
      }
      else {
        return "Wij verkopen je beste producten die je op de markt kan vinden"
      }
    },
    randomNumber() {
      let randomNumber = Math.random(0, 1)
      return randomNumber;
    },
    changePicture(monkey, buttonName) {
      this.monk = monkey;
      this.buttonName = `${buttonName}`;
    }
  }
}
</script>

<template>
  <h1>Welkom in de Vue App</h1>
  <h1>{{ titel }}</h1>
  <p>{{ intro }}</p>
  <img v-if="monk" :src="'/assets/' + monk" alt="monk" @click="showMe = true">
  <button @click="changePicture(monkey, 'picture changed')">{{ buttonName }}</button>
  <button v-if="showMe" @click="showMe = false">Hide Me</button>
  <p>{{ value() }}</p>
  <h2  @click="age++">{{ name }}</h2>
  <p>{{ age }}</p>
  <p>{{ age + 5 }}</p>
  <p>{{ randomNumber() }}</p>
  <a :href="website" target="_blank">website</a>
  <input type="text" :value="name">
</template>

<style>
img {
  width: 75%;
}
</style>
