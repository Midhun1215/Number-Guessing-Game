🚀 Number Guessing Game in Python 🎮
I recently built a fun Number Guessing Game using Python to sharpen my programming skills and practice concepts like functions, loops, conditionals, and user input handling.
🔑 Features of the Game:
--Difficulty Levels: Players can choose between three levels (easy, medium, hard), each with different ranges and number of chances.
--Random Number Generation: The program generates a random number within the chosen range.
--Interactive Feedback: After each guess, the game tells you if your number is too high or too low.
--Replay Option: At the end of each round, players can decide whether to continue or exit.

🧩 What I Practiced:
-Function design and modular coding.
-Using random.randint() for unpredictability.
-Handling user input and validating responses.
-Implementing recursion for replay functionality.

This project was a great way to combine logic building with user interaction design. It’s simple, but it demonstrates how Python can be used to create interactive console-based applications.


Code Is Below:


import random

print("\t \t \t Welcome To the Number guessing game!!! \t \t \t ")

#Asking For The name
name = input("Enter Your Name: ")

#The Code For Running The Number Guessing Game in a Function
def number_guessing():
    #Function for the user to continue with next round or discontinue
    def choices():
        choice = input("Would you like to Try Another Round( yes or no) : ")
        if choice.lower() == "yes":
            print("""
    
                                     Next Round """)
            number_guessing()
        elif choice.lower() == "no":
            print("Thankyou For Playing the 'The Number Guessing Game'")
            exit()
        else:
            print("Invalid Input (Yes or No Only)")
            choices()
    #Function for the difficulty of the Game
    def difficulty():
        global diff , y , z
        diff = input("Enter difficulty level 1, 2, 3 : ")

        if diff == "1":
            y = 30
            z = 5
            print(""" Clue : The Number is Between 1 & 30
                      Important : You Only Have 5 Chances!!!""")
        elif diff == "2":
            y = 60
            z = 8
            print(""" Clue : The Number is Between 1 & 60
                      Important : You Only Have 8 Chances!!!""")
        elif diff == "3":
            y = 100
            z = 10
            print(""" Clue : The Number is Between 1 & 100
                      Important : You Only Have 10 Chances !!! """)
        # Condition For Invalid input   
        else:
                   print("Invalid Input")
                   difficulty()
    difficulty()
#Generating The Number
    x = random.randint(1, int(y))
#Checking If Input is Equal To The Number Generated
    for i in range(z):
        a = int(input("Enter a number : "))
        if a == x :
            print("Congratulations {} !!!! You guessed the Number Correctly".format (name))
            choices()
        elif a > x:
            print("The Number you entered is Too High {}".format(name))
        elif a < x:
            print("The Number You entered is too low {}".format(name))
    print("Your Chances Are Up")

    choices()

number_guessing()
