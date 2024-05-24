<script>
export default {
  data() {
    return {
      message: "Hello VueJs",
      count: 0,
      name: "",
      users: ["Sardor", "Vali", "Ali", "Jumavoy"],
      img: "https://e7.pngegg.com/pngimages/436/593/png-clipart-vue-js-logo-landscape-tech-companies-thumbnail.png",
      user: {
        name: "Bekzod",
        age: 20,
        course: ["Vue", "NodeJs"],
      },
      groups: [
        {
          number: "1",
          students_count: 10,
          students: [
            {
              name: "Sardor",
              age: 34,
            },
            {
              name: "Bekzot",
              age: 34,
            },
            {
              name: "Muhammad",
              age: 34,
            },
            {
              name: "Farzot",
              age: 34,
            },
            {
              name: "Amir",
              age: 34,
            },
          ],
        },
        {
          number: "2",
          students_count: 9,
          students: [
            {
              name: "Alina",
              age: 34,
            },
            {
              name: "Nargiza",
              age: 34,
            },
            {
              name: "Husan",
              age: 34,
            },
          ],
        },
        {
          number: "3",
          students_count: 8,
          students: [
            {
              name: "Rustam",
              age: 34,
            },
            {
              name: "Bobur",
              age: 34,
            },
            {
              name: "Samandar",
              age: 34,
            },
          ],
        },
      ],
      arr: [],
      input: "",
    };
  },
  methods: {
    counter() {
      this.count++;
    },
    reset() {
      save.count = 0;
    },
    addName() {
      if (this.input.trim() == "") return;
      this.arr.push(this.input);
    },
    handleInput() {
      console.log("input event: ", this.input);
    },
  },
};
</script>

<template>
  <div>
    <input type="text" v-model="input" />
    <button @click="addName">Add</button>
  </div>

  <div v-for="(item, index) in arr" :key="index">
    {{ item }}
  </div>

  <div>
    <h1 class="logo">{{ message }}</h1>
    <input type="text" v-model="name" class="inp" />
    <h2 v-if="name.length > 10">v-if {{ name }}</h2>
    <h2 v-else-if="name.length > 5">v-else-if {{ name }}</h2>
    <h2 v-else>v-else {{ name }}</h2>
    <!-- <h3 v-show="name.length > 10">v-show {{ name }}</h3> -->
    <h1 v-once>{{ count }}</h1>
    <button @click="counter">Count: {{ count }}</button>
    <button @click="reset">Reset</button>
    <ul>
      <li v-for="(item, index) in users" :key="index">{{ item }}</li>
    </ul>
    <img :src="img" alt="" />
    <img src="./assets/vue.svg" alt="" />
    <h1 :class="{ active: name.length > 10 }">Binding class</h1>
    <div v-for="item in user.course">
      {{ item }}
    </div>

    <div class="groups">
      <div class="group" v-for="(item, index) in groups" :key="index">
        <h6>Group number{{ item.number }}</h6>
        <h6>Number of students{{ item.students_count }}</h6>
        <ul>
          <li v-for="students in item.students">
            <p>name:{{ students.name }}</p>
            <p>age:{{ students.age }}</p>
          </li>
        </ul>
      </div>
    </div>

    <div>
      <input type="text" v-model="models" />
      <button @click="models">Add</button>
      <p>{{ models }}</p>
    </div>
  </div>
</template>

<style scoped>
input {
  padding: 10px 20px;
}
.groups {
  display: grid;
  gap: 20px;
  grid-template-columns: repeat(3, 300px);
}
.group {
  background-color: white;
  padding: 5px;
  border-radius: 10px;
  margin-bottom: 20px;
  color: black;
}

.active {
  font-size: 30px;
  color: red;
}

h1 {
  font-size: 30px;
}

button:hover {
  filter: drop-shadow(0 0 2em #0014f5aa);
  color: white;
}

button {
  display: flex;
  margin: 0 auto;
}
.inp {
  will-change: filter;
  transition: filter 300ms;
  color: white;
}

.inp:focus {
  filter: drop-shadow(0 0 2em #0014f5aa);
}
.logo {
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
  color: red;
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #0014f5aa);
}
.logo:hover {
  filter: drop-shadow(0 0 2em #f50000aa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #ef0000aa);
}
</style>
