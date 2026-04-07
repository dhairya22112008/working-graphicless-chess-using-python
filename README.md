import chess
import random

board = chess.Board()
boards_moves = []
move_count = [sum(boards_moves)]
print(board)
comp = str(board._is_safe)
print(len(comp))
print(comp)

def amove():
    while True: 
        try:
            c = chess.Move.from_uci(input("Enter your move (white): "))
            if c in board.legal_moves:
                c_str = str(c)
                c_sqr_from = c_str[:2]
                c_sqr_to = c_str[2:]
                
                board.push(c)
                print(board)
                print(f"The piece is moved from {c_sqr_from} to {c_sqr_to}")
                boards_moves.append(0.5)
                break
            else:
                print("Invalid move. Please enter a legal move.")
        except ValueError:
            print("Invalid UCI format. Please enter a move like 'e2e4'.")
    
    while True:
        try:
            q = chess.Move.from_uci(input("Enter the move from black: "))
            if q in board.legal_moves:
                q_str = str(q)
                q_sqr_from = q_str[:2]
                q_sqr_to = q_str[2:]
            
                board.push(q)
                print(board)
                print(f"The piece is moved from {q_sqr_from} to {q_sqr_to}")
                boards_moves.append(0.5)
                break
            else:
                print("Invalid move. Please enter a legal move.")
        except ValueError:
            print("Invalid UCI format. Please enter a move like 'e7e5'.")


while True :
    amove()
