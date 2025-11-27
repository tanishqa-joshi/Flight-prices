#include <stdio.h>

struct Flights {
    char name[50];
    char to[50];
    char from[50];
    int num;
    float price;
};
void bubbleSort(struct Flights flight[], int n) {
    int i, j;
    struct Flights temp;

    for (i = 0; i < n - 1; i++) {
        for (j = 0; j < n - 1 - i; j++) {
            if (flight[j].price > flight[j + 1].price) {
            
                temp = flight[j];
                flight[j] = flight[j + 1];
                flight[j + 1] = temp;
            }
        }
    }
}

int main() {
    int i, n;

    printf("~~~~~~~~~~~~ Flight details ~~~~~~~~~~~~\n");
    printf("Enter number of flights: ");
    scanf("%d", &n);

    struct Flights flight[n];

    for (i = 0; i < n; i++) {
        printf("\nEnter details of flight %d\n", i + 1);

        printf("Name: ");
        scanf("%s", flight[i].name);

        printf("To: ");
        scanf("%s", flight[i].to);

        printf("From: ");
        scanf("%s", flight[i].from);

        printf("Number: ");
        scanf("%d", &flight[i].num);

        printf("Price: ");
        scanf("%f", &flight[i].price);
    }
    bubbleSort(flight, n);

    printf("\n====== Flights Sorted by Price (Low to High) ======\n");
    for (i = 0; i < n; i++) {
        printf("\n----- Flight %d -----\n", i + 1);
        printf("Name: %s\n", flight[i].name);
        printf("To: %s\n", flight[i].to);
        printf("From: %s\n", flight[i].from);
        printf("Number: %d\n", flight[i].num);
        printf("Price: %.2f\n", flight[i].price);
    }

    return 0;
}
