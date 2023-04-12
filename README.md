import random


# function and hints
def hangman():
    print("Hello,welkome to the game")
    # winin words
    wordlist = ['pizza', 'sushi','family','home']
    secret = random.choice(wordlist)
    guesses = 'a,e,i,o,u'
    turns = 5

    while turns > 0:
        missed = 0
        for letter in secret:
            if letter in guesses:
                print(letter,end='')
            else:
                print('_', end=' ')
                missed += 1
        # you are win if no missing 0
        if missed == 0:
            print('\nYou are win!')
            break

        guess = input(' \nWrite the letter: ')
        guesses += guess

        # accii art for hang man for each mistake
        if guess not in secret:
            turns -= 1
            print("You are wrong")
            print('\n', 'You can try more:', turns)
            if turns < 5: print('\n -|')
            if turns < 4: print('  o ')
            if turns < 3: print(' /|\ ')
            if turns < 2: print('  | ')
            if turns < 1: print(' / \ ')
            if turns < 0: print('\n\nThis word: ', secret)


# Are you want to play again?
ans = 'Yes'
while ans == 'Yes':
    hangman()
    print("Are you want to play again?(yes or no)")
    ans = input()
    continue
