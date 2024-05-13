import random

class Hangman:
    def __init__(self):
        # Initialize the Hangman game with a list of words, an empty secret word, and other attributes for the guesses that the attempts at guessing given to the user.
        self.words = ["apple", "germany", "giraffe", "computer", "clock", "videogame", "soccer", "yogurt"]
        self.secret_word = ""
        self.guesses = []
        self.incorrect_guesses = 0
        self.max_incorrect_guesses = 7

    def choose_word(self):
        # Choose a random word for the player to guess from the list created.
        self.secret_word = random.choice(self.words)

    def display_word(self):
        # Display the current state of the word being guessed.
        displayed_word = ""
        
        for letter in self.secret_word:
            
            if letter in self.guesses:
                displayed_word += letter
                
            else:
                displayed_word += " _ "
        return displayed_word

    def make_guess(self, letter):
        # Allow the player to guess letters and check if they are correct.
        if letter in self.guesses:
            print("You alreaday guessed that letter.")
            return False
            
        elif letter in self.secret_word:
            self.guesses.append(letter)
            return True
            
        else:
            self.guesses.append(letter)
            self.incorrect_guesses += 1
            return False

# Main function to play the game
def play_hangman():
    game = Hangman()
    game.choose_word()

    while game.incorrect_guesses < game.max_incorrect_guesses:
        print("\nCurrent Word:", game.display_word())

        guess = input("Guess a letter: ").lower()

        if len(guess) != 1 or not guess.isalpha():
            print("Please enter a single letter.")
            continue

        if guess in game.guesses:
            print("You already guessed that letter... Try a different one!")
            print("Remaining tries:", game.max_incorrect_guesses - game.incorrect_guesses)
            continue

        if game.make_guess(guess):
    # Find all occurrences of the guessed letter in the secret word
            positions = [i + 1 for i, letter in enumerate(game.secret_word) if letter == guess]
    # Generate a string representing the positions
            positions_str = " and ".join(str(pos) for pos in positions)
    # Determine the suffix for the last position
            last_suffix = "th" if positions[-1] > 3 else ["st", "nd", "rd"][positions[-1] - 1]
    # Print the message indicating the guessed letter and its positions in the word
            print(f'{guess} is the {positions_str}{last_suffix} letter in the word!')
    
        else:
            print(guess, "is not in the word...")
            print("Remaining tries:", game.max_incorrect_guesses - game.incorrect_guesses)

        if all(letter in game.guesses for letter in game.secret_word):
            print("Congratulations! You guessed the word:", game.secret_word)
            break
        
    if game.incorrect_guesses >= game.max_incorrect_guesses:
        print("You ran out of guesses. The correct word was:", game.secret_word)

if __name__ == "__main__":
    play_hangman()
