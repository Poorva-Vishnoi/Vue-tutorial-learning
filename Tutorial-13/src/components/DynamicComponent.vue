<script>
import CatCard from './CatCard.vue'
import PlantCard from './PlantCard.vue'

export default {
  components: { CatCard, PlantCard },
  data() {
    return {
      current: 'CatCard'
    }
  }
}
</script>

<template>
  <div class="wrapper">

    <!-- Tab Buttons -->
    <div class="tabs">
      <button 
        @click="current = 'CatCard'"
        :class="{ active: current === 'CatCard' }"
      >
        🐱 Cat Facts
      </button>
      <button 
        @click="current = 'PlantCard'"
        :class="{ active: current === 'PlantCard' }"
      >
        🌿 Plant Tips
      </button>
    </div>

    <!-- Dynamic Component -->
    <component :is="current" />

  </div>
</template>

<style>
.wrapper {
  padding: 40px;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 24px;
}

.tabs {
  display: flex;
  gap: 12px;
}

.tabs button {
  padding: 8px 20px;
  border-radius: 20px;
  border: 1.5px solid #ccc;
  background: transparent;
  cursor: pointer;
  font-size: 14px;
}

.tabs button.active {
  background: #1a5fa8;
  color: white;
  border-color: #1a5fa8;
}
</style>