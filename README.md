#include <stdio.h>
struct Student
{
char name[50];
int roll;
int marks[5];
int total;
float average;
char grade;
};
int main()
{
struct Student s[50];
int n, i, j;
printf("Enter number of students: ");
scanf("%d", &n);
if (n < 1 || n > 50)
{
printf("Please enter between 1 and 50 students.");
return 1;
}
{
for (i = 0; i < n; i++)
printf("\nEnter details of student %d\n", i + 1);
printf("Enter name: ");
scanf(" %49[^\n]", s[i].name);
printf("Enter roll number: ");
scanf("%d", &s[i].roll);
s[i].total = 0;
for (j = 0; j < 5; j++)
{
printf("Enter marks of subject %d: ", j + 1);
scanf("%d", &s[i].marks[j]);
s[i].total += s[i].marks[j];
}
s[i].average = s[i].total / 5.0;
if (s[i].average >= 90)
s[i].grade = 'A';
else if (s[i].average >= 80)
s[i].grade = 'B';
else if (s[i].average >= 70)
s[i].grade = 'C';
else if (s[i].average >= 60)
s[i].grade = 'D';
else
s[i].grade = 'F';
}
printf("\n----- STUDENT RESULT -----\n");
for (i = 0; i < n; i++)
{
printf("\nName: %s", s[i].name);
printf("\nRoll Number: %d", s[i].roll);
printf("\nTotal Marks: %d", s[i].total);
printf("\nAverage Marks: %.2f", s[i].average);
printf("\nGrade: %c\n", s[i].grade);
}
return 0;
}
