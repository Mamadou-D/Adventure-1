# Adventure-1
Small Role-Playing Game !   

Hi,
i am Mamadou DOUMBIA, majoring in computer Science at Butler community college.
I have made an assignment which talks about a Role-Playing Game using a seed random number generator
and some other command such as conditions if statement, DO/WHILE statement and some incrementation.  


#include <iostream>
#include <cstdlib>
#include <ctime>
#include <windows.h>

using namespace std;

int main()
{
    int health = 10 , attack, block;

srand(time(0));
    Sleep(1000);
    cout << "Welcome to Role-Playing Game (RPG) !! " << endl;
    Sleep(2000);
    cout << "Let's begin the fight" <<endl;
    do {
            // I used an integer turn as an iterator, because "code blocks " take it as a command.
           int turn =1;

           while (turn <= 4){
                // Attack, and block point will randomly be set to 0-4 !
            attack = (rand()%5);
            block = (rand()%5);

           /* As a Role-playing game, I have added sleep command to help each statement
           to be executed according to the number of second before. Sleep(3000) = 3s !!
           */
            Sleep(3000);

            // Turn shows off number of turn we have
            cout << "\nTurn:\t" <<turn << endl;

           if (block >= attack){
                Sleep(2000);
                cout << "Successful block !!" << endl;
                Sleep(2000);
             cout << "Player's health:\t" << health <<" PH" <<endl;
            } else {
            health = health - attack;
           Sleep(2000);
             cout << "Player's health:\t" << health <<" PH" << endl;
             Sleep(2000);
            }
            turn ++;
            // I used break to terminate the loop right away whenever health (PH) <= 0 ;
            if (health <= 0){
                break;
            }
            }

   }  while (health > 0 && health <0);

   /* I have used nesting here because I've wanted the program to print out either "congratulations"
   if the player's health >5 and "go seeing a doctor for full recovery" when health <0 && health >=5.
   */
   if (health > 0 ){
        if (health <= 5){
        cout << "\n\t°Congratulations !!°" << endl;
        Sleep(2000);
        cout << "\tGo seeing a doctor for full recovery !!" <<endl;
        }else {
        cout << "\n°Congratulations !!°" << endl;
        Sleep(2000);
        }
    }else {
    cout << "\n\t° YOU ARE DEAD !!°" <<endl;
    }

    return 0;
}



/*welcome the player
set up the game
    int health = 10, attack, block, iterator
    seed the random number generator
start the loop
    add 1 to the iterator
    start the encounter
        randomly generate numbers for attack (range = 0-4) and block (range = 0-4)
        if block is greater or equal to attack, successful block
        otherwise, subtract attack value from health.
keep looping while health is greater than zero and fewer than 4 turns have happened

if health is greater than 0, congratulate player
otherwise, tell the player they're dead.
*/
