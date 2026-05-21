# CodeAlpha_Tasks
import random

words_to_guess = ["intrenship" , "coding" , "hackathon" , "projects" , "skills" , "learning"]

words = random.choice(words_to_guess)

guessed_letters = []
wrong_guesses = 0
max_wrong_guesses = 6
correct_guesses = 0

diaplay_word = []

for letter in words:
    diaplay_word.append("_")

print("Welcome to the Hangman Game!")

while wrong_guesses < max_wrong_guesses and "_" in diaplay_word:
    print("\nCurrent word: " + " ".join(diaplay_word))
    print("Guessed letters: " + ", ".join(guessed_letters))
    print(f"Wrong guesses: {wrong_guesses}/{max_wrong_guesses}")

    guess = input("Guess a letter: ").lower()

    if guess in guessed_letters:
        print("You already guessed that letter. Try again.")
        continue

    guessed_letters.append(guess)

    if guess in words:
        for index, letter in enumerate(words):
            if letter == guess:
                diaplay_word[index] = guess
        print("Correct!")
        correct_guesses += 1
    else:
        wrong_guesses += 1
        print("Wrong!")
        print("Hint: The word contains the letter '" + guess + "'.")
        print("Hint: The word is related to btech students.")
if "_" not in diaplay_word:
    print("\nCongratulations! You guessed the word: " + words)
    print("You won!")
else:
    print("\nGame Over! The word was: " + words)
    print("Better luck next time!") 