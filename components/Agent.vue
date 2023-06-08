/* eslint-disable */

<template>
    <div class="container">
        <div class="agent-container">
            <img class="agent-img" :src="agent.fullPortrait" alt="">
        </div>
        <div class="agent-info-container">
            <h2>{{ agent.displayName }}</h2>
            <button>
                <i class="fas fa-chevron-down"></i>
            </button>
        </div>
    </div>
</template>

<script>

export default {
  name: 'AgentComponent',
  data: () => ({
    agent: {}
  }),
  async fetch () {
    const agent = await this.$axios.get('https://valorant-api.com/v1/agents/e370fa57-4757-3604-3648-499e1f642d3f')
    this.agent = await agent.data.data
  }
}
</script>

<style scoped>

.container {
    display: flex;
    flex-direction: column;
    align-items: center;
}
.agent-container {
    border: 2px solid white;
    width: 260px;
    height: 470px;
}

.agent-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.agent-info-container {
    width: 260px;
    height: 120px;
    background-color: white;
    text-align: center;
    padding: 10px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    box-shadow: 0px 10px 15px #444;
}

button {
    border: none;
    cursor: pointer;
}

i {
    font-size: 24px;
}
</style>
