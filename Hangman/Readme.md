"""
2/12/2022


Concepts to keep in mind:

    Random
    Variables
    Boolean
    Input and Output
    Integer
    Char
    String
    Length
    Print

Importantly!

Despite the name, the actual “hangman” part isn’t necessary. 
The main goal here is to create a sort of “guess the word” game. The 
user needs to be able to input letter guesses. A limit should also 
be set on how many guesses they can use. This means you’ll need a 
way to grab a word to use for guessing. (This can be grabbed from 
a pre-made list. No need to get too fancy.) You will also need functions
to check if the user has actually inputted a single letter, to 
check if the inputted letter is in the hidden word (and if it is, 
how many times it appears), to print letters, and a counter variable 
to limit guesses.

"""

import random



def check_guess(letter):
	for ind,x in enumerate(ran_word):
		if x == letter:
			dsp_word[ind] = letter


while True:

	print("\n" *30)

	words = ["jazz", "buzz", "jazzed", "jinx", "runaway"]
	random.shuffle(words)
	ran_word = words.pop()

	dsp_word = ["_"]*len(ran_word)
	wrg_str = ""
	count = 0
	playing = True

	print("\tWelcome to Hangman!")
	print("\tYour word is {} letters long! and you have 7 tries to figure it out!".format(len(ran_word)))

	while count < 7 or playing == False:
		print("\n")
		print("\t {}".format(" ".join(dsp_word)))
		print("\n")

		print("\tThings you've guessed wrong: {}".format(wrg_str))
		guess = input("What's your guess?  ")

		if len(guess) == 1:
			if guess in ran_word:
				check_guess(guess)
				if "".join(dsp_word) == ran_word:
					print("\tYou've won!")
					print("\tThe word is {}!".format(ran_word))
					break
				continue
			else:
				print("\tYou'll have to try again if you want to win.")
				wrg_str += " {} ".format(guess)
				count += 1
				print("\tYour count is now at {}!".format(count))
		else:
			if guess == ran_word:
				print("\tYou've won!")
				print("\tThe word is {}!".format(ran_word))
				break
			else:
				print("\tNot even close, bby!")
				wrg_str += " {} ".format(guess)
				count += 1

				print("\tYour count is now at {}!".format(count))

	if count == 7:
		print("\tWow.. Of course you lost.")
		print("\tThe word is {}!".format(ran_word))

	replay = input("Would you like to play again? y/n:")

	if replay.lower() == "y":
		print("\tNice, let's do it.")
		continue
	else:
		print("\tWhatever.")
		break
		
		####################### OUTPUT #########################################
# play two time only see below







	Welcome to Hangman!
	Your word is 4 letters long! and you have 7 tries to figure it out!


	 _ _ _ _


	Things you've guessed wrong: 

What's your guess?  b


	 b _ _ _


	Things you've guessed wrong: 

What's your guess?  k
	You'll have to try again if you want to win.
	Your count is now at 1!


	 b _ _ _


	Things you've guessed wrong:  k 

What's your guess?  z


	 b _ z z


	Things you've guessed wrong:  k 

What's your guess?  u
	You've won!
	The word is buzz!

Would you like to play again? y/n:y
	Nice, let's do it.







	Welcome to Hangman!
	Your word is 4 letters long! and you have 7 tries to figure it out!


	 _ _ _ _


	Things you've guessed wrong: 

What's your guess?  h
	You'll have to try again if you want to win.
	Your count is now at 1!


	 _ _ _ _


	Things you've guessed wrong:  h 

What's your guess?  a


	 _ a _ _


	Things you've guessed wrong:  h 

What's your guess?  b
	You'll have to try again if you want to win.
	Your count is now at 2!


	 _ a _ _


	Things you've guessed wrong:  h  b 

What's your guess?  l
	You'll have to try again if you want to win.
	Your count is now at 3!


	 _ a _ _


	Things you've guessed wrong:  h  b  l 

What's your guess?  u
	You'll have to try again if you want to win.
	Your count is now at 4!


	 _ a _ _


	Things you've guessed wrong:  h  b  l  u 

What's your guess?  e
	You'll have to try again if you want to win.
	Your count is now at 5!


	 _ a _ _


	Things you've guessed wrong:  h  b  l  u  e 

What's your guess?  x
	You'll have to try again if you want to win.
	Your count is now at 6!


	 _ a _ _


	Things you've guessed wrong:  h  b  l  u  e  x 

What's your guess?  n
	You'll have to try again if you want to win.
	Your count is now at 7!
	Wow.. Of course you lost.
	The word is jazz!

Would you like to play again? y/n:n
	Whatever.
