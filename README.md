This code write with the C program

#include <stdio.h>

// Alien numeral value
int character(char c)
{
    if (c == 'A')
        return 1;
    if (c == 'B')
        return 5;
    if (c == 'Z')
        return 10;
    if (c == 'L')
        return 50;
    if (c == 'C')
        return 100;
    if (c == 'D')
        return 500;
    if (c == 'R')
        return 1000;
    return 0;
}
// Variable
char Alien[50];
int s = 0;

int main(void)
{
    printf("Program will loop. Type \"E\" to end program\n");
    while (1)
    {
        // Input
        printf("Input:s = ");
        scanf("%49s", Alien);
        // Read
        for (int i = 0; Alien[i] != '\0'; i++)
        {
            int first = character(Alien[i]);
            int second = character(Alien[i + 1]);
            // Invalid
            if (first == 0 && Alien[0] != 'E')
            {
                printf("Error: Invalid character '%c'\n----------------------------\n", Alien[i]);
                s = 0;
                break;
            }
            if (first < second)
            {
                s = s + (second - first);
                i++;
            }
            else
            {
                s = s + first;
            }
            // Debug
            // printf("Debug: i=%d, first=%d, second=%d, s=%d\n", i, first, second, s);
        }
        // Output
        if (s != 0)
        {
            printf("Output:s = %d\n----------------------------\n", s);
        }
        // Reset
        s = 0;
        // End
        if (Alien[0] == 'E')
        {
            printf("End program.\n");
            break;
        }
    }
    return 0;
}
