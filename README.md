#include<stdio.h>
/ Structure to store details of each day
struct Planner {
    char dayName[20];
    int date;
    char activity[50];
};

// Function prototypes
void create(struct Planner week[], int n);
void read(struct Planner week[], int n);
void display(struct Planner week[], int n);

// Main function
int main() {
    int n = 7;  // Weekly planner (7 days)
    struct Planner week[7];

    create(week, n);
    read(week, n);
    display(week, n);

    return 0;
}

// Function to initialize the weekly planner
void create(struct Planner week[], int n) {
    for (int i = 0; i < n; i++) {
        week[i].dayName[0] = '\0';
        week[i].date = 0;
        week[i].activity[0] = '\0';
    }
}

// Function to read planner details from user
void read(struct Planner week[], int n) {
    printf("Enter weekly schedule details:\n");
    for (int i = 0; i < n; i++) {
        printf("\nDay %d:\n", i + 1);
        printf("Enter day name: ");
        scanf("%s", week[i].dayName);
        printf("Enter date (numeric): ");
        scanf("%d", &week[i].date);
        printf("Enter activity: ");
        scanf(" %[^\n]", week[i].activity);  // To read full line with spaces
    }
}

// Function to display the weekly planner
void display(struct Planner week[], int n) {
    printf("\n----- Weekly Activity Report -----\n");
    printf("Day\t\tDate\tActivity\n");
    printf("-----------------------------------------\n");

    for (int i = 0; i < n; i++) {
        printf("%-10s\t%d\t%s\n", week[i].dayName, week[i].date, week[i].activity);
    }
}
