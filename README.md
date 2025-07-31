import random

#update the word list to use the word_list from hangman_word.py
word_list = ["apple", "banana", "cherry", "dog", "elephant", "flower", "guitar", "house", "island", "jungle", "kite", "lemon", "mountain", "notebook", "ocean", "pencil", "queen", "river", "sun", "tree", "umbrella", "violin", "whale", "xylophone", "yogurt", "zebra"]

choosen_word = random.choice(word_list)


placeholder = ""
for position in choosen_word:
    placeholder += "_"
print(placeholder)

correct_letter = []
lives = 6
game_over = False
print("you have ********{lives}*********")
while not game_over:
    
    guess = input("guess the letter in word : ")
    if guess in correct_letter:
        print('you have already guess the letter')
    
    
            
    display = "" #main variable that hold the user value 
    for letter in choosen_word:
        if letter == guess:
            display += letter
            correct_letter.append(guess)
        elif letter in correct_letter:
            display += letter
        else:
            display += "_"
    print(display)

    if guess not in choosen_word:
        lives -= 1
        print(f"you guessed {guess}, that is not in the word, you losse a life")
        print(f"NOW YOU HAVE*********{lives}**********")
        if lives == 0:
            game_over = True
            print(f"YOU LOSE. IT WAS {choosen_word}")
    if "_" not in display:
        game_over = True
        print("YOU WIN")
        
