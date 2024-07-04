<template>
  <div>
    <a :href="item.href">
      <img :src="item.img" class="normal-Icon" alt="Icon">
      <img :src="item.imgMobile" class="mobile-Icon" alt="Icon">
      <span>{{ item.title }}</span>
    </a>
  </div>
</template>

<script>
export default {
  props: ['item']
}
</script>

<!-- "scoped" faz com que esse "style funcione exclusivamente para esse componente" -->
<style scoped>
div {
  border: solid 1px red;
  width: 120px;
  height: 150px;
  border-radius: 10px;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  margin: 30px 20px;
  border-radius: 16px;
  cursor: pointer;
  background: rgba(255, 255, 255, 0.438);
  box-shadow: 0 4px 30px rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(5.8px);
  -webkit-backdrop-filter: blur(5.8px);
  border: 1px solid rgba(255, 255, 255, 0.57);
}

div:hover {
  transform: translate(0px, -16px)
}

img {
  width: 80px;
  align-self: center;
}

.mobile-Icon {
  display: none;
}

span {
  font-weight: 900;
}

@media (width <=800px) {

  div {
    width: 80%;
    height: 70px;
    margin: 10px 20px;
    border-radius: 50px;
    background-color: #E0E3F0;
  }

  a {
    display: flex;
    flex-direction: row;
    align-items: center;
    text-align: center;
  }

  img {
    width: 50px;
    margin: 0 20px;
  }

  .normal-Icon {
    display: none;
  }

  .mobile-Icon {
    display: block;
  }

  span {
    text-align: start;
    font-size: 20px;
    width: 70%;
  }
}
</style>