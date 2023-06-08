<template>
  <div class="container">
    <h1 class="title-container">Welcome to this website!</h1>
    <div class="second-title-container">
      <img class="second-title-img" src="https://media.valorant-api.com/agents/e370fa57-4757-3604-3648-499e1f642d3f/killfeedportrait.png" alt="">
      <h1 class="second-title-content">Here you can see about some Valorant info!</h1>
    </div>
    <i class="fas fa-chevron-down" :style="{color: 'white', fontSize: '40px', cursor: 'pointer'}"></i>
  </div>
</template>

<script>
export default {
  name: 'IndexPage'
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Valorant', sans-serif;
}

.container {
  height: 100vh;
  background-color: #101823;
  color: #F24153;
  text-align: center;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}

.title-container {
  font-size: 54px;
  width: 40%;
  padding: 0 0 0 100px;
  animation: fade-in 1s ease forwards;
}

.second-title-container {
  display: flex;
  align-items: center;
  color: #F24153;
  justify-content: space-evenly;
  animation: fade-in 2s ease forwards;
}

.second-title-img {
  height: 100px;
}

@keyframes fade-in {
  0% {
    opacity: 0;
    transform: translateY(20px);
  }
  100% {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
