   #include <stdio.h>
#include <string.h>

#define MAX_CITY_NAME 50
#define MAX_CONDITION 50

// Structure to store weather data
struct Weather {
    char city[MAX_CITY_NAME];
    float temperature;
    float humidity;
    char condition[MAX_CONDITION];
};

int main() {
    struct Weather weather;
    
    printf("Weather Report Generation\n");
    printf("-------------------------\n");

    // Input weather details
    printf("Enter city name: ");
    fgets(weather.city, MAX_CITY_NAME, stdin);
    weather.city[strcspn(weather.city, "\n")] = '\0';  // Remove trailing newline
    
    printf("Enter temperature (in Celsius): ");
    scanf("%f", &weather.temperature);

    printf("Enter humidity (in percentage): ");
    scanf("%f", &weather.humidity);

    getchar(); // Consume newline left by scanf
    printf("Enter weather condition (e.g., Sunny, Rainy): ");
    fgets(weather.condition, MAX_CONDITION, stdin);
    weather.condition[strcspn(weather.condition, "\n")] = '\0';  // Remove trailing newline

    // Display the weather report
    printf("\nWeather Report\n");
    printf("-------------------------\n");
    printf("City: %s\n", weather.city);
    printf("Temperature: %.2f °C\n", weather.temperature);
    printf("Humidity: %.2f %%\n", weather.humidity);
    printf("Condition: %s\n", weather.condition);

    return 0;
}
