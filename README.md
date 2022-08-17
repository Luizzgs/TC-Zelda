# TC-Zelda

</br>
<img width="788" alt="Screen Shot 2020-03-30 at 10 17 57 PM" src="https://raw.githubusercontent.com/Luizzgs/TC-Zelda/main/images/Zelda_Preview.png">

## Tópicos
1. [Introdução](#Introdução)
2. [Linguagens](#Linguagens)
3. [Features](#features)
5. [Future Direction](#future-direction)

## Introdução

Zelda-js is a raw javascript concept based on the classic NES title The Legend of Zelda.  This project includes the original's overworld, movement logic, basic enemies, minimap, and health system. Cave and underground areas are not currently accessable.

## Linguagens

**Javascript** <br/> 
Feito em Javascript puro sem qualquer dependencia, utiliza sprites para definir o mundo e o jogador.

## Features
* Full UI - Players can utilize a functional minimap, inventory, and lifebar. <img width="759" alt="Screen Shot 2020-03-30 at 10 28 42 PM" src="https://user-images.githubusercontent.com/47997709/77990306-d5df4080-72d5-11ea-84af-56d10f4e5d1d.png">
<br/> 

* Full overworld - entirety of the original game's overworld is present and explorable in this demo. Zelda-JS maps are scanned to contruct the game's 'board' and inform collision.<img width="1038" alt="splitmap" src="https://user-images.githubusercontent.com/47997709/77993527-2dcd7580-72dd-11ea-9916-48c3121c1910.png">
    ``` javascript
      # game.js
      scanGrid(ctx) {
        let newGrid = [];
        let openSpaces = [];
        for (let y = 168; y < 696; y += 48) {
          let row = [];
          for (let x = 0; x < 768; x += 48) {
            let value = Util.scanMapTile(ctx, x, y);
            row.push(value);
            if (value === 1020) openSpaces.push([x, y]);
          }
          newGrid.push(row);
        }
        this.openSpaces = openSpaces;
        this.grid = newGrid;
      }

      # util.js
      export function scanMapTile(ctx, x, y) {
      const tile = ctx.getImageData(x+23, y+23, 2, 2);
      return sumArr(tile.data)
      }
    ```

* Attackable enemies - Enemies have a random-acting AI and can be fought by the player. <img width="780" alt="Screen Shot 2020-03-30 at 10 40 11 PM" src="https://user-images.githubusercontent.com/47997709/77990950-7aae4d80-72d7-11ea-83de-a0a42cd01309.png">
    ``` javascript
    updateAction() {
        let possibleActions = this.checkAvailableActions();
        this.frameData.action = 48;
        let action = util.sample(possibleActions);
        this.frameData.direction = action[0];
        this.pos.col += action[1];
        this.pos.row += action[2];
      }
    ```
## Future Direction
* Collectable Items
* Additional enemy types
* Underground Areas
