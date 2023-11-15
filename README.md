# rock-paper-scissors-game
#include <iostream>
#include <array>
#include <cmath>
#include <vector>
#include <random>
using namespace std;

int main()
{
    array<int, 12> computer_choice {2, 1, 0, 1, 0, 2, 0, 1, 2, 0, 1, 2};
    array<int, 3> user_choice {0, 1, 2};
    bool play_again = true;
    int user_wins = 0;
    int comp_wins = 0;
    cout << "------------Welcome you to rock-paper-sciccors game-------------" <<endl;
    
    while(play_again)
    {
        std::random_device vinh;
        std::mt19937 gen(vinh());
        std::uniform_int_distribution<> dis(0, 2);
        int computer_index = dis(gen);
        
        cout << "Let's play this game right now" << endl;
        while(true)
        {
            int computer = computer_choice[computer_index];
            cout << "Enter your choice (0 for rock, 1 for papers, 2 for scissors): ";
            int user_choice;
            cin >> user_choice;
            cout << "You chose: ";
            if(user_choice == 0)
            {
                cout << "rock";
            }  
            else if(user_choice == 1)
            {
                cout << "paper";
            }
            else if(user_choice == 2)
            {
                cout << "scissors";
            }
            else{
                cout << "Invalid choice! Choice again. " <<endl;
                continue;
            }
            cout << " , and the computer chose: ";
            if(computer == 0)
            {
                cout << "rock";
            }
            else if(computer == 1)
            {
                cout << "paper";
            }
            else if(computer == 2)
            {
                cout << "scissors";
            }
            cout << endl;
            if(user_choice == 0){
                if(computer == 1){
                    cout << " You lose " << endl;
                    comp_wins++;
                    break;
                }
                else if(computer == 2){
                    cout << " You win " <<endl;
                    user_wins++;
                    break;
                }
                else{
                    cout << "It's a tie. Play again. " <<endl;
                }
            }
            if(user_choice == 1){
                if(computer == 0){
                    cout << " You win " << endl;
                    user_wins++;
                    break;
                }
                else if(computer == 2){
                    cout << " You lose " <<endl;
                    comp_wins++;
                    break;
                }
                else{
                    cout << "It's a tie. Play again. " <<endl;
                }
            }
            if(user_choice = 2){
                 if(computer == 0){
                    cout << " You lose " << endl;
                    comp_wins++;
                    break;
                }
                else if(computer == 1){
                    cout << " You win " <<endl;
                    user_wins++;
                    break;
                }
                else{
                    cout << "It's a tie. Play again. " <<endl;
                }
            }
           
        }
        cout << "You have won " << user_wins << " times, " << "Computer has won " << comp_wins << " times.";
        cout << "Do you want to continue ? Yes or No?"<<endl;
        char decision;
        cin >> decision;
        play_again = (decision == 'Y' || decision == 'y');
        
        
        
    }

    
    return 0;
}

