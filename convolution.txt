#include <iostream>
using namespace std;
int main()
{
    int * array1; // X[n] array pointer declaration 
    int * array2; // H[n] array pointer declaration

    int size1, size2;

    cout << "Enter the size of X[n]: ";     // size of X[n] array input 
    cin >> size1;

    array1 = new int[size1];

    cout<<"Enter the size of H[n]: ";      // size of H[n] array input
    cin>>size2;

    array2 = new int[size2]; 

    cout<<"Enter the values of X[n]: ";
    //get size of array1

    for(int i=0;i< size1 ;i++)  // X[n] array input
    {
        cin>>array1[i];
    }

    cout<<"Enter the values of H[n]: ";
    //get size of array2
    for(int i=0;i< size2 ;i++) // H[n] array input
    {
        cin>>array2[i];
    }

    // convolution starts here
    int size3 = size1 + size2 - 1; // size of Y[n] array
    int * array3 = new int[size3]; // Y[n] array pointer declaration

    for(int i=0;i<size3;i++) // Y[n] array initialization
    {
        array3[i]=0;
    }

    for(int i=0;i<size1;i++) // convolution operation
    {
        for(int j=0;j<size2;j++)
        {
            array3[i+j] = array3[i+j] + array1[i]*array2[j];
        }
    }

    // convolution ends here

    for(int i=0;i<size3;i++) // Y[n] array output
    {
        cout<<array3[i]<<" ";
    }

    
}