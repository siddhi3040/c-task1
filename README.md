#include <iostream>
#include <cstdlib>
#include <ctime>

int main() {
    // Seed the random number generator
    srand(time(0));
    
    // Generate a random number between 1 and 10
    int secretNumber = rand() % 10 + 1;
    
    int guess;
    int attempts = 0;
    
    std::cout << "Welcome to the Guess the Number game!\n";
    
    // Loop until the user guesses the correct number
    do {
        std::cout << "Enter your guess (between 1 and 10): ";
        std::cin >> guess;
        attempts++;

        // Check if the guess is too high, too low, or correct
        if (guess > secretNumber) {
            std::cout << "Too high! Try again.\n";
        } else if (guess < secretNumber) {
            std::cout << "Too low! Try again.\n";
        } else {
            std::cout << "Congratulations! You guessed the number " << secretNumber << " correctly!\n";
            std::cout << "Number of attempts: " << attempts << "\n";
        }
    } while (guess != secretNumber);
    
    return 0;
}
