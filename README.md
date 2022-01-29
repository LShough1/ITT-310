#ITT-310
#Code for ITT-310 Class Milestone Project

// This is a console-based calculator using C code.
// The program will expand but currently only includes two operations. 
// The user can choose to add or subtract and only use two numbers at a time. 
// There is also a feature that sees when an unavailable operation is chosen, and resets the program. 
#include<stdio.h>

#define OPERATION "Enter the calculator operation you want to do:" //Asks the user to enter an operation

// Function called 
void addition(); //Calls the addition function
void subtraction(); //Calls the subtraction fucntion
void calculator_operations(); //Calls the calculator operations function

/*Main Program*/
int main()
{
    int V = 1; //Allows the program to run if there is an operation chosen
    char Calc_operation; //Defines variable so that operations can be chosen

    // Use the function 
    calculator_operations();

    while (V) //While loop if there is an operation chosen
    {
        printf("\n"); //\n just makes a new line in the console output
        printf("%s : ", OPERATION); //Asks the user to enter a calculator operation
        Calc_operation = getche();
        switch (Calc_operation)
        {
        case '+': addition(); //When + is chosen, the program jumps to use the rules to add numbers below.
            break;

        case '-': subtraction(); //When - is chosen, the program jumps to use the rules to subtract numbers below. 
            break;

        default: system("cls"); //If any other key besides - or + is chosen, this variable is called
            printf("\nYou have entered unavailable operator\n"); //Tells the user they entered an unavailable operation
            printf("\nPlease Enter either + or - \n"); //Asks the user to add or subtract
            calculator_operations(); //Displays the operations available to use
        }
    }
}

/*Defintions and preprocessor use*/

void calculator_operations() /*Defines the variableand tells the user what the program does.*/
{
    printf("\nThis is a simple console-based calculator program \n"); //Print 'This is a calculator program' to tell the user
    printf("This first release only includes two operations, so: \n\n"); //Gives detail to the user
    printf("Use + symbol to Add \n"); //Tells the user to use + to Add numbers
    printf("Use - symbol to Subtract \n"); //Tells the user to use - to Subtract numbers
}

void addition() /*Defines what happens when + is chosen by the user*/
{
    int z, x, y = 0; //Makes three local variables to add later on
    printf("\nPlease enter first number  : "); //Asks the user to enter a number
    scanf_s("%d", &z); //The first number entered is now defined as z
    printf("Please enter second number : "); //Asks the user to enter a number
    scanf_s("%d", &x); //The second number entered is now defined as x
    y = z + x; //Y is now equal to the first and second number added together.
    printf("\n%d + %d = %d\n", z, x, y); //Prints the result of the addition. 
}

void subtraction() /*Defines what happens when - is chosen by the user*/
{
    int a, b, c = 0; //Makes three local variables to subtract later on
    printf("\nPlease enter first number  : "); //Asks the user to enter a number
    scanf_s("%d", &a); //The first number entered is now defined as a
    printf("Please enter second number : ");  //Asks the user to enter a number
    scanf_s("%d", &b); //The second number entered is now defined as b
    c = a - b; //c is now equal to the first and second number added together.
    printf("\n%d - %d = %d\n", a, b, c);  //Prints the result of the subtraction. 
}
