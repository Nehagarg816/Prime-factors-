# Prime-factors-
This is a program for finding prime factors of a number in C programming using recursive and non recursive approaches both


#include <stdio.h>
void factor(int n) // Iterative approach
{
    int s;
    printf("Prime factors of entered numbers are: ");
    for (int i = 2; i <= n; i++)
    {
        s = n % i;
        if (s == 0 && i > 0)
        {
            n = n / i;
            if (check_factor(i) == 1)
            {
                printf("%d\n", i);
            }
        }
    }
}
int check_factor(int num)
{
    int i = 2;
    while (i <= num)
    {
        if (num % i == 0)
            break;
        i++;
    }

    if (i == num)
    {
        return 1;
    }
    return 0;
}
void rec_factor(int n) // Recursive approach
{
    if (n == 0)
    {
        return;
    }

    for (int i = 2; i <= n; i++)
    {
        if (n % i != 0)
        {
            continue;
        }
        else
        {
            if (check_factor(i) == 1)
            {
                printf("%d\n", i);
                rec_factor(n / i);
                return;
            }
        }
    }
}
int main()
{
    int num;
    printf("Enter one number: ");
    scanf("%d", &num);
    factor(num);
    return 0;
}
