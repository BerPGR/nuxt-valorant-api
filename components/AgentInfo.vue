<template>
  <div class="agent-info-container">
    <div class="agent-image-container" :style="{backgroundImage: 'url('+ info.background +')'}">
        <img :src="info.fullPortrait" class="agent-image"/>
    </div>
    <div class="agent-info">
      <h1 class="agent-info-title">{{ info.displayName }}</h1>
      <h2 class="agent-info-role">{{ info.role.displayName }}</h2>
      <p class="agent-info-description">{{ info.description }}</p>
      <h1 class="agent-info-abilitites">Abilities</h1>
      <div class="agent-abilities-container">
        <div class="agent-ability" v-for="(ability, i) in info.abilities" :key="i" @click="toogleAbilityDescription(ability.description)">
          <img :src="ability.displayIcon" alt="" class="agent-ability-icon">
          <p class="agent-ability-name">{{ ability.displayName }}</p>
        </div>
      </div>
      <div class="agent-ability-description" v-if="abilityDescription == true">
        <p>{{ description }}</p>
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
  data: () => ({
    abilityDescription: false,
    description: ''
  }),
  methods: {
    toogleAbilityDescription (desc) {
      this.abilityDescription = true
      this.description = desc
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
    background-repeat: no-repeat;
    background-size: contain;
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
  cursor: pointer;
  margin-left: 15px;
}

.agent-ability-icon {
  height: 50px;
  object-fit: cover;
}

.agent-ability-name {
  color: #F24153;
  text-align: center;
  padding-top: 20px;
  animation: fade-in 1s ease-in forwards
}

.agent-ability-description {
  text-align: center;
  color: white;
  margin-top: 20px;
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
