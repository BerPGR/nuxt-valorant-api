/* eslint-disable */

<template>
    <div class="container">
        <div class="agent-container" :style="{backgroundImage: 'url(' + fullAgent.background +')'}">
            <img class="agent-img" :src="fullAgent.fullPortrait" alt="">
        </div>
        <div class="agent-info-container">
            <h2>{{ fullAgent.displayName }}</h2>
            <button @click="scrollToAgent(fullAgent)">
                <i class="fas fa-chevron-down"></i>
            </button>
        </div>
    </div>
</template>

<script>

export default {
  name: 'AgentComponent',
  props: {
    fullAgent: Object,
    scrollToAgent: Function
  }
}
</script>

<style scoped>
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 15px;
}
.agent-container {
    border: 2px solid white;
    width: 280px;
    height: 470px;
    background-repeat: no-repeat;
    background-size: contain;
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
