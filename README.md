#include <stdio.h>

int main() {
    int age, health;
    char gender;
    float premium ;

    
    printf("Enter age: ");
    scanf("%d", &age);

    printf("Enter gender (M/F): ");
    scanf(" %c", &gender);

    printf("Health condition (1-Healthy / 0-Unhealthy): ");
    scanf("%d", &health);

    
    if (age < 25) {
        if (health == 1)
            premium = 5000;
        else
            premium = 0; // Not eligible
    } 
    else if (age >= 25 && age <= 40) {
        if (health == 1)
            premium = 7000;
        else
            premium = 9500;
    } 
    else if (age >= 41 && age <= 60) {
        if (health == 1)
            premium = 10000;
        else
            premium = 13000;
    } 
    else if (age > 60) {
        if (health == 1)
            premium = 15000;
        else
            premium = 0; // Not eligible
    }

    
    printf("\nCustomer Details:\n");
    printf("Age: %d\n", age);
    printf("Gender: %c\n", gender);
    printf("Health: %s\n", (health == 1) ? "Healthy" : "Unhealthy");

    
    if (premium == 0) {
        printf("Not Eligible for Insurance.\n");
    } else {
        // Apply female discount
        if (gender == 'F' || gender == 'f') {
            premium = premium - (premium * 0.10);
        }

        printf("Final Premium: ₹%f\n", premium);
    }

    return 0;
}
