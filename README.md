# Hangman
name = input("What is your name?: ")
print("Welcome to Hangman, " + name + " let's play!")
#Choosing a random word
import random
from words import words
#factoring out invalid words
if words != "-" or " ": word = (random.choice(words))
print(word)
#printing each letter of that random word with an underscore.
underscore = "_ " * len(word)
print(underscore)
 
#Word_bank
guess = input("Guess a letter or word here: ")
guessed_letters = [""]
guessed_words = [""]
guessed = False
#game == tries > 0
#game == True
tries = int(7)
indicies = [i for i, letter in enumerate(word) if letter == guess ]
letter = ("""a, b, c, d, e, f, g, h, i, j, k, l, m, n, o, p, q, r, s, t, u, v, w, y, x, z""")
attempts = guess != word
attempts = 7
#printing "Guess a letter or word here:" the number of tries we have
 
for i in range(1, 7):
    print('     ----------')
    print('     |        |')
    print('     |        ' + ('O' if tries > 1 else ''))
    print('     |        ' + ('|' if tries > 2 else ''))
    print('     |       ' +('\ / ' if tries > 3 else ''))
    print('     |        ' + ('|' if tries > 4 else ''))
    print('     |       ' +('/ \\' if tries > 5 else ''))
    print('     |      ' +('-   -' if tries > 6 else ''))
    print('     |        ' + ('*' if tries > 7 else ''))
    print(' -------------')
    print (underscore)
    #Checking for each guessed letter

#for guess in range(1, 7):
#  print(input("Guess a letter or word here: "))
#for attempts in range(1, 7):
while tries > 0:
  if guess in word:
    guessed_letters.append(guess)
    word_as_list = list(underscore)
    print("Correct! " + guess + " is in the word!")
    print (input("Guess a letter or word here: "))
  elif guessed_letters == guess:
    print("You have already guessed this letter " + guess)
    print(guessed_letters)
    print(tries) 
  else:
    print("Sorry. " + guess + " is not in the word")
    tries -= 1
 
while len(guess) > 1:
  if guess == guessed_words:
    print("Sorry, you already gessed this word", guess)
    print(tries)
  elif guess != word:
      print(guess + " is not the word.")
      tries -= 1
      guessed_words.append(guess)
      print(tries)
  elif guess == word:
      guessed = True
      underscore = word
      print("Yay!!! You guessed the word!  Whoo-hoo! ")
 
for i in range(1, 7):
  play = input("Would you like to play again? ")
  if play == "Yes":
    continue
  if play == "No":
    print("Thanks for playing, " + name + " ! Hope to see you again!!")
  break
