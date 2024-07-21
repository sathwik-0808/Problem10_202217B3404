#include <stdio.h>

#include <stdlib.h>



// Function to merge two subarrays of arr[]

void merge(int arr[], int beg, int mid, int end) {

    int n1 = mid - beg + 1;

    int n2 = end - mid;



    // Create temporary arrays

    int* left = (int*)malloc(n1 * sizeof(int));

    int* right = (int*)malloc(n2 * sizeof(int));



    // Copy data to temporary arrays

    for (int i = 0; i < n1; i++)

        left[i] = arr[beg + i];

    for (int j = 0; j < n2; j++)

        right[j] = arr[mid + 1 + j];



    // Merge the temporary arrays back into arr[]

    int i = 0; // Initial index of first subarray

    int j = 0; // Initial index of second subarray

    int k = beg; // Initial index of merged subarray



    while (i < n1 && j < n2) {

        if (left[i] <= right[j]) {

            arr[k] = left[i];

            i++;

        } else {

            arr[k] = right[j];

            j++;

        }

        k++;

    }



    // Copy the remaining elements of left[], if any

    while (i < n1) {

        arr[k] = left[i];

        i++;

        k++;

    }



    // Copy the remaining elements of right[], if any

    while (j < n2) {

        arr[k] = right[j];

        j++;

        k++;

    }



    // Free allocated memory

    free(left);

    free(right);

}



// Function to implement merge sort

void merge_sort(int arr[], int beg, int end) {

    if (beg < end) {

        int mid = beg + (end - beg) / 2;



        // Recursively sort the first and second halves

        merge_sort(arr, beg, mid);

        merge_sort(arr, mid + 1, end);



        // Merge the sorted halves

        merge(arr, beg, mid, end);

    }

}



// Function to print an array

void print_array(int arr[], int size) {

    for (int i = 0; i < size; i++)

        printf("%d ", arr[i]);

    printf("\n");

}



int main() {

    int arr[] = {38, 27, 43, 3, 9, 82, 10};

    int arr_size = sizeof(arr) / sizeof(arr[0]);



    printf("Given array is \n");

    print_array(arr, arr_size);



    merge_sort(arr, 0, arr_size - 1);



    printf("\nSorted array is \n");

    print_array(arr, arr_size);



    return 0;

}