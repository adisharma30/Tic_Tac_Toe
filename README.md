# Tic_Tac_Toe


Hi Everyone,

I have created this Tic_Tac_toe game using python by sys and Ipython.Display modules.
This is souly user interactive game while allowing two different players to play the game from the same console.
I have created four core functions in the program:-

Create_Board() - Create_Board() function basically prints the board on your console everytime you enter your choice on the board.
Player_input() - Player_input() function makes you select two choices from the ingame markers ie:-'X' and 'O'
Position_select()- Position_select function enables you to select the position on the board where you want to place the marker
Win_check()- Win_check() function is the core of the game where the function checks for the win and lose condition of both the players during each step of the game.


Any suggestions and any improvement in the program will be highly appreciated.

Please find the code for the game below
_______________________________________________________________________________________
from IPython.display import clear_output
import sys
Board=['']*10

def Create_Board():
	
	clear_output()
	print('   '+Board[7]+'| '+Board[8]+'  |'+Board[9])
	print("-----------")
	print('   '+Board[4]+'| '+Board[5]+'  |'+Board[6])
	print("-----------")
	print('   '+Board[1]+'| '+Board[2]+'  |'+Board[3])
	return (Board)

def Player_input(marker):

	#marker=input('Player1:Please select X or O')
	count=0
	
	if  marker !='X' or marker !='O':
		player1 = marker
		
		if player1 == 'X':
			
			player2 ='O'
			
		else:
			player2 = 'X'

	#count=count+1
	return (player1,player2)

def Position_select(marker):
	
	pos=int(input('Select the position:- \n'))
	if pos<=9:
		Board[pos]=marker
	else:
		Print("Invalid Position")

	return(Board[pos])
def Win_check(marker,count):

	if Board[1]==Board[4]==Board[7]==marker:
		print('CONGRATULATIONS Player:'+marker+' Wins....')
		sys.exit()
	elif Board[2]==Board[5]==Board[8]==marker:
		print('CONGRATULATIONS Player:'+marker+' Wins....')
		sys.exit()
	elif Board[3]==Board[6]==Board[9]==marker:
		print('CONGRATULATIONS Player:'+marker+' Wins....')
		sys.exit()
	elif Board[1]==Board[2]==Board[3]==marker:
		print('CONGRATULATIONS Player:'+marker+' Wins....')
		sys.exit()
	elif Board[4]==Board[5]==Board[6]==marker:
		print('CONGRATULATIONS Player:'+marker+' Wins....')
		sys.exit()
	elif Board[7]==Board[8]==Board[9]==marker:
		print('CONGRATULATIONS Player:'+marker+' Wins....')
		sys.exit()

	elif Board[1]==Board[5]==Board[9]==marker:
		print('CONGRATULATIONS Player:'+marker+' Wins....')
		sys.exit()
	elif Board[3]==Board[5]==Board[7]==marker:
		print('CONGRATULATIONS Player:'+marker+' Wins....')
		sys.exit()
	elif count==9:
		print("It is a DRAW.... \n")
		sys.exit()
	else:
		print('CONTINUE Playing....\n')
    
print('WELCOME to the TIC TAC ToOE game,Lets Start!!\n')
b=Create_Board()
marker= input('Player1:Please select "X" or "O":\n')
(c1,c2)=Player_input(marker)
if c1 == 'X':

	print("Player1 you are: 'X' and Player2 you are: 'O'\n")
else:

	print("Player1 you are: 'O' and Player2 you are: 'X'\n")
count=0

for i in range(1,6):

	#for i in range(1,5):
	print("Player 1 please select the position you want to play: ")
	Position_select(c1)
	Create_Board() 
	count=count+1
	Win_check(c1,count)
	
	if count==9:	
		Win_check(c1,count)
		break
	else:
		print("Player 2 please select the position you want to play:")
		Position_select(c2)
		Create_Board()
		count=count+1
		Win_check(c2,count)
