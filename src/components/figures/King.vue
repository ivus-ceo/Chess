<template>
  <div class="icon">
    <i class="fas fa-chess-king"></i>
  </div>
</template>

<script>
  export default {
    name: 'King',

    methods: {
      getMoves(color, x, y) {
        console.log('King');
      },
    },
  }
</script>