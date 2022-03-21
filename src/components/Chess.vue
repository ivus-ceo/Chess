<template>
  <div class="chess-container">
    <!-- Start 1 row -->
    <div class="row">
      <Cell>
        <Figure type="rook" color="black" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="knight" color="black" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="bishop" color="black" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="queen" color="black" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="king" color="black" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="bishop" color="black" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="knight" color="black" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="rook" color="black" :cells="cells"/>
      </Cell>
    </div>
    <!-- End 1 row -->

    <!-- Start 2 row -->
    <div class="row">
      <Cell>
        <Figure type="pawn" color="black" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="pawn" color="black" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="pawn" color="black" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="pawn" color="black" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="pawn" color="black" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="pawn" color="black" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="pawn" color="black" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="pawn" color="black" :cells="cells"/>
      </Cell>
    </div>
    <!-- End 2 row -->

    <!-- Start 3 row -->
    <div class="row">
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
    </div>
    <!-- End 3 row -->

    <!-- Start 4 row -->
    <div class="row">
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell>
        <Figure type="pawn" color="black" :cells="cells"/>
      </Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
    </div>
    <!-- End 4 row -->

    <!-- Start 5 row -->
    <div class="row">
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell>
        <Figure type="pawn" color="white" :cells="cells"/>
      </Cell>
      <Cell></Cell>
      <Cell></Cell>
    </div>
    <!-- End 5 row -->

    <!-- Start 6 row -->
    <div class="row">
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
      <Cell></Cell>
    </div>
    <!-- End 6 row -->

    <!-- Start 7 row -->
    <div class="row">
      <Cell>
        <Figure type="pawn" color="white" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="pawn" color="white" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="pawn" color="white" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="pawn" color="white" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="pawn" color="white" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="pawn" color="white" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="pawn" color="white" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="pawn" color="white" :cells="cells"/>
      </Cell>
    </div>
    <!-- End 7 row -->

    <!-- Start 8 row -->
    <div class="row">
      <Cell>
        <Figure type="rook" color="white" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="knight" color="white" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="bishop" color="white" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="queen" color="white" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="king" color="white" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="bishop" color="white" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="knight" color="white" :cells="cells"/>
      </Cell>
      <Cell>
        <Figure type="rook" color="white" :cells="cells"/>
      </Cell>
    </div>
    <!-- End 8 row -->
  </div>
</template>

<script>
  import Cell from './Cell';
  import Figure from './Figure';

  export default {
    name: 'Chess',

    data() {
      return {
        cells: []
      }
    },

    components: {
      Cell, 
      Figure
    },

    methods: {
      
    },

    mounted() {
      const rows = document.querySelectorAll('.row');

      rows.forEach((row, i) => {
        const cells = row.querySelectorAll('.cell');

        cells.forEach((cell, j) => {
          cell.setAttribute('x', j)
          cell.setAttribute('y', i)
          this.cells.push(cell);
        });
      })
    },
  }
</script>

<style lang="scss">
  .chess-container {
    width: 100%;
    height: 100%;
    display: flex;
    max-width: 600px;
    max-height: 600px;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    background-color: white;

    div.row {
      display: flex;
      width: 100%;
      height: calc(100% / 8);

      &:nth-child(odd) {
        background-color: #2f3542;

        div.cell:nth-child(odd) {
          background-color: #dfe4ea;
        }
      }

      &:nth-child(even) {
        background-color: #2f3542;

        div.cell:nth-child(even) {
          background-color: #dfe4ea;
        }
      }
      
      div.cell {
        height: 100%;
        width: calc(100% / 8);
      }
    }
  }
</style>