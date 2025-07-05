# substitution
 A simple C program that performs substitution cipher encryption. It replaces each letter of the plaintext with a corresponding letter from a user-provided key. Built for educational purposes as part of the CS50 course.


#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(int argc, string argv[])
{
if (argc != 2)
{
    printf("you must enter the program name and the cipher key\n");
return 1;
}
string key = argv[1];

if (strlen(key) != 26)
{
    printf("key must be 26 characters\n");
return 1;
}
for (int i = 0; i < 26; i++)
{
char c = key[i];
if (!((c >= 'a' && c <= 'z') || (c >= 'A' && c <= 'Z')))
{
printf("key must contain only letters\n");
return 1;
    }
}
string plaintext = get_string("plaintext: ");

    printf("ciphertext: ");

for (int i = 0; i < strlen(plaintext); i++)
{
char c = plaintext[i];

if (c >= 'A' && c <= 'Z')
{
int index = c - 'A';
char cipher = key[index];

if (cipher >= 'a' && cipher <= 'z')
{
cipher = cipher - ('a' - 'A');
}


    printf("%c", cipher);
}

else
{
    printf("%c", c);
    }
}
printf("\n");


return 0;
}
