# githubTest
#include <iostream>

using namespace std;

int tealeaves;
int sunflowers;
int toadstools;
int pineNeedles;
int magicPotion(int& tea, int& sun, int& toad, int& pine) {
    int magicPotions = 0;
    while(tea >= 3 && sun >= 3 && toad >= 10 && pine >= 1) {
        magicPotions++;
        tea -= 3;
        sun -= 3;
        toad -= 10;
        pine -= 1;
    }
    return magicPotions;
}

int healthPotion(int& tea, int& sun, int& toad, int& pine) {
    int healthPotions = 0;
    while(tea >= 6 && sun >= 1 && toad >= 5 && pine >= 2) {
        healthPotions++;
        tea -= 6;
        sun -= 1;
        toad -= 5;
        pine -= 2;
    }
    return healthPotions;
}

int main() {
    int potionType;
    int tealeaves;
    int sunflowers;
    int toadstools;
    int pineNeedles;

    cout << "Select a potion crafting priority: \n1. Health Potion \n2. Magic Potion" << endl;
    cin >> potionType;

    while(potionType != 1 && potionType != 2) {
        cout << "Invalid input. Please select 1 or 2." << endl;
        cin >> potionType;
    }
    cout << "How many Tealeaves do you have?" << endl;
    cin >> tealeaves;
    while(tealeaves < 0) {
        cout << "Invalid input. Please enter a non-negative integer." << endl;
        cout << "How many Tealeaves do you have?" << endl;
        cin >> tealeaves;
    }
    cout << "How many Sunflowers do you have?" << endl;
    cin >> sunflowers;
    while(sunflowers < 0) {
        cout << "Invalid input. Please enter a non-negative integer." << endl;
        cout << "How many Sunflowers do you have?" << endl;
        cin >> sunflowers;
    }
    cout << "How many Toadstools do you have?" << endl;
    cin >> toadstools;
    while(toadstools < 0) {
        cout << "Invalid input. Please enter a non-negative integer." << endl;
        cout << "How many Toadstools do you have?" << endl;
        cin >> toadstools;
    }
    cout << "How many Pine Needles do you have?" << endl;
    cin >> pineNeedles;
    while(pineNeedles < 0) {
        cout << "Invalid input. Please enter a non-negative integer." << endl;
        cout << "How many Pine Needles do you have?" << endl;
        cin >> pineNeedles;
    }
    int healthCount;
    int magicCount;

    switch (potionType) {
        case 1:
            healthCount = healthPotion(tealeaves, sunflowers, toadstools, pineNeedles);
            magicCount = magicPotion(tealeaves, sunflowers, toadstools, pineNeedles);
            cout << "You can make " << healthCount << " Health potion(s) and " << magicCount << " Magic potion(s)." << endl;
            break;
        case 2:
            magicCount = magicPotion(tealeaves, sunflowers, toadstools, pineNeedles);
            healthCount = healthPotion(tealeaves, sunflowers, toadstools, pineNeedles);
            cout << "You can make " << magicCount << " Magic potion(s) and " << healthCount << " Health potion(s)." << endl;
            break;
    }

    return 0;

}