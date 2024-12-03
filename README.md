#include <stdio.h>
#include <stdlib.h>
#include <time.h>

void winner(int player, int computer) {
    if (player == computer) {
        printf("It's a tie, nobody win's!\n");
    } else if ((player == 0 && computer == 2) || 
               (player == 1 && computer == 0) || 
               (player == 2 && computer == 1)) {
        printf("You win!\n");
    } else {
        printf("Computer wins!\n");
    }
}
int main() {
    int player, computer;
    srand(time(0));
    printf("Rock, Paper, Scissors Game\n");
    printf("Enter 0 for Rock, 1 for Paper, 2 for Scissors\n");
    printf("Enter your choice: ");
    scanf("%d", &player);
    if (player < 0 || player > 2) {
        printf("Invalid choice! Please choose between 0, 1, or 2.\n");
        return 1;
    }
    computer = rand() % 3;
    if (computer == 0)
        printf("Computer chose Rock\n");
    else if (computer == 1)
        printf("Computer chose Paper\n");
    else
        printf("Computer chose Scissors\n");

    winner(player, computer);
  return 0;
}
