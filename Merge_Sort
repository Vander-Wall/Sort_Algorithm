#include <stdio.h>
#include <iostream>
#include <string.h>

using namespace std;

// 归并 = 分治 + 合并


void merge(int arr[],int L,int M,int R){
	int LEFT_SIZE = M - L;
	int RIGHT_SIZE = R - M + 1;
	int left[LEFT_SIZE];
	int right[RIGHT_SIZE];

	//1.fill in the left arr

	for (int i = L; i < M; ++i){
		left[i-L]=arr[i];
	}
	for(int i = M; i <= R; ++i){
		right[i-M]=arr[i];
	}
//	for(int i = 0; i < LEFT_SIZE; i++)
//		printf("%d\n", left[i]);
//	for(int i = 0; i < RIGHT_SIZE; i++)
//		printf("%d\n", right[i]);
    int i = 0,j = 0, k = L;
    while(i < LEFT_SIZE && j < RIGHT_SIZE){
        if(left[i] < right[j]){
            arr[k++] = left[i++];
        }else{
            arr[k++] = right[j++];
        }
    }
    while(i < LEFT_SIZE){
        arr[k++] = left[i++];
    }
    while(j < RIGHT_SIZE){
        arr[k++] = right[j++];
    }
}


void merge_sort(int arr[],int L,int R){
    if(L == R)
        return;
    int M = (L + R) /2;
    merge_sort(arr, L, M);
    merge_sort(arr, M + 1, R);
    merge(arr,L,M+1,R);
}

int main()
{
	int arr[] = {-2312, 32318, 449, 0, -4, 31235, 6, 7};
	int L = 0;

	int R = sizeof(arr)/sizeof(int) - 1;
	printf("R=%d\n",R);
	//getchar();
	merge_sort(arr, L, R);
	for(int i = 0; i <= R;i++)
        printf("%d\n",arr[i]);
	return 0;
}
