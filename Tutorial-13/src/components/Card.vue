<script>
import BaseCard from "./BaseCard.vue";
export default {
  components: { BaseCard },
  data() {
    return {
      cards: [
        {
          id: 1,
          emoji: "🐱",
          title: "Cat Facts",
          color: "blue",
          description: "Cats sleep 12–16 hours a day and have 32 muscles in each ear.",
          action: "Learn more →",
        },
        {
          id: 2,
          emoji: "🌿",
          title: "Plant Tips",
          color: "green",
          description: "Water your succulents only when the soil is completely dry.",
          action: "Got it ✓",
        },
      ],
    };
  },
};
</script>

<template>
  <div class="layout">
    <BaseCard v-for="card in cards" :key="card.id" :color="card.color">
      <template #header>
        <div class="card-header">{{ card.emoji }} {{ card.title }}</div>
      </template>
      <template #default>
        <p>{{ card.description }}</p>
      </template>
      <template #footer>
        <div class="card-footer">
          <button>{{ card.action }}</button>
        </div>
      </template>
    </BaseCard>
  </div>
</template>

<style>
.layout {
  display: flex;
  gap: 24px;
  padding: 40px;
  background: #f0f0f0;
  min-height: 100vh;
  align-items: flex-start;
  justify-content: center;
}
</style>