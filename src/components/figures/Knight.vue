<template>
  <div class="icon">
    <i class="fas fa-chess-knight"></i>
  </div>
</template>

<script>
  export default {
    name: 'Knight',

    methods: {
      getMoves(color, x, y) {
        console.log('Knight');
      },
    },
  }
</script>