<template>
  <div class="card" :class="{ 'sold-out': !course.available }">
    <img :src="course.image" :alt="course.title" />
    <span v-if="!course.available" class="badge">Sold Out</span>
    <h3>{{ course.title }}</h3>
    <p>Chef: {{ course.chef }}</p>
    <p>Level: {{ course.level }}</p>
    <p class="price">R {{ course.price.toLocaleString() }}</p>
    <button
      @click="$emit('save-course', course.id)"
      :disabled="course.saved || !course.available"
    >
      {{ course.saved ? 'Saved ✓' : 'Save' }}
    </button>
  </div>
</template>

<script>
export default {
  props: ['course'],
  emits: ['save-course']
}
</script>