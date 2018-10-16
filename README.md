// Rock, Paper, Scissors

const readline = require('readline');

const reader = readline.createInterface({
  input: process.stdin,
  output: process.stdout
});
let answers = {
   r: "rock",
   p: "paper",
   s: "scissors"
}

reader.question(`Welcome to rock, paper, scissors. Please type 'r', 'p', or 's' to make a choice.`, (res) => {
  console.log(`You chose: ${answers[res]}. The computer is thinking ...`)

  let cAnswer = Math.floor(Math.random()*3)

  setTimeout(() => {
      if ((cAnswer) === 0) {
        console.log("The computer chose: Rock.")
      } else if ((cAnswer) === 1) {
        console.log("The computer chose: Paper.")
      } else {
        console.log("The computer chose: Scissors.")
        }
  }, 3000)

  setTimeout(() => {
    if (answers[res] === "rock" && cAnswer === 0) {
    console.log (" Tie! Play Again")
  } else if (answers[res] === "rock" && cAnswer === 1) {
    console.log("You lose! Play Again!")
  } else if (answers[res] === "rock" && cAnswer === 2){
    console.log("Congrats! You Won!")
  } else if (answers[res] === "paper" && cAnswer === 1) {
    console.log("Tie! Play Again")
  } else if (answers[res] === "paper" && cAnswer === 2) {
    console.log("You lose! Play Again")
  } else if ( answers[res] === "scissors" && cAnswer == 2) {
    console.log("Tie! PLay Again")
  }
}, 4000)
})
