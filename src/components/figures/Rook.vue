<template>
  <div class="icon">
    <i class="fas fa-chess-rook"></i>
  </div>
</template>

<script>
  export default {
    name: 'Rook',

    methods: {
      getMoves(color, x, y) {
        console.log('Rook');
      },
    },
  }
</script>