# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
## 5. Implementation of one-dimensional array and multidimensional array.
## 6. Implementation of string manipulation.
# Ex.No:11
  Formulate a C program to convert a given decimal number into its binary equivalent and display it.
# Date : 
# Aim:
To formulate a C program to convert a decimal number into its binary equivalent and display it.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare variables: num (input number), rem (remainder), binary[] (array to store binary digits), and loop counters i and k.
### Step 4: 
  Read the decimal number from the user.
### Step 5: 
  Initialize i = 0.
### Step 6: 
  Repeat while num > 0:
  Divide num by 2 and store the remainder in binary[i].
  Increment i.
  Update num = num / 2.
### Step 7: 
  Display the binary digits in reverse order (from i-1 down to 0).
### Step 8: 
   Stop
# Program:
`
#include <stdio.h>

int main()
{
    int n, binary[20], i = 0, j;

    printf("Enter a decimal number: ");
    scanf("%d", &n);

    while (n > 0)
    {
        binary[i] = n % 2;
        n = n / 2;
        i++;
    }

    printf("Binary equivalent: ");

    for (j = i - 1; j >= 0; j--)
        printf("%d", binary[j]);

    return 0;
}
`
# Output:
<img width="1087" height="428" alt="653886901-86a497d1-f1ba-476f-b80b-22f10cd9893f" src="https://github.com/user-attachments/assets/635475c1-68b7-425f-9582-2dc85cf63684" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:12
  Develop a C program to read a matrix and find its saddle point. A saddle point is an element that is the minimum in its row and also the maximum in its column. If such an element exists, display its position and value.
# Date : 
# Aim:
  To develop a C program that inputs a matrix, checks each row for its minimum element, verifies whether that element is also the maximum in its corresponding column, and displays the saddle point and its position if it exists.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
 Declare variables i, j, k, m, min, max and a position array pos[2][2].
### Step 4: 
 Read the order of the square matrix m.
### Step 5: 
 Declare an m × m matrix and read its elements.
### Step 6: 
 Display the matrix.
### Step 7: 
   For each row `i` from `0` to `m−1`:
- **Step 7.1:** Set `min` as the first element of the row.  
- **Step 7.2:** Scan the row to find its minimum element and store its position in `pos[0]`.  
- **Step 7.3:** Let `j` be the column of this minimum element.  
- **Step 7.4:** Set `max` as the first element of column `j`.  
- **Step 7.5:** Scan column `j` to find its maximum element and store its position in `pos[1]`.  
### Step 8: 
  Check if the row minimum equals the column maximum:
- If `min == max` **and their positions match**, then the element is a **saddle point**.
- Print the saddle point value and its position.
### Step 9: 
  Stop
# Program:
`
#include <stdio.h>

int main()
{
    int a[10][10], r, c, i, j, k;
    int min, isSaddle = 0;

    printf("Enter rows and columns: ");
    scanf("%d %d", &r, &c);

    printf("Enter matrix elements:\n");
    for (i = 0; i < r; i++)
        for (j = 0; j < c; j++)
            scanf("%d", &a[i][j]);

    for (i = 0; i < r; i++)
    {
        min = a[i][0];

        for (j = 1; j < c; j++)
        {
            if (a[i][j] < min)
                min = a[i][j];
        }

        for (j = 0; j < c; j++)
        {
            if (a[i][j] == min)
            {
                for (k = 0; k < r; k++)
                {
                    if (a[k][j] > min)
                        break;
                }

                if (k == r)
                {
                    printf("Saddle Point: Position = (%d, %d), Value = %d\n",
                           i + 1, j + 1, min);
                    isSaddle = 1;
                }
            }
        }
    }

    if (!isSaddle)
        printf("No Saddle Point\n");

    return 0;
}
`
# Output:
<img width="1362" height="457" alt="653888388-c894ca92-0d23-40a7-bc08-ff5e9cface87" src="https://github.com/user-attachments/assets/ebd1438e-a058-48ef-a8c3-236a5a23591a" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:13
  Formulate a C program to reverse a string entered by the user and display the reversed string.
# Date : 
# Aim:
  To formulate a C program that reads a string from the user, reverses it, and prints the reversed string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare two character arrays: `s` to store the input string and `d` to store the reversed string.
### Step 4: 
  Read the string from the user using `scanf("%[^\n]s", s);`
### Step 5: 
  Find the length of the string `s` by traversing it until the null character `'\0'` is encountered.
### Step 6: 
  Initialize a counter `j` for the reversed string.
### Step 7: 
  Copy characters from the end of `s` to the beginning of `d` using a loop until all characters are copied in reverse order.
### Step 8: 
  Terminate the reversed string `d` with the null character `'\0'`.
### Step 9: 
  Print the reversed string.
### Step 10: 
  Stop
# Program:
`
#include <stdio.h>
#include <string.h>

int main()
{
    char str[100];
    int i, len;

    printf("Enter a string: ");
    scanf("%s", str);

    len = strlen(str);

    printf("Reversed string: ");

    for (i = len - 1; i >= 0; i--)
        printf("%c", str[i]);

    return 0;
}
`
# Output:
<img width="1251" height="557" alt="653889481-f46ef81c-caf0-4515-ac3d-341d61305cb6" src="https://github.com/user-attachments/assets/42df10ae-05d4-42d8-a2d4-19639630aede" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:14
  Formulate a C program to count the frequency of each character in a given string and display the count of every character.
# Date : 
# Aim:
  To formulate a C program that accepts a string from the user and calculates the frequency of each character in the string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array `s[100]` to store the input string, an integer array `visited[256]` initialized to `0`, and variables `i`, `n`, and `count`.
### Step 4: 
  Read the string from the user using `scanf("%[^\n]", s);`
### Step 5: 
  Calculate the length of the string using `strlen(s)` and store it in `n`.
### Step 6: 
 For each character `s[i]` in the string (from `i = 0` to `n - 1`):
 - If `visited[(unsigned char)s[i]] == 0` (character not yet counted):  
  - Initialize `count = 0`.  
  - Loop through the string again and increment `count` for every occurrence of `s[i]`.  
  - Print `s[i]` and its count.  
  - Set `visited[(unsigned char)s[i]] = 1` to mark it as counted.
### Step 7: 
  Repeat Step 6 for all characters.
### Step 8:
  Stop
# Program:
`
#include <stdio.h>

int main()
{
    char str[100];
    int freq[256] = {0};
    int i;

    printf("Enter a string: ");
    scanf("%s", str);

    for (i = 0; str[i] != '\0'; i++)
        freq[(unsigned char)str[i]]++;

    printf("Character Frequency:\n");

    for (i = 0; i < 256; i++)
    {
        if (freq[i] > 0)
            printf("%c = %d\n", i, freq[i]);
    }

    return 0;
}

`
# Output:
<img width="1285" height="627" alt="653891278-229b5bdb-9e0a-4a08-aa72-c00eeff07405" src="https://github.com/user-attachments/assets/7d035a3a-64b1-439f-a244-fa0e2e937d38" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:15
  Formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Date : 
# Aim:
  To formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array `str` to store the input string and a 2D array `words` to store individual words.
### Step 4: 
  Read the input string using `scanf("%[^\n]s", str);`
### Step 5: 
 Split the string into words:
 - Traverse the string character by character.  
 - When a space is encountered, terminate the current word with `'\0'` and move to the next row in `words`.  
 - Otherwise, copy the character into the current word.
### Step 6: 
  Compare each word with all other words to detect duplicates:
  - If a duplicate is found, mark it by setting the first character to `'\0'`.
### Step 7: 
  Print all words that are not marked as duplicates.
### Step 8: 
  Stop
# Program:
`
#include <stdio.h>
#include <string.h>

int main()
{
    char str[200], words[50][20];
    int n = 0, i, j, duplicate;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    char *word = strtok(str, " \n");

    while (word != NULL)
    {
        duplicate = 0;

        for (i = 0; i < n; i++)
        {
            if (strcmp(words[i], word) == 0)
            {
                duplicate = 1;
                break;
            }
        }

        if (!duplicate)
        {
            strcpy(words[n], word);
            n++;
        }

        word = strtok(NULL, " \n");
    }

    printf("String with unique words: ");

    for (i = 0; i < n; i++)
        printf("%s ", words[i]);

    return 0;
}

`
# Output:
<img width="1227" height="677" alt="653892420-fe285639-f335-495c-a5af-e90a323d4f4e" src="https://github.com/user-attachments/assets/2567a8a9-e4be-4166-adaf-1fe37786d3a9" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.
