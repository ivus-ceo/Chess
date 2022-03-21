<template>
  <div class="figure" :color="color" @click="select">
    <component :is="type" ref="figure"/>
  </div>
</template>

<script>
  import Bishop from './figures/Bishop';
  import King from './figures/King';
  import Knight from './figures/Knight';
  import Pawn from './figures/Pawn';
  import Queen from './figures/Queen';
  import Rook from './figures/Rook';

  export default {
    name: 'Figure',

    props: {
      type: String,
      color: String,
      cells: Array,
    },

    components: {
      'bishop': Bishop,
      'king': King,
      'knight': Knight,
      'pawn': Pawn,
      'Queen': Queen,
      'rook': Rook,
    },

    data() {
      return {
        figure: null,
        cell: null, 
        x: null,
        y: null,
      }
    },

    methods: {
      select(e) {
        this.figure = e.target;
        this.cell = this.figure.closest('.cell');
        this.x = parseInt(this.cell.getAttribute('x'));
        this.y = parseInt(this.cell.getAttribute('y'));

        this.draw();
      },

      draw() {
        this.reset()

        /* Call get moves from another dynamic component */
        const moves = this.$refs.figure.moves(this.cells, this.color, this.x, this.y)

        /* Add events and classes */
        moves.map((move) => {
          move.addEventListener('click', this.move);
          move.classList.add('possible-move')
        })

        this.cell.classList.add('selected');
      },

      reset() {
        /* Remove events and classes */
        this.cells.forEach((cell) => {         
          cell.removeEventListener('click', this.move)
          cell.classList.remove('selected', 'possible-move')
        });
      },

      move(e) {
        this.reset()
        e.target.appendChild(this.figure)
      }
    }
  }
</script>

<style lang="scss">
  div.figure {
    width: 100%;
    height: 100%;
    display: flex;
    font-size: 3rem;
    align-items: center;
    justify-content: center;
    text-shadow: 0 1px 3px rgba(0, 0, 0, .4);

    &[color="white"] {
      color: white;
    }

    &[color="black"] {
      color: black;
    }

    .icon {
      pointer-events: none;
    }
  }
</style>