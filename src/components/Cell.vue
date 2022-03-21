<template>
  <div class="cell">
    <slot/>
  </div>
</template>

<style lang="scss">
  div.cell {
    &.selected {
      background-color: #7bed9f !important;
    }

    &.possible-move {
      background-color: #7bed9f !important;
    }
  }
</style>