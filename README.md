# Max-circular-sub-array-sum
Find the maximum sum of sub array out of a given  circular array 
//Maximum circular sub array sum
#include<iostream>
#include<bits/stdc++.h>
using namespace std;

int main(){
	int n;
	cout<<"Enter a number: ";
	cin>>n;
	int arr[n];
	for(int i=0;i<n;i++){
		cin>>arr[i];
	}
	int res=arr[0];
	for(int i=0;i<n;i++){
		int curr_max=arr[i];
		int curr_sum=arr[i];
		for(int j=1;j<n;j++){
			int index=(i+j)%n;
			curr_sum+=arr[index];
			curr_max=max(curr_max,curr_sum);
		}
		res=max(res,curr_max);
	}
	cout<<"Maximum circular sub array sum: "<<res;
}
