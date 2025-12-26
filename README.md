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
#include <stdio.h>

int main()
{
    int num=13, binary[32], i = 0;
    scanf("%d", &num);

    if (num == 0)
    {
        printf("Binary equivalent: 0\n");
    }
    else
    {
        while (num > 0)
        {
            binary[i] = num % 2;
            num = num / 2;
            i++;
        }

        printf("Binary equivalent: ");
        for (i = i - 1; i >= 0; i--)
        {
            printf("%d", binary[i]);
        }
        printf("\n");
    }

    return 0;
}

# Output:
Binary equivalent: 1101

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:12
  Binary equivalent: 1101

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
#include <stdio.h>

int main() {
    int m, n, i, j, k;
    int flag = 0;

    printf("Enter number of rows and columns: ");
    scanf("%d %d", &m, &n);

    int mat[m][n];

    printf("Enter matrix elements:\n");
    for (i = 0; i < m; i++)
        for (j = 0; j < n; j++)
            scanf("%d", &mat[i][j]);

    for (i = 0; i < m; i++) {
        int min = mat[i][0];
        int col_index = 0;
        for (j = 1; j < n; j++) {
            if (mat[i][j] < min) {
                min = mat[i][j];
                col_index = j;
            }
        }
        int isSaddle = 1;
        for (k = 0; k < m; k++) {
            if (mat[k][col_index] > min) {
                isSaddle = 0;
                break;
            }
        }

        if (isSaddle) {
            printf("Saddle point = %d at position (%d, %d)\n", min, i, col_index);
            flag = 1;
        }
    }

    if (!flag)
        printf("No saddle point exists in the matrix.\n");

    return 0;
}


# Output:
Enter number of rows and columns: 3 3
Enter matrix elements:
11 23 12
45 14 17
7  16  9
Saddle point = 12 at position (0, 2)

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
#include <stdio.h>
#include <string.h>

int main()
{
    char str[100];
    int len, i;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);  
    str[strcspn(str, "\n")] = '\0'; 

    len = strlen(str);

    printf("Reversed string: ");
    for(i = len - 1; i >= 0; i--)
    {
        printf("%c", str[i]);
    }
    printf("\n");

    return 0;
}

# Output:
Enter a string: Saveetha
Reversed string: ahteevaS

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
#include <stdio.h>
#include <string.h>

int main()
{
    char str[100];
    int freq[256] = {0}; 
    int i;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);  
    str[strcspn(str, "\n")] = '\0'; 
    for(i = 0; str[i] != '\0'; i++)
    {
        freq[(int)str[i]]++;
    }

    printf("Character frequencies:\n");
    for(i = 0; i < 256; i++)
    {
        if(freq[i] != 0)
        {
            printf("%c : %d\n", i, freq[i]);
        }
    }

    return 0;
}

# Output:
Enter a string: hello
Character frequencies:
h : 1
e : 1
l : 2
o : 1

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
#include <stdio.h>
#include <string.h>

int main()
{
    char str[200], words[50][50];
    int i, j, k = 0, wordCount = 0, flag;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);
    str[strcspn(str, "\n")] = '\0'; 
    char *token = strtok(str, " ");
    while(token != NULL)
    {
        strcpy(words[wordCount], token);
        wordCount++;
        token = strtok(NULL, " ");
    }

    printf("String with unique words:\n");
    for(i = 0; i < wordCount; i++)
    {
        flag = 0;
        for(j = 0; j < i; j++)
        {
            if(strcmp(words[i], words[j]) == 0)
            {
                flag = 1; 
                break;
            }
        }

        if(flag == 0)
            printf("%s ", words[i]);
    }

    printf("\n");
    return 0;
}

# Output:
Enter a string: hello world hello saveetha world
String with unique words:
hello world saveetha

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

