# Campo-Minado-JS
meu primeiro projeto
<!DOCTYPE html>
<html lang="pt">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  
  <style>

  </style>
  <title>Campo Minado</title>
</head>
<body>
  <div class="game-container">
    <h1>Campo Minado</h1>
    <div class="game-board">

    </div>
    <button class="reset-button" onclick="resetGame()">Reiniciar Partida</button>
  </div>
  <script>

  </script>
  <style>


body {
  font-family: Arial, sans-serif;
  text-align: center;
  background-color: #333;
  color: white;
  margin: 0;
  padding: 0;
}

.game-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.game-board {
  display: grid;
  grid-template-columns: repeat(8, 40px);
  gap: 2px;
  margin-top: 20px;
}

.cell {
  width: 40px;
  height: 40px;
  border: 1px solid #444;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 18px;
  cursor: pointer;
  background-color: #666;
  transition: background-color 0.2s;
}

.cell.clicked {
  cursor: default;
  background-color: #333;
}

.cell.safe {
  background-color: #aaa;
  color: #333;
}

.cell.explode {
  background-color: #ff7f7f;
  color: white;
}

.reset-button {
  margin-top: 20px;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  background-color: #444;
  color: white;
  border: none;
  border-radius: 5px;
  transition: background-color 0.2s;
}

.reset-button:hover {
  background-color: #555;
}



</style>
  <title>Campo Minado</title>
</head>
<body>
  <div class="game-container">
    <h1>Campo Minado</h1>
    <div class="game-board">

    </div>
    <button class="reset-button" onclick="distributeMines(), createBoard()">Reiniciar Partida</button>
  </div>
  <script>

  </script>

<!DOCTYPE html>
<html lang="pt">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>


body {
  font-family: Arial, sans-serif;
  text-align: center;
  background-color: #333;
  color: white;
  margin: 0;
  padding: 0;
}

.game-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.game-board {
  display: grid;
  grid-template-columns: repeat(8, 40px);
  gap: 2px;
  margin-top: 20px;
}

.cell {
  width: 40px;
  height: 40px;
  border: 1px solid #444;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 18px;
  cursor: pointer;
  background-color: #666;
  transition: background-color 0.2s;
}

.cell.clicked {
  cursor: default;
  background-color: #ff00008c;
}

.cell.safe {
  background-color: #aaa;
  color: #333;
}

.cell.explode {
  background-color: #ff7f7f;
  color: white;
}

.reset-button {
  margin-top: 20px;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  background-color: #444;
  color: white;
  border: none;
  border-radius: 5px;
  transition: background-color 0.2s;
}

.reset-button:hover {
  background-color: #555;
}



</style>
<title>Campo Minado</title>
</head>
<body>
<div class="game-container">
<h1>Campo Minado</h1>
<div class="game-board">

  
</div>
<button class="reset-button" onclick="createBoard(), distributeMines()">Reiniciar Partida</button>
</div>

<script>
document.addEventListener("DOMContentLoaded", () => {

});
</script>
</body>
</html>

  </style>
  <title>Campo Minado</title>
</head>
<body>
  <div class="game-container">
    <h1>Campo Minado</h1>
    <div class="game-board">

    </div>
    <button class="reset-button" onclick="resetGame()">Reiniciar Partida</button>
    
  </div>
  <script>

  </script>

    <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
    }

    .game-board {
      display: grid;
      grid-template-columns: repeat(8, 40px);
      gap: 2px;
      margin-top: 20px;
    }

    .cell {
      width: 40px;
      height: 40px;
      border: 1px solid #eeeeee36;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 18px;
      cursor: pointer;




    .cell.safe {
      background-color: #aaa;
      color: #333;
    }


    .cell.explode {
      background-color: #ff7f7f;
      color: white;
    }
  </style>
  <title>Campo Minado</title>
</head>
<body>
  <h1>Campo Minado</h1>
  <div class="game-board">

  </div>
  <script>
    document.addEventListener("DOMContentLoaded", () => {
      const board = document.querySelector(".game-board");
      const rows = 8;
      const cols = 8;
      const totalMines = 10;

      // Função para gerar um número aleatório entre min e max
      const getRandomNumber = (min, max) => Math.floor(Math.random() * (max - min + 1)) + min;

      // Função para criar o tabuleiro
      const createBoard = () => {
        for (let row = 0; row < rows; row++) {
          for (let col = 0; col < cols; col++) {
            const cell = document.createElement("div");
            cell.classList.add("cell");
            board.appendChild(cell);
          }
        }
      };

      createBoard();

      const cells = document.querySelectorAll(".cell");


      const distributeMines = () => {
        const mineIndices = [];
        while (mineIndices.length < totalMines) {
          const randomIndex = getRandomNumber(0, rows * cols - 1);
          if (!mineIndices.includes(randomIndex)) {
            mineIndices.push(randomIndex);
            cells[randomIndex].classList.add("mine");
          }
        }
      };

      distributeMines();


      cells.forEach((cell, index) => {
        cell.addEventListener("click", () => {
          if (cell.classList.contains("mine")) {
            cell.classList.add("explode");
            revealMines();
            alert("BOOM! Você acertou uma mina!");
          } else {
            const row = Math.floor(index / cols);
            const col = index % cols;
            const numberOfMines = countMinesAround(row, col);

            cell.classList.add("clicked", "safe");
            cell.textContent = numberOfMines === 0 ? "" : numberOfMines;
          }
        });
      });


      const countMinesAround = (row, col) => {
        let count = 0;
        for (let r = Math.max(0, row - 1); r <= Math.min(rows - 1, row + 1); r++) {
          for (let c = Math.max(0, col - 1); c <= Math.min(cols - 1, col + 1); c++) {
            if (r !== row || c !== col) {
              if (cells[r * cols + c].classList.contains("mine")) {
                count++;
              }
            }
          }
        }
        return count;
      };

      const revealMines = () => {
        cells.forEach(cell => {
          if (cell.classList.contains("mine")) {
            cell.classList.add("clicked");
          }
        });
      };
    });
    
  </script>

</body>
</html>



