#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main() {
    int user, comp;
    char choice;

    srand(time(NULL)); 

    do {
        printf("Enter a number (1-100): ");
        scanf("%d", &user);

        if (user < 1 || user > 100) {
            printf("Error: Number out of range!\n");
            continue;
        }

        comp = rand() % 100 + 1;
        printf("Computer-generated number: %d\n", comp);

        if (comp > user)
            printf("%d is greater than %d.\n", comp, user);
        else if (comp < user)
            printf("%d is greater than %d.\n", user, comp);
        else
            printf("Numbers are equal.\n");

        if (comp % 2 == 0)
            printf("%d is even.\n", comp);
        else
            printf("%d is odd.\n", comp);

        printf("Try again? (yes/no): ");
        scanf(" %c", &choice);
    } while (choice == 'y' || choice == 'Y');

    return 0;
}
