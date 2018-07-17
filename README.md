# Simple-Calculator-App
A Python Calculator app that asks which operation you want to perform, then accepts two numbers, then performs the operation.

    def welcome_user():
        '''welcomes user with a cool banner'''

        banner = "*"
        welcome = "Welcome to the simple calculator!"

        print("\t\t",banner, banner * len(welcome), banner)
        print("\t\t",banner, welcome, banner)
        print("\t\t",banner, banner * len(welcome), banner)

    def calculator():
        '''checks which type of operation user wants,
            gets number input, returns answer'''

        question = input("\nDo you want to add, subtract, multiply, or divide?: ").lower() #converts to lowercase
        while question not in ('add', 'subtract', 'multiply', 'divide'): #while question is not a valid choice
            print("Choose a valid option...")
            question = input("\nDo you want to add, subtract, multiply, or divide?: ").lower() #ask again

        num1 = None
        while num1 is None:
            try:
                num1 = float(input("What's number 1?: ")) #accepts first number
            except ValueError:
                print("Enter a number...")

        num2 = None
        while num2 is None:
            try:
                num2 = float(input("What's number 2?: ")) #accepts second number
            except ValueError:
                print("Enter a number...")

        #checks which operation user wants, then performs, stores, prints the operation
        if question == 'add':
            answer = num1 + num2
            print("\n",num1, "+", num2, "=", answer)
        elif question == 'subtract':
            answer = num1 - num2
            print("\n",num1, "-", num2, "=", answer)
        elif question == 'multiply':
            answer = num1 * num2
            print("\n",num1, "*", num2, "=", answer)
        elif question == 'divide':
            while num2 == 0: #while user enters zero for second number
                print("Can't divide by zero...")
                num2 = float(input("What's number 2?: ")) #ask again for second number
            answer = num1 / num2 #if num2 is not 0, then perform, store, print operation
            print("\n",num1, "/", num2, "=", answer)
        else: #if user doesn't choose valid choice
            print("Choose a valid option...")

        return answer #return the answer to the program
    
    def main():
        '''main loop'''

        welcome_user() #calls welcome_user()

        answer = calculator() #call calculator() in 'answer' variable

        again = " " #empty string variable

        while again != "no".lower(): #while again is not no

            again = input("\nDo you want to go again?: (yes or no) ").lower() #ask to go again
            if again == "yes".lower(): #if input is yes
                answer = calculator() #call calculator() again

        print("\nGoodbye.") #if no, breaks out of loop, prints goodbye

    main() #call main loop

    input("\n\nPress enter to exit")






    
    

