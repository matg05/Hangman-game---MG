This is code allows you to play a game of hangman. You start out with 7 attempts at guessing letter for a randomly generated word within a list. The code will output The number of letters in the word,
and it will prompt you to enter a letter of your choice. Then, the program will either 

a) print the letter you entered, followed by "is the #st, #nd, #rd, #th letter in the word!" if it's in the random word.
b) print the letter you entered, followd by "is not in the word..." and you will loose 1 attempt at guessing if it's not in the random word.
c) print "You already guessed that letter... Try a different one!" if you input a character that you already tried.
d) print "Please enter a single letter." if you entered more than one letter at a time (if a number is entered, it will just prompt you to enter a letter).

If the 7 attempts given are depleted, the program will print "You ran out of guesses. The correct word was: *word*" and the code will stop running.

If the user manages to guess the word before their guesses run out, the code will print "Congratulations! You guessed the word: yogurt". and the code will stop running.
