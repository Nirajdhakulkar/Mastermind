# Mastermind
import random 
import time

OPERATORS = ["+","-","*"]
MIN_OPERAND = 1
MAX_OPERAND = 15



def problem():
    left = random.randint(MIN_OPERAND,MAX_OPERAND)
    right = random.randint(MIN_OPERAND,MAX_OPERAND)
    operator = random.choice(OPERATORS)

    expr = str(left) + " " + operator + " " + str(right)
    ans = eval(expr)
    return expr,ans

def practice(N):

    TOTAL_PROB = N

    input("Press enter to dive into the game...")
    print("")
    starttime = time.time()

    for i in range(TOTAL_PROB):

        
        expr, ans = problem()
        while True :
            guess = input ("problem #"+str(i+1)+" "+":"+" "+expr+" "+"= :")
            if guess == str(ans):
                break

    endtime = time.time()
    totaltime = endtime - starttime
    return totaltime

print("\tWelcome to Mastermind!!")
print("Let's check your calculation speed!!!")
print("\tchoose an option :")
print("\t1 practice")
print("\t2 play game")
ch = int(input())

while ch != 3:

    if ch == 1:
        TOTAL_PROB = int(input("Enter total no. of problems :"))
        time = practice(TOTAL_PROB)
        print("Your total time is :",time,".....Keep practising you can be more fast!")
        break
    elif ch == 2:
        TOTAL_PROB = int(input("Enter total no. of problems :"))
        name1 = input("Enter the name of player 1 :")
        print(name1,"'s chance ")
        player1time = practice(TOTAL_PROB)
        print(name1,"'s score is :",player1time,"seconds.")

        name2 = input("Enter the name of player 2 :")
        print(name2,"'s chance ")
        player2time = practice(TOTAL_PROB)
        print(name2,"'s score is :",player2time,"seconds.")

        if player1time > player2time:
            print(name2," is the real mastermind!! ")
        else :
            print(name1," is the real mastermind!! ")
        break
    else :
        break
