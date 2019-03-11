<template>
    <div :id="randomId">
        {{ name }}
        {{ randomId + 100 }}
        {{ animals[0] }}
        {{ name.split('').reverse().join('').toUpperCase() }}
        {{ Math.floor(randomId) % 2 === 0 ? 'Deljiv' : 'Nije deljiv' }}

        <div v-if="name === 'Marina' ">
            Hello, {{ name }}.
        </div>

        <div v-else>
            Hi.
        </div>

        <div v-show="name !== 'Marina' ">
            Hello, {{ name }}
        </div>

        <div @click="name = 'Pera'">Click me.</div>

        <button v-on:click="handleClick">Click me!</button>

        <a :href="link">Link</a>

        <form @submit.prevent="handleSubmit">
            <button type="submit">Submit</button>
        </form>

        <div :class="{ 'blue': isBlue }">
            Blue
        </div>

        <ul>
            <li v-for="(color, index) in colors" :key="color">
                {{ color }} - {{ index }}
            </li>
        </ul>

        <input type="text" v-model="name"/>

        <input type="text" v-model="ime"/>
        <button @click="naKlik">Greet!</button>
    </div>
</template>

<script>
export default {
  data() {
    return {
      ime: "",
      name: "Marina",
      randomId: Math.random(),
      animals: ["dog", "cat"],
      link: "https://www.google.rs/",
      isBlue: true,
      colors: ["red", "green", "blue"]
    };
  },

  methods: {
    naKlik() {
      alert(`Hello, ${this.ime}`);
    },

    handleClick(event) {
      console.log("clicked", event);
    },

    handleSubmit(event) {
      //   event.preventDefault();
      console.log("submitted");
    }
  }
};
</script>

<style>
.blue {
  background-color: blue;
}
</style>