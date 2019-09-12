//# Adventure-1
Homework assignment in C++ working with loops//

#include <iostream>
#include <cstdlib>
#include <ctime>
#include <chrono>
#include <thread>

using namespace std;

int main() {
  srand(time(0));	
	int sanity = 10;
	int psy_Attack;
	int psy_Block;
	int counter = 1;

	cout << "You awaken to the sound of a meteor crashing into the woods near your home.\n";
	cout << "Putting on clothes you venture outside to investigate.\n";
	cout << "You feel a dark presence futher into the Woods.\n\n";


	while(	sanity >= 0 && counter <= rand() % 6 + 1 ) {

		cout << "You go deeper into the woods\n\n";
		counter++;

		std::this_thread::sleep_for(chrono::milliseconds(5000));


		int encounter = rand() % 4;
		cout << "Something comes out of the woods!\n"; 
		switch (encounter){
			case 0:
				cout << "A malshaped wolf the size of a horse\n";
				cout << "A MUTANT DIREWOLF CHAGRGES!\n";
				break;
			case 1:
				cout << "A strange undead zombie\n";
				cout << "A WEIDERGANER COMES FORWARD!\n";
				break;
			case 2: 
				cout << "A mass of aberrational horror\n";
				cout << "A FOULSPAWN SLITHERS OUT!\n";
				break;
			}
			cout << "You prepare your psycic defenses.\n";

			psy_Attack = rand() % 5; 
			psy_Block = rand() % 5;
			if (psy_Attack <= psy_Block) {
			cout << "You defend against the attack of the monster and escape\n\n"; 

			std::this_thread::sleep_for(chrono::milliseconds(5000));

			} else { 
			sanity =	sanity - psy_Attack;
			cout << "You are damaged by the monster. Your sanity has " <<	sanity << " points left \n\n";

			std::this_thread::sleep_for(chrono::milliseconds(5000));

			}
			}
		if(sanity <= 5){
			cout << "You feel the weight of the madness in these woods press down on you\n";
			cout << "You feel like you should go home but press on\n";
			}

		if	(sanity > 0){
			cout << "You find the heart of the meteor. It calls you forward.\n";
			cout << "You wake up in your bed, was that all a dream?\n";
			}

		else {
			cout << "You feel something break in your mind.\n";
			cout << "You wander into the darkest parts of the woods forever lost\n"; 
			return - 1;
		}
}



/*welcome the player
set up the game
    int health = 10, attack, block, turns = 0
    seed the random number generator
start the loop
    add 1 to turns
    start the encounter
        randomly generate numbers for attack (range = 0-4) and block (range = 0-4)
        if block is greater or equal to attack, successful block
        otherwise, subtract attack value from health.
keep looping while health is greater than zero and fewer than 4 turns have happened

if health is greater than 0, congratulate player
otherwise, tell the player they're dead. */
