Three way Partitioning of an Array around a Given Range in C++
 

Here, in this page we will discuss the program for Three way partitioning of an array around a given range in C++ programming language. We are given with an array and a range say [low, high], we need to partition the array in such a way,

All the elements less than low value, should come first.
Elements between the low and high value come in middle.
All elements greater than high should come at the last.
Three way Partitioning of an Array around a Given Range in C++
Method 1 :
Take the size of the array from the user and store it in variable say n.
Now, declare an array of n size and take n elements of the array from the use.
Now, take the lower limit and upper limit of the range from the user and store them in variable say low and high respectively.
Now, sort the array after sorting the array got partitioned.
Note : By this algorithm the order of the array can’t be maintained.

Time and Space Complexities :
Time-Complexity : O(nlogn)
Space-Complexity : O(1)
Partitioning of array
Code for Three way Partitioning of an Array around a given Range in C++
Run
#include<bits/stdc++.h>
using namespace std;
int main(){

  int n;
  cin>>n;

  int a[n];
  for(int i=0; i<n; i++) cin>>a[i];

  int low, high;
  cin>>low>>high;

  sort(a, a+n);

  for(int i=0; i<n; i++)
  cout<<a[i]<<" ";

}
Input :
10
2 89 34 16 17 10 11 78 30 19
15 20

Output :
2 10 11 16 17 19 30 34 89 78
While loop in C
Related Pages
Given an array which consists of only 0, 1 and 2

Move all the negative elements to one side of the array

Minimum no. of Jumps to reach the end of an array 

Find Largest sum contiguous Subarray

Minimize the maximum difference between heights 

Method 2 :
Take the size of the array from the user and store it in variable say n.
Now, declare an array of n size and take n elements of the array from the use.
Now, take the lower limit and upper limit of the range from the user and store them in variable say low and high respectively.
Call getPartition function, in that function pass the array, size and low and high value of the range.
In the getPartition function,
Declare two pointer one is ptr1 set at 0 index and another is ptr2 set at last index i.e, n-1.
Now, traverse the array till i<=ptr2.
Check if current value is lower than low value than swap it with ptr1 pointing value, and increase the value of ptr1 and i.
Else if current value is greater than high than swap it with ptr2 value, and decrease the value of ptr2 .
Otherwise increase the value of i.
Time and Space Complexities :
Time-Complexity : O(n)
Space-Complexity : O(1)
Code for Three way Partitioning of an Array around a given Range in C++
Run
#include<bits/stdc++.h>
using namespace std;
void getPartition(int a[], int n, int low, int high)
{
   int ptr1 = 0, ptr2 = n-1;
   for (int i=0; i<= ptr2;)
   {
      if (a[i] < low) swap(a[i++], a[ptr1++]); else if (a[i] > high)
      swap(a[i], a[ptr2--]);
      else
      i++;
    }
}

int main(){

  int n;
  cin>>n;

  int a[n];
  for(int i=0; i<n; i++) cin>>a[i];

  int low, high;
  cin>>low>>high;

  getPartition(a, n, low, high);

  for(int i=0; i<n; i++)
  cout<<a[i]<<" ";

}
Input :
10
2 89 34 16 17 10 11 78 30 19
15 20

Output :
2 10 11 16 17 19 30 34 89 78
