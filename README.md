# Flight-prices
#include <stdio.h>
void bubbleSort(float price[], int n) {
    int i, j;
    float temp;
    for (i = 0; i < n - 1; i++) {
        for (j = 0; j < n - 1 - i; j++) {
            if (price[j] > price[j + 1]) {
                temp = price[j];
                price[j] = price[j + 1];
            price[j + 1] = temp;
            }
        }
    }
}
int main() {
    int n, i;
    printf("************Flight Prices************\n");
    printf("Enter the number of tickets: ");
    scanf("%d", &n);
    printf("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n");
    float price[n];
    for (i = 0; i < n; i++) {
        printf("Enter price of ticket %d: ", i + 1);
        scanf("%f", &price[i]);
        printf("~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~\n");
    }
    bubbleSort(price, n);
    printf("\nPrices in increasing order are:\n");
    for (i = 0; i < n; i++) {
        printf(" %d: %.2f\n", i + 1, price[i]);
    }
    return 0;
}
