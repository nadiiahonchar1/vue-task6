<template>
  <div class="container">
    <form class="card" @submit.prevent="submitHandler">
      <h1>Vue developer application form!</h1>
      <div class="form-control">
        <label for="name">What is your name?</label>
        <input
          class="input"
          type="text"
          id="name"
          placeholder="Enter your name"
          v-model.trim="name"
        />
      </div>

      <div class="form-control">
        <label for="age">Choose your age</label>
        <input
          class="input"
          type="number"
          id="age"
          max="100"
          v-model.number="age"
        />
      </div>

      <div class="form-control">
        <label for="city">Choose your city</label>
        <select id="city" class="input" v-model="city">
          <option value="Kyiv">Kyiv</option>
          <option value="Kharkiv">Kharkiv</option>
          <option value="Dnipro">Dnipro</option>
          <option value="Odesa">Odesa</option>
          <option value="Lviv">Lviv</option>
        </select>
      </div>

      <div class="form-checkbox">
        <span class="label">Are you ready to relocation?</span>
        <div class="checkbox">
          <label
            ><input type="radio" v-model="relocate" value="yes" name="trip" />
            Yes</label
          >
        </div>

        <div class="checkbox">
          <label
            ><input type="radio" v-model="relocate" value="no" name="trip" />
            No</label
          >
        </div>
      </div>

      <div class="form-checkbox">
        <span class="label">What do you know about Vue?</span>
        <div class="checkbox">
          <label
            ><input
              type="checkbox"
              v-model="skills"
              value="vuex"
              name="skills"
            />
            Vuex</label
          >
        </div>
        <div class="checkbox">
          <label
            ><input
              type="checkbox"
              v-model="skills"
              value="cli"
              name="skills"
            />
            Vue CLI</label
          >
        </div>
        <div class="checkbox">
          <label
            ><input
              type="checkbox"
              v-model="skills"
              value="router"
              name="skills"
            />
            Vue Router</label
          >
        </div>
      </div>

      <button type="submit" class="btn primary">Send</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      name: "",
      age: 18,
      city: "Odesa",
      relocate: null,
      skills: [],
    };
  },
  components: {},
  methods: {
    submitHandler() {
      console.group("Form Data");
      console.log("Name", this.name);
      console.log("Age", this.age);
      console.log("City", this.city);
      console.log("Relocate", this.relocate);
      console.log("Skills", this.skills);
      console.groupEnd();
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  border: 1px solid blue;
  border-radius: 10px;
  width: 50vw;
  min-width: 500px;
  margin: 20px auto;
  padding: 20px;
}
.card :not(:last-child) {
  margin-bottom: 20px;
}
.input {
  display: block;
  width: 100%;
  box-sizing: border-box;
  /* margin-left: 10px; */
  padding: 5px 20px;
}
</style>
