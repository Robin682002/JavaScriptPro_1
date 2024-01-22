# JavaScriptPro_1
guessing game using java script


const readline = require('readline').createInterface({
  input: process.stdin,
  output: process.stdout
});

const randomNumber = Math.floor(Math.random() * 10) + 1;
let guessCount = 0;

readline.question('Guess a number between 1 and 10: ', (guess) => {
  guessCount++;

  if (guess < randomNumber) {
    console.log('Too low!');
    promptForGuess();
  } else if (guess > randomNumber) {
    console.log('Too high!');
    promptForGuess();
  } else {
    console.log(`Congratulations! You guessed the number in ${guessCount} tries!`);
    readline.close();
  }
});

function promptForGuess() {
  readline.question('Guess again: ', (guess) => {
    guessCount++;
    if (guess < randomNumber) {
      console.log('Too low!');
      promptForGuess();
    } else if (guess > randomNumber) {
      console.log('Too high!');
      promptForGuess();
    } else {
      console.log(`Congratulations! You guessed the number in ${guessCount} tries!`);
      readline.close();
    }
  });
}
