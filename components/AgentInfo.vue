<template>
  <div class="agent-info-container">
    <div class="agent-image-container" @click="showInfo">
        <img :src="info.fullPortrait" class="agent-image"/>
    </div>
    <div class="agent-info">
      <h1 class="agent-info-title">{{ info.displayName }}</h1>
      <h2 class="agent-info-role">{{ info.role.displayName }}</h2>
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
</style>
