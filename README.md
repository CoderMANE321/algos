# algos
List of beginner algos
bubbleSort
linearSearch
binarySearch
selectionSort
recursion
mergesort

/******************************************************************************

 

Welcome to GDB Online.

GDB online is an online compiler and debugger tool for C, C++, Python, Java, PHP, Ruby, Perl,

C#, OCaml, VB, Swift, Pascal, Fortran, Haskell, Objective-C, Assembly, HTML, CSS, JS, SQLite, Prolog.

Code, Compile, Run and Debug online from anywhere in world.

 

*******************************************************************************/

#include <iostream>

 

using namespace std;

 

void linearSearch(int n,int arr[])

{//declare variables

    int target = 10;

    bool found;

    int i;

    //create a loop to iterate through

    for( i = 0; i < n - 1; i++)

    { found = false;

        if (arr[i] = target)

        {

            cout << "Target found: ";

            cout << arr[i];

            found = true;

            break;

        }

        else{

            found = false;

            return;

        }

    }

}

 

 

 

 

int main()

{//declare a array

int arr[] = {1, 2, 4, 10, 7, 9};

//determine sizw

int N =sizeof(arr) / sizeof(arr[0]);

//call for linearSearch

linearSearch( N, arr);

return 0;

 

   

}

 

 

/******************************************************************************

 

Welcome to GDB Online.

GDB online is an online compiler and debugger tool for C, C++, Python, Java, PHP, Ruby, Perl,

C#, OCaml, VB, Swift, Pascal, Fortran, Haskell, Objective-C, Assembly, HTML, CSS, JS, SQLite, Prolog.

Code, Compile, Run and Debug online from anywhere in world.

 

*******************************************************************************/

#include <iostream>

 

using namespace std;

 

 

 

void bubbleSort(int arr[], int n)

{

    //declare variables

    int i,j;

    bool swapped;

    // create  a loop for the first i to be compared

    for (i = 0; i < n - 1; i++) // start defining function

    {

        swapped = false;

        // after declaring if elements have swapped as untrue

        //start another loop to compare elements in the array

        for (j = 0; j < n - i - 1; j++)//after putting j behind i while looping define cases

        {//compare if number behind next element is less than if so switch

            if(arr[j] > arr[j + 1])

            {

                swap(arr[j], arr[j + 1]);

                swapped = true;

            }

        }

        //else array is sorted so break the function

        if (swapped == false)

            break;

    }

}

//now that it's sorted loop through the array

void printArray(int arr[], int size)

{//declare the postion of array

    int i;

    // print each number as you iterate though postions of array

    for(i = 0; i < size; i++)

        cout << " " << arr[i];

   

}

 

int main()

{// declare a array of numbers

    int arr[] = { 64, 34, 25, 12, 22, 11, 90 };

    // determine the size of array by taking the first element[0] and diving by total

    int N = sizeof(arr) / sizeof(arr[0]);

    //call the bubbleSort function to perform tasks

    bubbleSort(arr,N);

    //print out the statement

    cout << "Sorted array: \n";

    // print out array

    printArray(arr, N);

    return 0;

   

}

_________

binary_search 

#include <iostream>
using namespace std;

//must be sorted!

//define a function calling array, left half,right half, and target
int binary_search(int arr[], int l, int r, int x)
{
    while (l <= r)
    {// create a midpoint by adding left half and right which - 1 since array starts at 0 then divide it in two sections
       int m = l + (r - l) / 2;
       // now if x is at midpoint during split stop and return value
       if (arr[m] == x)
        {
            return m;
            
        }
        if (arr[m] < x)
        {
            l = m + 1;
        }
        else 
        {
            r = m - 1;
           
        }
    
    }
    // anything else reutrn as not present
    return -1;
}

int main(void)
{
    //create an array
    int arr[] = {1, 2, 5, 7 ,40};
    // target
    int x = 7;
    // create array using full length and divide by first element
    int n = sizeof(arr) / sizeof(arr[0]);
    //call function with params
    int result = binary_search(arr, 0, n - 1, x);
   if (result == -1)
    {
        cout << "Element not found" << endl;
    }
    else
    {
        cout << "Element found at index " << result << endl;
    }

    return 0;

}





_________
Selection sort 
#include <bits/stdc++.h>
using namespace std;
 
 
 //create a function 
 void selectionSort(int arr[], int n)
 {  //declare variables
    int i, j, minimium_index;
    
    //loop, # i is behind j
    for (i = 0; i < n - 1; i++) 
    {
        //find minimium_index
        minimium_index = i;
        //for second element
        for (j = i + 1; j < n; j++)
        {   // if element in front is less than
            if (arr[j] < arr[minimium_index])
            {
                // new minimium_index is j
                minimium_index = j;
            }
            
        }
        // if minimium_index not equal to i store element
        if (minimium_index != i)
        {
            swap(arr[minimium_index], arr[i]);
        }
    }
 }
 
 void printArray(int arr[], int size) 
 {
    int i;
    for (i = 0; i < size; i++) {
        cout << arr[i] << " ";
        cout << endl;
    }
 }
 
 int main()
{
    int arr[] = { 64, 25, 12, 22, 11 };
    int n = sizeof(arr) / sizeof(arr[0]);
 
    // Function Call
    selectionSort(arr, n);
    cout << "Sorted array: \n";
    printArray(arr, n);
    return 0;
}
 

 
_________
recursion
#include <bits/stdc++.h>
using namespace std;
 
//declare poles
void poles( int n, char sourcePole, char destiPole, char auxPole)
{
    //base case
    if(0 == n)
        return;
        
    
    //move disk 1 over 
    poles(n - 1, sourcePole, auxPole, destiPole);
    
    //describe poles movement
    
    cout << "Move the disk " << n << "\tfrom " << sourcePole << " " << "to" <<  " " << destiPole << endl;
    
    //move now source(auxPole) to destiPole replacing source as aux 
    poles(n - 1, auxPole, destiPole, sourcePole);
    
}

int main()
{
    poles(4, 's', 'd', 'a');
    return 0;
}
