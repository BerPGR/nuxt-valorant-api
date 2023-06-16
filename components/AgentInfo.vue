<template>
  <div class="agent-info-container">
    <div class="agent-image-container" @click="showInfo">
        <img :src="info.fullPortrait" class="agent-image"/>
    </div>
    <div class="agent-info">
      <h1 class="agent-info-title">{{ info.displayName }}</h1>
      <h2 class="agent-info-role">{{ info.role.displayName }}</h2>
      <p class="agent-info-description">{{ info.description }}</p>
      <h1 class="agent-info-abilitites">Abilities</h1>
      <div class="agent-abilities-container">
        <div class="agent-ability" v-for="(ability, i) in info.abilities" :key="i">
          <img :src="ability.displayIcon" alt="" class="agent-ability-icon">
          <p :style="{color: '#F24153', textAlign: 'center', paddingTop: '20px'}">{{ ability.displayName }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AgentInfoComponent',
  props: {
    info: Object
  },
  methods: {
    showInfo () {
      console.log(this.info.fullPortrait)
    }
  }
}
</script>

<style scoped>
.agent-info-container {
    display: flex;
    padding: 10px 120px 0;
    justify-content: space-around;
}

.agent-image-container {
    width: 300px;
    height: 560px;
    border: none;
}

.agent-image {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.agent-info {
  display: flex;
  flex-direction: column;
  width: 420px;
}

.agent-info-title {
  color: #F24153;
  font-size: 54px;
  text-align: center;
}

.agent-info-role {
  color: white;
  margin-top: 20px;
}

.agent-info-description {
  margin-top: 20px;
  color: white;
}

.agent-info-abilitites {
  color: #F24153;
  font-size: 54px;
  text-align: center;
  margin-top: 60px;
}

.agent-abilities-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-top: 20px;
}

.agent-ability {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-right: 15px;
  cursor: pointer;
}

.agent-ability-icon {
  height: 50px;
  object-fit: cover;
}
</style>
