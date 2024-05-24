<script>
export default {
  data() {
    return {
      message: "Hello Vue js",
      count: 0,
      name: "",
      users: [],
      image:
        "https://img-cdn.pixlr.com/image-generator/history/65bb506dcb310754719cf81f/ede935de-1138-4f66-8ed7-44bd16efc709/medium.webp",
      user: {
        name: "sardor",
        age: 20,
        job: "programmer",
      },
      groups: [
        {
          number: "1",
          amount: 10,
          pupils: [
            {
              name: "sardor",
              age: 20,
              job: "programmer",
            },
            {
              name: "hojiakbar",
              age: 37,
              job: "programmer",
            },
            {
              name: "jumavoy",
              age: 30,
              job: "programmer",
            },
            {
              name: "tursunqul",
              age: 24,
              job: "programmer",
            },
          ],
        },
        {
          number: "2",
          amount: 10,
          pupils: [
            {
              name: "sardor",
              age: 20,
              job: "programmer",
            },
            {
              name: "hojiakbar",
              age: 37,
              job: "programmer",
            },
            {
              name: "jumavoy",
              age: 30,
              job: "programmer",
            },
            {
              name: "tursunqul",
              age: 24,
              job: "programmer",
            },
          ],
        },
      ],
    };
  },
  methods: {
    add() {
      this.users.push(this.name);
      this.name = "";
    },
    handleInput() {
      console.log(this.name);
    },
  },
};
</script>

<template>
  <div>
    <!-- <h1>{{ message }}</h1>
    <input type="text" v-model="name" />
    <h2 v-if="name.length > 10">v-if:{{ name }}</h2>
    <h2 v-else-if="name.length > 5">v-else-if: {{ name }}</h2>
    <h2 v-else>v-else: {{ name }}</h2>

    <h3 v-show="name.length > 10">v-show: {{ name }}</h3>

    <h1 v-once>{{ count }}</h1>

    <button @click="increment">count: {{ count }}</button>

    <ul>
      <li v-for="(item, index) in users" :key="index">{{ item }}</li>
    </ul>

    <img v-bind:src="image" alt="" />

    <h1 :class="{ active: name.length > 10 }">Binding class</h1>
    <div v-for="item in user">
      {{ item }}
    </div> -->
    <!-- <div class="groups">
      <div class="group" v-for="(item, index) in groups" :key="index">
        <h1>Guruh raqami: {{ item.number }}</h1>
        <h1>Student amount: {{ item.amount }}</h1>
        <h2>O'quvchilar</h2>
        <ul>
          <li v-for="pupil in item.pupils">
            <p>ismi: {{ pupil.name }}</p>
            <p>yoshi: {{ pupil.age }}</p>
          </li>
        </ul>
      </div>
    </div>-->
    <input
      @keyup.enter="add"
      type="text"
      v-model="name"
    />
    <button @click="add()">Add</button>
    <ul>
      <li v-for="(item, index) in users" :key="index">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<style scoped>
input {
  padding: 10px;
}
.groups {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
}
.group {
  background-color: #fff;
  padding: 5px;
  border-radius: 10px;
  margin-bottom: 20px;
  color: black;
  box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.2);
}
/* .active {
  font-size: 30px;
  color: red;
} */
</style>
