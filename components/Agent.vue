/* eslint-disable */

<template>
    <div class="container">
        <div class="agent-container">
            <img class="agent-img" :src="agentImage" alt="">
        </div>
        <div class="agent-info-container">
            <h2>{{ agentName }}</h2>
            <button>
                <i class="fas fa-chevron-down" @click="scrollToAgent()"></i>
            </button>
        </div>
    </div>
</template>

<script>

export default {
  name: 'AgentComponent',
  props: {
    agentName: String,
    agentImage: String,
    scrollToAgent: Function
  }
}
</script>

<style scoped>

.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 15px
}
.agent-container {
    border: 2px solid white;
    width: 280px;
    height: 470px;
}

.agent-img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.agent-info-container {
    width: 280px;
    height: 120px;
    background-color: white;
    text-align: center;
    padding: 10px;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    box-shadow: 0px 10px 15px #444;
}

h2 {
    padding-top: 10px;
}

button {
    border: none;
    cursor: pointer;
    background-color: transparent;
}

i {
    font-size: 24px;
}
</style>
