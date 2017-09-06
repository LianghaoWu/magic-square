# magic-square
A magic square is a square array of integers such that the sum of every sum of every row, the sum of every column, and the sum of each of the two diagonals are all equal


------------------------------------------------------------------------------------------------------------------------------------------
#include <iostream>
using namespace std;

int main() {
	int n,arr[100][100]={0};
	cout<<"Please input the size of the square: "<<endl; 
	cin>>n;
	cout<<"Please input the square: "<<endl;
	for (int i=0;i<n;i++) {
		for(int j=0;j<n;j++) {
			cin>>arr[i][j];
		}
	}
	int sum=0;
	for (int i=0;i<n;i++) {
		sum=sum+arr[0][i];
	}
	int yes=0;
	int temp1=0;
	for (int i=1;i<n;i++) {
		for (int j=0;j<n;j++) {
			temp1=temp1+arr[i][j];
		}
		if (temp1!=sum) {
			yes=1;
			break;
		}
		temp1=0;
	}
	int temp2=0;
	for (int j=0;j<n;j++) {
		for (int i=0;i<n;i++) {
			temp2=temp2+arr[i][j];
		}
		if (temp2!=sum) {
			yes=1;
			break;
		}
		temp2=0;
	}
	int temp3=0;
	int ok=0;
	for (int i=0;i<n;i++) {
		temp3=temp3+arr[i][i];
	}
	if (temp3!=sum) {
		ok=1;
	}
	int temp4=0;
	for (int i=0,j=n-1;i<n;i++,j--) {
		temp4=temp4+arr[i][j];
	}
	if (temp4!=sum) {
		ok=1;
	}
	if (ok==1||yes==1) {
		cout<<"This is not a magic square!"<<endl;
	}
	else cout<<"This is a magic square!"<<endl;
}
