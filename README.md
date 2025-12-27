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
void bin(int n)
{
    if(n==0){
        return;
    } else {
        bin(n/2);
        printf("%d",n%2);
    }
}
int main()
{
    int num;
    scanf("%d",&num);
    printf("%d in decimal = ",num);
    bin(num);
    printf(" in binary\n");
    return 0;
    
}
# Output:
<img width="1110" height="376" alt="image" src="https://github.com/user-attachments/assets/24cdd909-956d-44e5-8aa2-74f9e6a7ccdd" />


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

int main()
{
    int n;
    int a[10][10];
    int i, j, k;
    int min, colIndex;
    int saddleRow = -1, saddleCol = -1, saddleValue;

    scanf("%d", &n);

    for (i = 0; i < n; i++)
        for (j = 0; j < n; j++)
            scanf("%d", &a[i][j]);

    printf("The matrix is\n");
    for (i = 0; i < n; i++)
    {
        for (j = 0; j < n; j++)
            printf("%d ", a[i][j]);
        printf("\n");
    }

    for (i = 0; i < n; i++)
    {
        min = a[i][0];
        colIndex = 0;

        for (j = 1; j < n; j++)
        {
            if (a[i][j] <= min)   // IMPORTANT FIX
            {
                min = a[i][j];
                colIndex = j;
            }
        }

        for (k = 0; k < n; k++)
        {
            if (a[k][colIndex] > min)
                break;
        }

        if (k == n)
        {
            saddleRow = i;
            saddleCol = colIndex;
            saddleValue = min;
        }
    }

    if (saddleRow != -1)
        printf("\nSaddle point (%d, %d) : %d", saddleRow, saddleCol, saddleValue);
    else
        printf("\nNo Saddle Point");

    return 0;
}



# Output:
<img width="731" height="446" alt="image" src="https://github.com/user-attachments/assets/6d74fd3d-d478-43a5-8445-25d3e748b32e" />


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
<img width="390" height="271" alt="image" src="https://github.com/user-attachments/assets/5a0896a2-1aae-4540-b0e3-41ef9a3dffdb" />


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
<img width="431" height="450" alt="image" src="https://github.com/user-attachments/assets/87a611ad-b125-4e80-adf7-0e3c535d9e96" />


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
<img width="552" height="278" alt="image" src="https://github.com/user-attachments/assets/0211fcdf-40da-4981-8efc-255f3efcc2db" />


# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

