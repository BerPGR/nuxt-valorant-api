<template>
  <div class="container">

    <div class="first-section">
      <h1 class="title-container">Welcome to this website!</h1>
      <div class="second-title-container">
        <img class="second-title-img" src="https://media.valorant-api.com/agents/e370fa57-4757-3604-3648-499e1f642d3f/killfeedportrait.png" alt="">
        <h1 class="second-title-content">Here you can see about some Valorant info!</h1>
      </div>
      <i class="fas fa-chevron-down" :style="{color: 'white', fontSize: '40px', cursor: 'pointer'}" @click="scrollToSecondDiv"></i>
    </div>

    <div class="second-section">
      <h1 class="second-section-title">Check out some of the agents</h1>
      <div class="agents-container">
        <div v-for="(agent, i) in agents" :key="i">
          <Agent :agentName="agent.displayName" :agentImage="agent.fullPortrait"/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import VueScrollTo from 'vue-scrollto'

export default {
  name: 'IndexPage',
  async fetch () {
    const agents = await this.$axios.get('https://valorant-api.com/v1/agents?isPlayableCharacter=true')
    this.agents = agents.data.data
  },
  data: () => ({
    agents: []
  }),
  methods: {
    scrollToSecondDiv () {
      VueScrollTo.scrollTo('.second-section', 1000)
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Valorant', sans-serif;
}

.first-section {
  min-height: 100vh;
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

.second-section {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  background-color: #888;
  text-align: center;
}

.second-section-title {
  padding-top: 50px
}

.agents-container {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  flex-wrap: wrap;
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
