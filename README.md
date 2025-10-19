# EX-26-AREA-OF-RECTANGLE-USING- POINTER
## AIM
To write a C Program to find area of rectangle using pointer.

## ALGORITHM
1.	Start the program.
2.	Read two numbers.
3.	Calculate the area of rectangle using the formula area=(x)(*y)
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

void calculateArea(float *length, float *breadth, float *area) {
    *area = (*length) * (*breadth);
}

int main(void) {
    float l, b, area;
    float *pl = &l;
    float *pb = &b;
    float *pa = &area;

    printf("Enter length of rectangle: ");
    scanf("%f", pl);
    printf("Enter breadth of rectangle: ");
    scanf("%f", pb);

    calculateArea(pl, pb, pa);

    printf("Area of rectangle = %.2f\n", area);

    return 0;
}
```

## OUTPUT
``
		  ![WhatsApp Image 2025-10-19 at 23 01 06_a82041dc](https://github.com/user-attachments/assets/8df89584-47b6-4f8c-986b-d423def1084f)
     	

``

## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'WELCOME' using malloc() and free().

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Allocate memory using malloc().
4.	Display the string.
5.	Remove the allocated memory using free().
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <stdlib.h>  // for malloc, free
#include <string.h>  // for strcpy

int main(void) {
    char *str = NULL;
    const char *text = "WELCOME";
    size_t len = strlen(text);

    // Allocate memory (including space for the terminating '\0')
    str = (char *) malloc((len + 1) * sizeof(char));
    if (str == NULL) {
        printf("Memory allocation failed!\n");
        return 1;
    }

    // Copy the text into the allocated memory
    strcpy(str, text);

    // Display the string
    printf("%s\n", str);

    // Free the allocated memory
    free(str);
    str = NULL;  // good practice to avoid dangling pointer

    return 0;
}

```
## OUTPUT
output
WELCOME

## RESULT
Thus the program to print 'WELCOME' using malloc() and free() has been executed successfully
 
.

# EX-28-STUDENT-INFORMATION-USING-STRUCTURE

## AIM

To write a C Program to store the student information and display it using structure.

## ALGORITHM

1.	Start the program.
2.	Create a student structure with name, roll number and marks as members.
3.	Using structure variable read the structure members and print them.
4.	Stop the program.

## PROGRAM
```
#include <stdio.h>

// Define Student structure
struct Student {
    int rollno;
    char name[50];
    float percentage;
};

// Function to input student details
void inputStudent(struct Student *stu) {
    scanf("%d", &stu->rollno);

    getchar();  // To consume leftover newline
    fgets(stu->name, sizeof(stu->name), stdin);

    // Remove trailing newline from fgets
    int len = 0;
    while (stu->name[len] != '\0') len++;
    if (len > 0 && stu->name[len - 1] == '\n') {
        stu->name[len - 1] = '\0';
    }

    scanf("%f", &stu->percentage);
}

// Function to display student details
void displayStudent(struct Student stu) {
    printf("Rollno is: %d\n", stu.rollno);
    printf("Name is: %s\n", stu.name);
    printf("Percentage is: %.2f\n", stu.percentage);
}

int main() {
    struct Student s;

    inputStudent(&s);
    displayStudent(s);

    return 0;
}
```

## OUTPUT
![WhatsApp Image 2025-10-19 at 23 05 22_947e9ce5](https://github.com/user-attachments/assets/7a9aaac3-fbc1-4256-a4c3-24cdeb01c027)


## RESULT

Thus the program to store the student information and display it using structure has been executed successfully
 
 


# EX-29-EMPLOYEE-STRUCTURE-SALARY-CALCULATION

## AIM

To write a C Program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure.

## ALGORITHM

1.	Start the program.
2.	Create an employee structure with name, id and salary details as members.
3.	Using structure variable read the structure members.
4.	Calculate the gross salary and print the details.
5.	Stop the program.

## PROGRAM
```
#include<stdio.h>
struct employee{
    int empno;
    char dept[20];
    float basic,da,hra,gross;
};
int main(){
    struct employee e[3];
    int i;
    
    for(i=0;i<3;i++){
    scanf("%d",&e[i].empno);
    
    scanf("%s",e[i].dept);
    
    
    scanf("%f",&e[i].basic);
    
    e[i].da=0.10*e[i].basic;
    e[i].hra=0.30*e[i].basic;
    e[i].gross=e[i].basic+e[i].da+e[i].hra;
    }
    printf("Details of the Employee:\n");
    
    for(i=0;i<3;i++)
  {  printf("%d %s %.0f %.0f %.0f %.2f\n",
    e[i].empno,e[i].dept,e[i].basic,e[i].da,e[i].hra,e[i].gross);
}
 return 0;   
}
```

 ## OUTPUT
![WhatsApp Image 2025-10-19 at 23 08 56_1c7652e7](https://github.com/user-attachments/assets/02887f6c-ea34-4c07-8ba3-bb2919b3b9d8)

 

## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STUDENTS MARK -TOTAL &AVERAGE USING STRUCURE

## AIM
Create a C program to calculate the total and average of student using structure.

## ALGORITHM 

Step 1: Start the program.
Step 2: Define a struct student with:
•	name: a character array (size 10) for the student's name (not used in the logic).
•	rollno: an integer for the student's roll number (also unused).
•	subject[5]: an array to store marks of 5 subjects.
•	total: an integer to store total marks.
Step 3: Declare an array s[2] of type struct student for 2 students. Also declare variables n, i, and j for input 
             and iteration.
Step 4: Input Loop (i = 0 to 1):
•	Read an integer n (but it's not used later — possibly intended for roll number or placeholder).
•	Loop j = 0 to 4:
o	Read 5 subject marks into s[i].subject[j].
Step 5: Total Marks Calculation Loop (i = 0 to 1):
•	Initialize s[i].total to 0.
•	Loop j = 0 to 4:
o	Add each subject mark to s[i].total.
Step 6: Override Total (Hardcoded):
•	Set s[0].total = 374;
•	Set s[1].total = 383;
           This step overwrites the computed totals. It seems like testing or hardcoded totals — unnecessary if you’re 
                 already calculating them.
Step 7: Output Loop (i = 0 to 1):
•	Print s[i].total for each student.
Step 8: End the program.

## PROGRAM
```
#include <stdio.h>

#define NUM_SUBJECTS 5  // you can change this as needed

// Define a structure for a student
struct Student {
    char name[50];
    int rollNumber;
    float marks[NUM_SUBJECTS];
    float total;
    float average;
};

int main(void) {
    struct Student s;
    int i;

    printf("Enter student name: ");
    scanf("%49s", s.name);  // read string (no spaces) for simplicity
    printf("Enter roll number: ");
    scanf("%d", &s.rollNumber);

    // Read marks
    printf("Enter marks for %d subjects:\n", NUM_SUBJECTS);
    s.total = 0.0f;
    for (i = 0; i < NUM_SUBJECTS; i++) {
        printf(" Subject %d: ", i + 1);
        scanf("%f", &s.marks[i]);
        s.total += s.marks[i];
    }

    // Compute average
    s.average = s.total / NUM_SUBJECTS;

    // Display results
    printf("\nStudent Details:\n");
    printf(" Name        : %s\n", s.name);
    printf(" Roll Number : %d\n", s.rollNumber);
    printf(" Total Marks : %.2f\n", s.total);
    printf(" Average     : %.2f\n", s.average);

    return 0;
}
```

## OUTPUT

 ![WhatsApp Image 2025-10-19 at 23 12 55_9eddc808](https://github.com/user-attachments/assets/b3fb151a-0f98-4e93-8b26-6dfdd27c1798)
![WhatsApp Image 2025-10-19 at 23 13 24_5eb13e0b](https://github.com/user-attachments/assets/8bb008dd-3ca6-4670-9452-58435eb25219)


## RESULT

Thus the C program to calculate the total and average of student using structure has been executed successfully.
	


