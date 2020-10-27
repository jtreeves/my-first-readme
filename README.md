# My first README

My repo explaining how to use README.

```javascript
const handleWin = (letter) => {
  gameIsLive = false;
  if (letter === "x") {
    statusDiv.innerHTML = `${letterToSymbol(letter)} has won!`;
  } else {
    statusDiv.innerHTML = `<span>${letterToSymbol(letter)} has won!</span>`;
  }
};
```

```css
.grid {
    background-color: salmon;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, 1fr);
    gap: 15px;
    margin-top: 50px;
}
```

```html
<div class="grid">
    <div class="box" id="box-1"></div>
    <div class="box" id="box-2"></div>
    <div class="box" id="box-3"></div>
    <div class="box" id="box-4"></div>
    <div class="box" id="box-5"></div>
    <div class="box" id="box-6"></div>
    <div class="box" id="box-7"></div>
    <div class="box" id="box-8"></div>
    <div class="box" id="box-9"></div>
</div>
```

| Functions             | Description |
| ---                   | --- |
| `handleWin()`         | Handle the win of either player |
| `checkGameStatus()`   | Check the status after each turn |

I think I should have just used querySelectorAll('.cell) to change the cells to X's instead of doing them individually. I also think I could have used the fact that querySelectorAll returns an array to access each cell in the array using bracket notation. That way, the Math.floor(Math.random()*9) could have accessed each cell one at a time using its index. I was planning to have the Math.floor(Math.random()*9) play the computer's side of the game, which is why I initially built all the cells to change to just X's when clicked on them, since I wanted to have the cells only change to O's when the computer played its turn. I wanted to use the setTimeout to delay the computer's move by one second. I also wasn't sure how to use the grid property of CSS to make each of the cells the same size (I tried various grid-template options to no avail). Or to put borders around them. (After using grid-area, it wouldn't let me set a grid-gap, but even then, I don't think that would have helped with a border.)

I honestly did not anticipate how long this assignment was going to take, but this failure is a good learning experience. I definitely need to manage my time better in the future!

This HTML code creates the grid that will contain the elements of the board:
```html
<div class="grid">
    <div class="cell" id="r1c1">r1c1</div>
    <div class="cell" id="r1c2">r1c2</div>
    <div class="cell" id="r1c3">r1c3</div>
    <div class="cell" id="r2c1">r2c1</div>
    <div class="cell" id="r2c2">r2c2</div>
    <div class="cell" id="r2c3">r2c3</div>
    <div class="cell" id="r3c1">r3c1</div>
    <div class="cell" id="r3c2">r3c2</div>
    <div class="cell" id="r3c3">r3c1</div>
</div>
```

This CSS code creates the template for the grid and assigns an id to a particular part of the template:
```css
.grid {
  display: grid;
  grid-template: "r1c1 r1c2 r1c3"
                "r2c1 r2c2 r2c3"
                "r3c1 r3c2 r3c3";
}

#r1c1 {
  grid-area: r1c1;
}
```

This JavaScript code replaces the existing text of a cell with an 'X' after the user clicks on that cell:
```javascript
document.querySelector('#r1c1').addEventListener('click', function() {
    document.querySelector('#r1c1').innerText = 'X';
});
```