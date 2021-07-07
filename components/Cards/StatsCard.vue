<template>
  <div class="card-wrapper">
    <!-- Header -->
    <slot name="stats-header"></slot>
    <!-- Header End -->
    <!-- Footer -->
    <slot name="footer"></slot>
    <!-- Footer End -->
  </div>
</template>

<script>
export default {
  name: "StatsCard"
};
</script>

<style scoped>
.card-wrapper {
  height: 200px;
  width: 25vw;
  padding: 1rem;
  display: flex;
}

@media screen and (max-width: 1200px) {
  .card {
    width: 50vw;
  }
}

@media screen and (max-width: 768px) {
  .card {
    width: 100vw;
  }
}
</style>
