## Requirement

- Size of the board : n * n
- No of players: n-1
- Symbol choosing 
- any bot ?
- only one bot per game.
- randomize player playing.
- decide winner -> when row/col/diagonal of one player symbol full.
- end game if no more moves and no winner.
- replay feature with stack.

## Class Diagram

```java

class Game{
  Board board;
  List<Player> players;
  int nextPlayerMove;
  boolean winner;
  GameState state;
}

class Move {
  Cell cell;
  Player player;
}

enum GameState {
  INPROGRESS,
  ENDED,
  DRAW
}

class Board{
  int size;
  List<List<Cell>> board;
  int players;
  boolean bot;
}

class Cell {
  int row;
  int col;
  Player whoseMove;
  CellState state;
}

enum CellState {
  EMPTY,
  FILLED,
  BLOCKED
}
class Player{
  int id;
  Symbol symbol;
  boolean isWinner;
  PlayerType type;
}

enum PlayerType {
  HUMAN,
  BOT
}

class Symbol{
  char sym;
}

class Bot extends Player {
  Difficulty level;
}

enum Difficulty {
  EASY,
  MEDIUM,
  HARD,
  EXTREME
}
```

## Implementation

