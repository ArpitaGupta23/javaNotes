# javaNotes
#include<iostream>
using namespace std;
void sort(int [],int);
void dis(int [],int);
void mergepattern(int [],int);
int main()
{
	int n,a[15],i,j;
	cout<<"\n enter the no of files";
	cin>>n;
	cout<<"\n enter the length of files";
	for(i=1;i<=n;i++)
		cin>>a[i];
	sort(a,n);
	dis(a,n);
	mergepattern(a,n);
}
void dis(int a[],int n)
{
	cout<<"\n";
	for(int i=1;i<=n;i++)
cout<<"\t"<<a[i];
}
void sort(int a[],int n)
{
	int i,j;
	for(i=1;i<=n;i++)
	{
		for(j=1;j<n;j++)
		{
			if(a[j]>a[j+1])
				swap(a[j],a[j+1]);
		}
	}	
}
void mergepattern(int a[],int n)
{
	if(n>1)
	{
		int i,j;
		a[1]=a[1]+a[2];
		for(i=2;i<=n;i++)
			a[i]=a[i+1];
		n--;
		sort(a,n);
		dis(a,n);
		mergepattern(a,n);	
}
}
