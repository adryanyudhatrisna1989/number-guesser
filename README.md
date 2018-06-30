# Number Guesser Application

### User can enter random number between 1 - 10, and will have 3 tries before losing the game

### Example code

```javascript
 // Check if won
  if (guess === winningNum) {
    // Game over - won
    gameOver(true, `${winningNum} is correct, YOU WIN!`);

  } else {
    // Wrong number
    guessesLeft -= 1;

    if (guessesLeft === 0) {
      // Game over - lost
      gameOver(false, `Game Over, you lost. The correct number was ${winningNum}`);
    } else {
      // Game continues - answer wrong

      // Change border color
      guessInput.style.borderColor = 'red';

      // Clear Input
      guessInput.value = '';

      // Tell user its the wrong number
      setMessage(`${guess} is not correct, ${guessesLeft} guesses left`, 'red');
    }
  }
});

// Game over
function gameOver(won, msg) {
  let color;
  won === true ? color = 'green' : color = 'red';

  // Disable input
  guessInput.disabled = true;
  // Change border color
  guessInput.style.borderColor = color;
  // Set text color
  message.style.color = color;
  // Set message
  setMessage(msg);

  //Play again?
  guessBtn.value = 'Play again'
  guessBtn.className += 'play-again'
}
```
