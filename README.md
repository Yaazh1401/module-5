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

int main() {
    float length, width, area;
    float *ptr_length = &length, *ptr_width = &width, *ptr_area = &area;
    scanf("%f", ptr_length);  
    scanf("%f", ptr_width);   
    *ptr_area = (*ptr_length) * (*ptr_width);  
    printf("Area of rectangle = %f sq. units\n", *ptr_area);
    
    return 0;
}
```
## OUTPUT
![image](https://github.com/user-attachments/assets/8d3ed73a-4b59-4eac-a033-7acd4e5135f6)
		       	


## RESULT
Thus the program to find area of rectangle using pointer has been executed successfully
 
 


# EX-27-DYNAMIC-MEMORY-ALLOCATION
## AIM
To write a C Program to print 'PRINTER' using malloc() and free().

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
#include <stdlib.h>  
#include <string.h>  
int main() {
    char *word = (char *)malloc(8 * sizeof(char));
    strcpy(word, "Printer");
    printf("%s\n", word);
    free(word);
    return 0;  
}
```
## OUTPUT
![image](https://github.com/user-attachments/assets/6335777c-8593-4a63-a948-2713c9c50a45)



## RESULT
Thus the program to print 'PRINTER' using malloc() and free() has been executed successfully
 
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
struct Student {
    char name[50];
    int roll_number;
    float marks;
};
int main() {
    struct Student s;
    scanf("%s", s.name); 
    scanf("%d", &s.roll_number);
    scanf("%f", &s.marks);
    printf("Displaying Information:\n");
    printf("Name: %s\n", s.name);
    printf("Roll number: %d\n", s.roll_number);
    printf("Marks: %.1f\n", s.marks);
    
    return 0;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/6ddbf52d-1282-454b-b9b9-4783e894f86a)


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
#include <stdio.h>
struct Employee {
    int empno;
    char dept[20];
    float basic_pay;
    float da;
    float hra;
    float gross_salary;
};
void calculateSalary(struct Employee *emp) {
    emp->da = emp->basic_pay * 0.10;  
    emp->hra = emp->basic_pay * 0.30; 
    emp->gross_salary = emp->basic_pay + emp->da + emp->hra;
}
int main() {
    struct Employee employees[3];
    int i;
    for(i = 0; i < 3; i++) {
        scanf("%d", &employees[i].empno);
        scanf("%s", employees[i].dept);
        scanf("%f", &employees[i].basic_pay);
        calculateSalary(&employees[i]);
    }
    printf("Details of the Employee:\n");
    for(i = 0; i < 3; i++) {
        printf("%d %s %.0f %.0f %.0f %.2f\n", 
               employees[i].empno,
               employees[i].dept,
               employees[i].basic_pay,
               employees[i].da,
               employees[i].hra,
               employees[i].gross_salary);
    }

    return 0;
}
```

 ## OUTPUT

 ![image](https://github.com/user-attachments/assets/5dc399b4-09f0-48a4-9c31-8a4cb876d853)


## RESULT

Thus the C program to read and store the data of 3 employees and calculate their Gross Salary using the concept of structure
 




# EX – 30 -STRUCURE

## AIM

Write a C program to create a student structure having fields stud_name and address. Accept the details of 'n' students, rearrange the data in alphabetical order of student name and display it.

## ALGORITHM 
Start

Define a structure Student with:

stud_name (string)

address (string)

Declare an array students[MAX_STUDENTS] to store student data

Read the number of students n

For each student from 0 to n - 1:

Read stud_name

Read address

Call the function sortStudents(students, n):

For i from 0 to n - 2:

For j from i + 1 to n - 1:

If students[i].stud_name comes after students[j].stud_name alphabetically (using strcmp):

Swap students[i] and students[j] using a temporary variable

After sorting, print the list:

For each student from 0 to n - 1:

Print stud_name and address

End



## PROGRAM
```
#include <stdio.h>
#include <string.h>
#define MAX_STUDENTS 50
#define MAX_LENGTH 50
struct Student {
    char stud_name[MAX_LENGTH];
    char address[MAX_LENGTH];
};
void sortStudents(struct Student students[], int n) {
    struct Student temp;
    for (int i = 0; i < n - 1; i++) {
        for (int j = i + 1; j < n; j++) {
            if (strcmp(students[i].stud_name, students[j].stud_name) > 0) {
                temp = students[i];
                students[i] = students[j];
                students[j] = temp;
            }
        }
    }
}
int main() {
    struct Student students[MAX_STUDENTS];
    int n;
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        scanf("%s", students[i].stud_name);
        scanf("%s", students[i].address);
    }
    sortStudents(students, n);
    for (int i = 0; i < n; i++) {
        printf("%s      %s\n", students[i].stud_name, students[i].address);
    }
    return 0;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/a5601379-0614-4072-82bf-58a972a2e53b)

 

## RESULT

Thus the C program to create a student structure having fields stud_name and address. Accept the details of 'n' students, rearrange the data in alphabetical order of student name and display it has been executed successfully.
	


