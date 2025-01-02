# binary-to-decimal
c programm of binary to decimal

#include <stdio.h>

void decimaltobinary(float num) {
    int integerPart = (int)num; 
    float fractionalPart = num - integerPart; 
    int binary[32];
    int i = 0;
    while (integerPart > 0) {
        binary[i] = integerPart % 2;
        integerPart = integerPart / 2;
        i++;
    }

    printf("Binary equal to: ");
    for (int j = i - 1; j >= 0; j--) {
        printf("%d", binary[j]);
    }

    
    if (fractionalPart > 0) {
        printf(".");
        int count = 0; 
        while (fractionalPart > 0 && count < 8) { 
            fractionalPart *= 2;
            int fractionalBit = (int)fractionalPart; 
            printf("%d", fractionalBit);
            fractionalPart -= fractionalBit; 
            count++;
        }
    }
    printf("\n");
}

int main() {
    float num;
    printf("Enter a decimal number: ");

    if (scanf("%f", &num) != 1) {
        printf("Invalid input. Please enter a decimal number.\n");
        return 1; 
    }

    decimaltobinary(num);
    
    return 0;
}
