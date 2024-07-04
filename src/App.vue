<script setup>

import Item from "./components/item.vue"
</script>

<script>

import Dados from "./data/data.json"
export default {
  data() {
    return {
      datas: null
    }
  },
  mounted() {
    this.datas = Dados
    // console.log(Dados)
  }
}

</script>

<template>
  <div>
    <header>

      <div class="profile">
        <img src="./assets/profile.png" />
      </div>

      <h1>Emerson Batista</h1>

    </header>
    <hr />
    <hr />
    <div class="card">
      <Item v-for="references, index in datas" :key="index" :item="references" />
    </div>

    <footer>
      <h3>Emerson Batista - 2024</h3>
    </footer>
  </div>
</template>

<style scoped>
header {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: 50px 0 20px 0;
  color: #221E40;
}

.profile {
  display: flex;
  width: 170px;
  border-radius: 100%;
}

.profile:hover {
  border: solid 6px;
}

.profile img {
  border-radius: 100%;
  width: 100%;
}

h1 {
  color: #221E40;
  line-height: 1.5;
  position: relative;
}

h1::before {
  content: '';
  width: 0;
  height: 5px;
  border-radius: 2px;
  background-color: #221E40;
  position: absolute;
  bottom: -.25rem;
  left: 50%;
  transition: width .4s, left .4s;
}

h1:hover::before {
  width: 100%;
  left: 0;
}

.card {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  margin: 50px 0;
}

footer {
  position: fixed;
  bottom: 0;
  width: 100%;
  background: rgba(255, 255, 255, 0.22);
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(5.8px);
  -webkit-backdrop-filter: blur(5.8px);
  border: 1px solid rgba(255, 255, 255, 0.57);
}

@media (width <= 800px) {

  h1 {
    color: #E0E3F0;
  }

  .card {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  footer {
    background-color: #E0E3F0;
  }
}

</style>
