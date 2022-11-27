# daaa

Practical:1
 
Write a program to sort given elements of an array in ascending order using bubble sort. Analyze the time complexity for best, average, and worst case. 
#include<stdio.h> #include<math.h> void swap(int *a,int *b){ 
int temp=*a; *a=*b; 
*b=temp; 
} 
void BubbleSort(int arr[],int n) 
{ int i,j; 
for(i=0;i<n-1;i++){ 
for ( j = 0; j <n-i-1; j++) 
{ 
if (arr[j]>arr[j+1]) 
{ 
swap(&arr[j],&arr[j+1]); 
} 
 
} 
 
} 
 
} 
void print_array(int arr[],int n){ int i; 
for(i=0;i<n;i++){ 
printf("%d ",arr[i]); 
 
} 
} 
void main(){ 
int arr[]={5,8,1,9,6,22,11,95,2}; 
int n=sizeof(arr)/sizeof(arr[0]); 
 
BubbleSort(arr,n); print_array(arr,n); 
 
} 
 
   
Time Complexity of Bubble Sort 
 
Best case 	Average case 	Worst case 
Ω(n) 	θ(n^2) 	O(n^2) 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 

Practical:2
 
Write a program to sort given elements of an array in ascending order using selection sort. Analyze the time complexity for best, average and worst case. 
// C program for implementation of selection sort 
#include <stdio.h> 
 
void swap(int *xp, int *yp) 
{ 
int temp = *xp; *xp = *yp; 
*yp = temp; 
} 
 
void selectionSort(int arr[], int n) 
{ 
int i, j, min_idx; 
 
for (i = 0; i < n-1; i++) 
{ 
 
min_idx = i; for (j = i+1; j < n; j++) if (arr[j] < arr[min_idx]) min_idx = j; 
 
 
if(min_idx != i) swap(&arr[min_idx], &arr[i]); 
} 
} 
 
 
void printArray(int arr[], int size) 
{ 
int i; 
for (i=0; i < size; i++) printf("%d ", arr[i]); 
printf("\n"); 
} 
int main() 
{ 
int arr[] = {20,40,06,17,99,22,987,01,10};                  int n = sizeof(arr)/sizeof(arr[0]); selectionSort(arr, n); printf("Sorted array: \n"); 
                 
printArray(arr, n); return 0; 
} 
 
 
 
 
 
 
 
Time Complexity of Selection Sort 
 
Best case 	Average case 	Worst case 
Ω(n^2) 	θ(n^2) 	O(n^2) 
 
 
 
 
 
 
 
 
 
 
 
 
 

 
 
Practical:3
 
Write a program to implement heap sort. 
 
// Heap Sort in C #include <stdio.h> 
void swap(int* a, int* b) 
{ 
 
int temp = *a; *a = *b; 
*b = temp; 
} 
void heapify(int arr[], int N, int i) 
{ int largest = i; 
 
int left = 2 * i + 1; int right = 2 * i + 2; 
 
if (left < N && arr[left] > arr[largest]) largest = left; if (right < N && arr[right] > arr[largest]) largest = right; if (largest != i) { swap(&arr[i], &arr[largest]); 
heapify(arr, N, largest); 
} 
} 
 
void heapSort(int arr[], int N) 
{ 
 
for (int i = N / 2 - 1; i >= 0; i--) heapify(arr, N, i); 
for (int i = N - 1; i >= 0; i--) { 
 
swap(&arr[0], &arr[i]); 
heapify(arr, i, 0); 
} 
} 
 
 
void printArray(int arr[], int N) 
{ for (int i = 0; i < N; i++) printf("%d ", arr[i]); 
printf("\n"); 
} 
 
int main() 
{ 
int arr[] = {20,5,100,9,40,9,50,60,5}; int N = sizeof(arr) / sizeof(arr[0]); 
 
 
heapSort(arr, N); printf("Sorted array is\n"); printArray(arr, N); 
} 
 
 
 
 
 
 
 
Time Complexity of Heap Sort 
 
Best case 	Average case 	Worst case 
Ω(n log(n)) 	θ(n log(n)) 	O(n log(n)) 
 
 
 
 
 
 
 
 
 
 
Practical:4
 
Write a program to search given element from an array using sequential search and binary search. Analyze the time complexity for best, average and worst case. 
 
Linear Search 
 
// C program for Indexed Sequential Search 
#include <stdio.h> 
#include <stdlib.h> 
 
void indexedSequentialSearch(int arr[], int n, int k) {     int GN = 3; 
    int elements[GN], indices[GN], i, set = 0; 
    int j = 0, ind = 0, start, end; 
    for (i = 0; i < n; i += 3) 
    { 
 
        elements[ind] = arr[i]; 
 
        indices[ind] = i;         ind++; 
    } 
    if (k < elements[0]) 
    { 
        printf("Not found"); 
        exit(0); 
    }     else 
    { 
 
        for (i = 1; i <= ind; i++) 
            if (k <= elements[i]) 
            { 
                start = indices[i - 1];                 end = indices[i]; 
                set = 1;                 break; 
            } 
    } 
    if (set == 0) 
    { 
        start = indices[GN - 1];         end = GN; 
    } 
    for (i = start; i <= end; i++) 
    { 
        if (k == arr[i]) 
        {             j = 1; 
            break; 
        } 
    } 
    if (j == 1) 
 
        else 
} 
 
void main() 
{ 
 
    printf("Found at index %d", i);     printf("Not found"); 
 
    int arr[] = {6, 7, 8, 9, 10, 11, 12, 13, 14, 
15}; 
    int n = sizeof(arr) / sizeof(arr[0]);     int k = 8; 
    indexedSequentialSearch(arr, n, k); 
} 
 
 
 
 
 
 
 Time Complexity of Sequential Search 
 
Best case 	Average case 	Worst case 
O(1) 	O(n) 	O(n) 
 
 
 
 
 
 
Binary Search 
 
#include <stdio.h> 
int binarySearch(int a[], int beg, int end, int val) 
{ 
int mid; if(end >= beg) 
{  	mid = (beg + end)/2; if(a[mid] == val) 
{ 
return mid+1; 
} 
else if(a[mid] < val) 
{ 
return binarySearch(a, mid+1, end, val); 
} else 
{ 
return binarySearch(a, beg, mid-1, val); 
} 
} 
return -1; 
} 
int main() { int a[] = {11, 14, 25, 30, 40, 41, 52, 57, 70}; int val = 40; int n = sizeof(a) / sizeof(a[0]); int res = binarySearch(a, 0, n-1, val); printf("The elements of the array are - "); 
for (int i = 0; i < n; i++) printf("%d ", a[i]); 
printf("\nElement to be searched is - %d", val); if (res == -1) 
printf("\nElement is not present in the array"); else 
printf("\nElement is present at %d position of array", res); return 0; 
} 
 
 
 
 
 
 
 
 Time Complexity of Binary Search 
 
Best case 	Average case 	Worst case 
Ω(1) 	θ(logn) 	O(logn) 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 


 
 
 
 
Practical:5 
 
Write a program to sort given elements of an array in ascending order using merge sort. Analyze the time complexity for best, average and worst case. 
 
/* C program for Merge Sort */ 
#include <stdio.h> 
#include <stdlib.h> 
 
void merge(int arr[], int l, int m, int r) 
{ 
int i, j, k; 
int n1 = m - l + 1; 
int n2 = r - m; 
 int L[n1], R[n2]; 
 
for (i = 0; i < n1; i++) 
L[i] = arr[l + i]; for (j = 0; j < n2; j++) 
R[j] = arr[m + 1 + j]; 
 
i = 0; j = 0; k = l; 
while (i < n1 && j < n2) { 
if (L[i] <= R[j]) { arr[k] = L[i]; i++; 
	} 	 
else { 
 	arr[k] = R[j]; 
j++; 
} 
k++; 
} 
 
while (i < n1) { arr[k] = L[i]; i++; 
k++; 
} 
 
while (j < n2) { arr[k] = R[j]; 
j++; 
 
k++; 
} 
} 
 
void mergeSort(int arr[], int l, int r) 
{ if (l < r) { 
 int m = l + (r - l) / 2; 
 
mergeSort(arr, l, m); mergeSort(arr, m + 1, r); 
 
merge(arr, l, m, r); 
} 
} 
 
void printArray(int A[], int size) 
{ int i; for (i = 0; i < size; i++) printf("%d ", A[i]); 
printf("\n"); 
} 
 
int main() 
{ int arr[] = { 12, 11, 13, 5, 6, 7 }; int arr_size = sizeof(arr) / sizeof(arr[0]); 
 
printf("Given array is \n"); printArray(arr, arr_size); 
 
mergeSort(arr, 0, arr_size - 1); 
 
printf("\nSorted array is \n"); printArray(arr, arr_size); return 0; 
} 
 
 
 
 
 
 
Time Complexity of merge sort 
 
Best case 	Average case 	Worst case 
Ω(n log(n)) 	θ(n log(n)) 	O(n log(n)) 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
  
Practical:6
 
sort given elements of an array in ascending order using 
quick sort. Analyze the time complexity for best, average and worst case. 
 
#include <stdio.h> 
void quicksort(int number[25], int first, int last) 
{ 
 
int i, j, pivot, temp; 
 
if (first < last) 
{ 
 
pivot = first; i = first; 
j = last; 
 
while (i < j) 
{ 
 
while (number[i] <= number[pivot] && i < last) i++; while (number[j] > number[pivot]) 
j--; 
if (i < j) 
{ 
 
temp = number[i]; number[i] = number[j]; 
number[j] = temp; 
} 
} 
 
temp = number[pivot]; number[pivot] = number[j]; number[j] = temp; quicksort(number, first, j - 1); 
quicksort(number, j + 1, last); 
} 
} 
 
int main() 
{ 
 
int i, count, number[25]; 
 
printf("Enter some elements (Max. - 25): "); scanf("%d", &count); printf("Enter %d elements: ", count); for (i = 0; i < count; i++) scanf("%d", &number[i]); quicksort(number, 0, count - 1); printf("The Sorted Order is: "); for (i = 0; i < count; i++) 
printf(" %d", number[i]); 
 
return 0; 
} 
 
 
 
 
Time Complexity of Quick sort 
 
Best case 	Average case 	Worst case 
Ω(n log(n)) 	θ(n log(n)) 	O(n^2) 
 
 
 


















 


Practical:7
 
implement making change problem using greedy algorithm. 

// C program to find minimum number of denominations 
#include <stdio.h> 
#define COINS 10 
#define MAX 20 
 
int coins[COINS] = { 1, 2, 5, 10, 20, 50, 100, 200,500, 2000 }; 
 
void findMin(int cost) 
{ 
int coinList[MAX] = { 0 }; 
int i, k = 0; 
 
for (i = COINS - 1; i >= 0; i--) { while (cost >= coins[i]) { cost -= coins[i]; // Add coin in the list coinList[k++] = coins[i]; 
} 
} 
 
for (i = 0; i < k; i++) { printf("%d ", coinList[i]); 
} 
return; 
} 
 
int main(void) 
{ 
// input value int n = 1582; 
 
printf("Following is minimal number" 
"of change for %d: ",n); findMin(n); 
return 0; 
} 
 
 
 
 
 
 
Time Complexity: O(V). 
Auxiliary Space: O(V). 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
Practical:8
 
implement the knapsack problem using greedy algorithm. 
#include <stdio.h> 
 
void knapsack(int n, float weight[], float profit[], float capacity) 
{ 
    float x[20], tp = 0;     int i, j, u; 
    u = capacity; 
 
    for (i = 0; i < n; i++)         x[i] = 0.0; 
 
    for (i = 0; i < n; i++) 
    { 
        if (weight[i] > u)             break;         else         {             x[i] = 1.0;             tp = tp + profit[i];             u = u - weight[i]; 
        } 
    } 
 
    if (i < n) 
        x[i] = u / weight[i]; 
 
    tp = tp + (x[i] * profit[i]); 
 
    printf("\nThe result vector is:- "); 
    for (i = 0; i < n; i++) 
        printf("%f\t", x[i]); 
 
    printf("\nMaximum profit is:- %f", tp); 
} 
 
int main() 
{ 
    float weight[20], profit[20], capacity; 
    int num, i, j;     float ratio[20], temp; 
 
    printf("\nEnter the no. of objects:- ");     scanf("%d", &num); 
 
    printf("\nEnter the wts and profits of each object:- "); 
    for (i = 0; i < num; i++) 
    { 
        scanf("%f %f", &weight[i], &profit[i]); 
    } 
 
    printf("\nEnter the capacityacity of knapsack:- ");     scanf("%f", &capacity); 
 
    for (i = 0; i < num; i++) 
    { 
        ratio[i] = profit[i] / weight[i]; 
    } 
 
    for (i = 0; i < num; i++) 
    { 
        for (j = i + 1; j < num; j++) 
        { 
            if (ratio[i] < ratio[j]) 
            { 
                temp = ratio[j];                 ratio[j] = ratio[i];                 ratio[i] = temp; 
 
                temp = weight[j];                 weight[j] = weight[i]; 
                weight[i] = temp; 
 
                temp = profit[j];                 profit[j] = profit[i]; 
                profit[i] = temp; 
            } 
        } 
    } 
 
    knapsack(num, weight, profit, capacity); 
    return (0); 
} 
  
 




Complexity Analysis: 
 
Time Complexity: O(N*W). 
 Auxiliary     Space: O(2*W) 

Practical:9 
 
Write a program to implement making change problem using dynamic programming. 
 
#include <bits/stdc++.h> using namespace std; 
 
int count(int coins[], int n, int sum) 
{ 
 
if (sum == 0) 
return 1; 
 
if (sum < 0) 
return 0; 
 
if (n <= 0) 
return 0; 
 
return count(coins, n - 1, sum) 
+ count(coins, n, sum - coins[n - 1]); 
} 
 
int main() 
{ int i, j; 
int coins[] = { 1, 2, 3 }; 
int n = sizeof(coins) / sizeof(coins[0]); int sum = 4; cout << " " << count(coins, n, sum); 
return 0; 
} 
 
 
 
 
Time Complexity: O(2sum) 
Auxiliary Space: O(target) 




















Practical:10
 
Write a program to implement the knapsack problem using dynamic programming. 
#include <bits/stdc++.h> 
using namespace std; 
 
int max(int a, int b) 
{ return (a > b) ? a : b; 
} 
 
int knapSack(int W, int wt[], int val[], int n) 
{ int i, w; 
vector<vector<int>> K(n + 1, vector<int>(W + 1)); 
 
// Build table K[][] in bottom up manner 
for(i = 0; i <= n; i++) 
{ 
for(w = 0; w <= W; w++) 
{ if (i == 0 || w == 0) 
K[i][w] = 0; else if (wt[i - 1] <= w) 
K[i][w] = max(val[i - 1] + 
K[i - 1][w - wt[i - 1]], 
K[i - 1][w]); 
else 
K[i][w] = K[i - 1][w]; 
} 
} 
return K[n][W]; 
} 
 
int main() 
{ int val[] = { 60, 100, 120 }; int wt[] = { 10, 20, 30 }; 
int W = 50; 
int n = sizeof(val) / sizeof(val[0]); cout << knapSack(W, wt, val, n); 
return 0; 
} 
 
 
  
 
 
 
Complexity Analysis: 
 
Time Complexity: O(N*W). 
where ‘N’ is the number of weight element and ‘W’ is capacity. As for every weight element we traverse through all weight capacities 1<=w<=W. 
Auxiliary Space: O(N*W). 
The use of 2-D array of size ‘N*W’. 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 

 
Practical:11
  
Write a program to implement Floyd’s algorithm for finding shortest path using dynamic programming. 
class FloydWarshall { 
final static int INF = 9999, nV = 4; void floydWarshall(int graph[][]) { 
int matrix[][] = new int[nV][nV]; 
int i, j, k; 
 
for (i = 0; i < nV; i++) 
for (j = 0; j < nV; j++) 
matrix[i][j] = graph[i][j]; 
 
// Adding vertices individually for (k = 0; k < nV; k++) { for (i = 0; i < nV; i++) { 
for (j = 0; j < nV; j++) { 
if (matrix[i][k] + matrix[k][j] < matrix[i][j]) 
matrix[i][j] = matrix[i][k] + matrix[k][j]; 
} 
} 
} 
printMatrix(matrix); 
} 
 
void printMatrix(int matrix[][]) { 
for (int i = 0; i < nV; ++i) { for (int j = 0; j < nV; ++j) { if (matrix[i][j] == INF) System.out.print("INF "); 
else 
System.out.print(matrix[i][j] + " "); 
} 
System.out.println(); 
} 
} 
 
public static void main(String[] args) { 
int graph[][] = { { 0, 3, INF, 5 }, { 2, 0, INF, 4 }, { INF, 1, 0, INF }, { INF, INF, 2, 0 } }; FloydWarshall a = new FloydWarshall(); a.floydWarshall(graph); 
} 
} 
 
  
 
 
 
 
 
Time Complexity 
There are three loops. Each loop has constant complexities. So, the time complexity of the Floyd-Warshall algorithm is O(n3). 
Space Complexity 
The space complexity of the Floyd-Warshall algorithm is O(n2). 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 

Practical:12
 
Write a program to implement chained matrix multiplication using dynamic programming 
 
 
#include <bits/stdc++.h> using namespace std; int dp[100][100]; 
int matrixChainMemoised(int* p, int i, int j) 
{ if (i == j) 
{ 
return 0; 
} 
if (dp[i][j] != -1) 
{ 
return dp[i][j]; 
} 
dp[i][j] = INT_MAX; for (int k = i; k < j; k++) 
{ 
dp[i][j] = min( dp[i][j], matrixChainMemoised(p, i, k) 
+ matrixChainMemoised(p, k + 1, j) + p[i - 1] * p[k] * p[j]); 
} 
return dp[i][j]; 
} 
int MatrixChainOrder(int* p, int n) 
{ 
int i = 1, j = n - 1; 
return matrixChainMemoised(p, i, j); 
} 
 
// Driver Code 
int main() 
{ 
int arr[] = { 1, 2, 3, 4 }; int n = sizeof(arr) / sizeof(arr[0]); memset(dp, -1, sizeof dp); 
 
cout << "Minimum number of multiplications is " 
<< MatrixChainOrder(arr, n); 
} 
 
 
 
 
 
 
  
 
 
Time Complexity: O(N3 ) 
Auxiliary Space: O(N2) ignoring recursion stack space 
 
 
 
 
 
 
 
 
 
 
 
 
 

Practical:13 
 
Write a program to implement longest common subsequence using dynamic programming. 
#include <iostream> using namespace std; 
 
void lcsAlgo(char *S1, char *S2, int m, int n) { 
int LCS_table[m + 1][n + 1]; for (int i = 0; i <= m; i++) { for (int j = 0; j <= n; j++) { if 
(i == 0 || j == 0) 
LCS_table[i][j] = 0; else if (S1[i - 1] == S2[j - 1]) 
LCS_table[i][j] = LCS_table[i - 1][j - 1] + 1; else 
LCS_table[i][j] = max(LCS_table[i - 1][j], LCS_table[i][j - 1]); 
} 
} 
 
int index = LCS_table[m][n]; char lcsAlgo[index + 1]; lcsAlgo[index] = '\0'; 
 
int i = m, j = n; while (i > 0 && j > 0) { 
if (S1[i - 1] == S2[j - 1]) { 
lcsAlgo[index - 1] = S1[i - 1]; i--; 
j--; 
index--; 
} 
 
else if (LCS_table[i - 1][j] > LCS_table[i][j - 1]) i--; 
else j--; 
} 
cout << "S1 : " << S1 << "\nS2 : " << S2 << "\nLCS: " << lcsAlgo << "\n"; 
} 
 
int main() { 
char S1[] = "ACADB"; char S2[] = "CBDA"; int m = sizeof(S1); int n = sizeof(S2); 
 
lcsAlgo(S1, S2, m, n); 
} 
 
 
 
 
 
 
Time complexity: O(n2) 
Space complexity: O(n2) 
 
