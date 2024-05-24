<script></script>

<template>
  <div>
    <h1>Hello Vue</h1>
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
