/*
 * Name: Eric Mallozzi
 * Student Number: 991242826
 * Class: PROG10111 1209_24301, Fall 2020
 * Date: 2020-10-21
 * Program: Assignment2_Mallozzi.c
 * Description: Sequence Processing.
 * 		Will prompt the user to enter how many integer elements they want
 * 		to enter into an array. Then the user will enter the elements into the
 * 		array. The array will print after the array is populated.
 *      It will then send back information about the array:
 *			the array length, the largest and smallest number, the sum of 
 *			of all the elements, and the average.
 *		The user will then be prompted to enter an integer that will be used
 *		as a key to search in the index. It will prompt the user to earch until
 *		they enter -1. 
 * Sheridan College: Trafalgar Campus
 */
 
#include<stdio.h>

#define SIZE 10

/*
 * Declaring and Defining the called functions.
 * Will be called in the main method once the user enters the necessary 
 * information (the length of elements in the array)
 */

void readInteger(int userArray[], int size); //Function 1

void printArray(int userArray[], int size); //Function 2

void summerizeArray(int userArray[], int size); //Function 3

int searchArray(int userArray[], int key, int size); //Function 4

 
int main(){

	//initializing size of the array
	int size = 0;
	
	//loop to ensure user enters a number between 1 and 10
	do{
		printf("=== Enter the number of the elements (1 - 10): ");
		scanf("%d", &size);
	} while(size < 1 && size > 10);
	
	//initializing array with the size the user entered
	int userArray[size];
	
	//Populating the array
	readInteger(userArray, size);
	
	//Prints the indexes of the array
	printArray(userArray, size);
	
	//Will print the min, max, size, sum, and average of the arrays elements
	summerizeArray(userArray, size);
	
	//Initializing the key that will search the array
	int key = 0;
	
	//Initializing the index of the array that will be searched.
	//if index is -1, will let the user know the key was not found.
	int index = 0;
	
	//Search will loop until the user enters -1
	do{
		
		//prompting the user to enter a number to search
		printf("=== Enter an integer to search, -1 to stop: ");
		scanf("%d", &key);
		
		//if the user entered any number besides the exit number
		if(key != -1){
			
			//sends they array along with the key and size to Function 4
			index = searchArray(userArray, key, size);
			
			//if the key does not match with any number in the array
			if(index == -1){
				
				printf("=== Number %d was not found in the array\n", key);
				
			//if the key matches a number in the array
			} else {
				
				//prints the key and position in the array
				printf("=== Found %d at position %d in the array\n", key, 
					index);
			}
		}
	} while(key != -1);
	
	//Exit Message
	printf("=== Thank you, see you next time!");
	return 0;
}

//Function 1: Reading the integers from the user and placing it into the array
void readInteger(int userArray[], int size){

	//Prompting the user to enter numbers for the array	
	printf("Enter %d integers: ", size);
	
	/* 
	 * for loop to get the integers from the user. Iterates however many times
	 * the user selected as their array size.
	 */
	for(int i = 0; i < size; i++){
		scanf("%d", &userArray[i]);
	}
}

//Function 2: Prints the array in sequence.
void printArray(int userArray[], int size){
	
	printf("=== The current sequence is: ");
	
	//prints the sequence.
	for(int i = 0; i < size; i++){
		
		//prints the array one index at a time
		printf("%d ", userArray[i]);
	}
	
	printf("\n");
}

/*
 * Function 3
 * Will process the array and output the min and max numbers, sum of all the 
 * numbers, and the average of all the numbers
 */
void summerizeArray(int userArray[], int size){
	
	//Initializing max, min, sum, and average
	int max = userArray[0];
	int min = userArray[0];
	int sum = 0;
	double average = 0.0;
	
	//Iterating through the array to gather information
	for(int i = 0; i < size; i++){
		
		//to determine the largest number
		if(max < userArray[i]){
			max = userArray[i];
		}
		
		//to determine the smallest number
		if(min > userArray[i]){
			min = userArray[i];
		}
		
		//Adding each element to get the sum
		sum += userArray[i];
	}
	
	//Casting the average as double using the sum and size of the array
	average = (double)sum/size;
	
	//Printing processed information
	printf("==== Sequence length: %d\n", size);
	printf("==== Sequence max: %d\n",max);
	printf("==== Sequence min: %d\n",min);
	printf("==== Sequence sum: %d\n",sum);
	printf("==== Sequence average: %.2f\n",average);
}


/*
 * Function 4: Searches the array using a key from the user.
 * Returns the index. 
 */
int searchArray(int userArray[], int key, int size){
	
	/*
	 * Initializing index. Will return -1 if the key doesn't match any number
	 * in the array
	 */
	int index = -1;
	
	//For-loop to search for the number
	for(int i = 0; i< size; i++){
		
		//Checking if the key matches.
		if(key == userArray[i]){
			
			//setting the index to i to confirm the number was found
			index = i;
		}
	}
	
	//returning the index to main.
	return index;
}
