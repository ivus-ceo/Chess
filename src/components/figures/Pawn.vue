<template>
  <div class="icon">
    <i class="fas fa-chess-pawn"></i>
  </div>
</template>

<script>
  export default {
    name: 'Pawn',

    methods: {
      moves(cells, color, x, y) {
        console.log('Pawn');
        
        /* White color figures */
        if (color === 'white') {
          cells = cells.filter((cell) => {
            const cellX = parseInt(cell.getAttribute('x'))
            const cellY = parseInt(cell.getAttribute('y'))

            const movesY = cellY >= y - 2 && cellY < y;
            const movesX = cellX === x;

            let asdasdasdasdsadasd
            
            if (cell.firstElementChild !== null && cell.firstElementChild.attributes.color.value === 'black') {
              asdasdasdasdsadasd = cellX === x - 1;
            }
            
            if (movesX && movesY) return cell
          });
        }

        /* Black color figures */
        if (color === 'black') {          
          cells = cells.filter((cell) => {
            const cellX = parseInt(cell.getAttribute('x'))
            const cellY = parseInt(cell.getAttribute('y'))

            const movesY = cellY <= y + 2 && cellY > y;
            const movesX = cellX === x;
            
            if (movesX && movesY) return cell
          });
        }

        /* Return possible moves */
        return cells;
      },
    },
  }
</script>