```C
#include <cs50.h>
#include <ctype.h>
#include <math.h>
#include <stdio.h>
#include <string.h>

int letters(string s);
int words(string s);
int sentences(string s);

int main(void)
{
    // Input from User
    string str = get_string("Enter the text: ");

    // Calculation Index
    float word = words(str);
    float L = (letters(str) / word) * 100;
    float S = (sentences(str) / word) * 100;
    int index = round(0.0588 * L - 0.296 * S - 15.8);

    // Giving Grades
    if (index < 1)
    {
        printf("Before Grade 1\n");
    }
    else if (index > 16)
    {
        printf("Grade 16+\n");
    }
    else
        printf("Grade %i\n", index);
}



// Calculates number of letters
int letters(string s)
{
    int x = 0;
    for (int i = 0; i < strlen(s); i++)
    {
        if (isblank(s[i]) || ispunct(s[i]) || s[i] == 32)
        {
        }
        else
            x++;
    }
    return x;
}

// Calculates number of words
int words(string s)
{
    int x = 1;
    for (int i = 0; i < strlen(s); i++)
    {
        if (isblank(s[i]))
        {
            x++;
        }
    }
    return x;
}

// Calculates number of sentences
int sentences(string s)
{
    int x = 0;
    for (int i = 0; i < strlen(s); i++)
    {
        if (s[i] == '.' || s[i] == '!' || s[i] == '?')
        {
            x++;
        }
    }
    return x;
}

```