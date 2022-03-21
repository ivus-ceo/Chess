<template>
  <div class="icon">
    <i class="fas fa-chess-bishop"></i>
  </div>
</template>

<script>
  export default {
    name: 'Bishop',

    methods: {
      getMoves(color, x, y) {
        console.log('Bishop');
      },
    },
  }
</script>