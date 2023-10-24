# code3
#include<iostream>
using namespace std;
int n, r, ans;  //r个数进行全排列  ans为排列个数 
int book[510]; //标记是否被访问
int a[510]; //记录每次的排列数据

void DFS(int cur){ 
	if(cur == r)
		{ 
		for(int i = 0; i < cur; i++)
		{ 
			cout << a[i] << ' ';
		}
		cout << endl;
		ans++;  
		return ;
	}
	
	for(int i = 1; i <= n; i++)
	{  
		if(!book[i])
		{ 
			book[i] = 1; 
			a[cur] = i; 
			DFS(cur + 1);
			book[i] = 0; 
		}
	} 
} 

int main(){
	cin >> n >> r;
	DFS(0);
	cout << ans << endl;
	return 0; 
}
