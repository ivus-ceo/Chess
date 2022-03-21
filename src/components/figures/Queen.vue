<template>
  <div class="icon">
    <i class="fas fa-chess-queen"></i>
  </div>
</template>

<script>
  export default {
    name: 'Queen',

    methods: {
      getMoves(color, x, y) {
        console.log('Queen');
      },
    },
  }
</script>