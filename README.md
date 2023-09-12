# arrayy

// Online C++ compiler to run C++ program online
#include <bits/stdc++.h>
using namespace std;
int upper(int nums[], int n, int j){
    int l=0,h=n-1;
    
    while(l<=h){
        int mid=(l+h)/2;
        if(nums[mid]<=j){
            
            l=mid+1;
        }
        else{
             h=mid-1;
        }
    }
    return h;
}


int lower(int nums[], int n, int i){
    int l=0,h=n-1;
  
    while(l<=h){
        int mid=(l+h)/2;
        if(nums[mid]>=i){
            h=mid-1;
        }
        else{
           l=mid+1;
        }
    }
    return l;
}

int func(int nums[], int n, int i, int j){
    int count=0;
    count=upper(nums,n,j)-lower(nums, n, i)+1;
    return count;
}

int main() {
    // Write C++ code here
    int nums[]={1,3,3,9,10,9};
    int n=sizeof(nums)/sizeof(nums[0]);
    sort(nums, nums + n);
    
    int i=1, j=4;
    cout<<func(nums, n,i,j)<<endl;
     i=9, j=12;
    cout<<func(nums, n,i,j)<<endl;
   

    return 0;
}
