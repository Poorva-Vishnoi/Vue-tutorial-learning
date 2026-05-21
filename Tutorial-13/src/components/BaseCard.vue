<script>
export default {
  props: {
    color: {
      type: String,
      default: 'blue' // 'blue' or 'green'
    }
  }
}
</script>

<template>
  <div class="card" :class="color">
    <slot name="header"></slot>
    <slot name="default"></slot>
    <slot name="footer"></slot>
  </div>
</template>

<style scoped>
.card {
  border: 1px solid #e0e0e0;
  border-radius: 16px;
  width: 200px;
  overflow: hidden;
  background: #fff;
  box-shadow: 0 2px 8px rgba(0,0,0,0.06);
}

/* Header slot styling */
.card :deep(.card-header) {
  padding: 14px 16px;
  font-size: 15px;
  font-weight: 600;
  display: flex;
  align-items: center;
  gap: 8px;
}

.card.blue :deep(.card-header) {
  background: #deeeff;
  color: #1a5fa8;
}

.card.green :deep(.card-header) {
  background: #dff2e0;
  color: #2e7d32;
}

/* Body */
.card :deep(p) {
  font-size: 14px;
  line-height: 1.55;
  color: #333;
  margin: 0;
  padding: 16px;
}

/* Footer */
.card :deep(.card-footer) {
  padding: 0 16px 16px;
}

.card :deep(button) {
  width: 100%;
  padding: 8px 14px;
  border-radius: 10px;
  border: 1.5px solid #ccc;
  background: transparent;
  cursor: pointer;
  font-size: 13px;
  font-weight: 500;
  color: #333;
  transition: background 0.15s;
}

.card :deep(button:hover) {
  background: #f5f5f5;
}
</style>