# BearHumanGunGame

import math
import random

def get_user_choice(user_input):
  user_input = user_input.lower()
  if (user_input == 'bear') or (user_input == 'human') or (user_input == 'gun'):
    return user_input
  else:
    print("error. choose valid thing")

get_user_choice("bear")

def getCompChoice():
  randomNum = math.floor(random.uniform(0,3))
  if randomNum == 0:
    return "bear"
  elif randomNum == 1:
    return "human"
  else:
    return "gun"

def winner(userChoice, compChoice):
  if userChoice == compChoice:
    return "Game was a tie"
    
  if userChoice == "human":
    if compChoice == "bear":
      return "Computer won"
    else:
      return "User won"
      
  if userChoice == "bear":
    if compChoice == "gun":
      return "Computer won"
    else:
      return "User won"
      
  if userChoice == "gun":
    if compChoice == "human":
      return "Computer won"
    else:
      return "User won"
      
def playGame():
  promptUserChoice = input("Please enter bear, human or gun")
  user_choice = get_user_choice(promptUserChoice)
  comp_choice = getCompChoice()
  print("User choice: ", user_choice)
  print("Computer choice: ", comp_choice)
  print(winner(user_choice, comp_choice))
  
playGame()
