<template>
  <div>
    <input
      :value="firstName"
      @input="$emit('update:firstName', $event.target.value)"
      placeholder="First name"
    />
    <input
      :value="lastName"
      @input="$emit('update:lastName', $event.target.value)"
      placeholder="Last name"
    />
  </div>
</template>

<script>
export default {
  props: ['firstName', 'lastName'],
  emits: ['update:firstName', 'update:lastName']
}
</script>