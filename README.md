# password-creator
error
#include<bits/stdc++.h>
using namespace std;
int jisuan(int m)
{
	int total=0;
 	while(m/10!=0)
 	{
 		total+=m%10;
 		m/=10;
	}
	total += m;
	//cout<<total<<endl;
	return total;
}
int main()
{
	int n;
	cin>>n;
	while(n--)
	{
		int password[6];
		string s;
		cin>>s;
		int p[6];
		for(int i=0;i<6;i++)
		p[i] = 0;
		int length = s.length();
		int r = length/6+1;
		char s1[r][6] = {0};
		int num = 0;
		for(int i=0;i<r;i++)
		{
			for(int j=0;j<6;j++)
			{
				s1[i][j] = s[num];
				num++;
				if(num>=s.length())
				break;
			}
		}
		/*
		for(int i=0;i<r;i++)
		{
			for(int j=0;j<6;j++)
			{
				
				cout<<s1[i][j];
			}
			cout<<endl;
		}
		*/
		for(int i=0;i<6;i++)
		{
			for(int j=0;j<r;j++)
			{
				//cout<<s1[j][i]-0<<" ";
				if(s1[j][i]>='a'&&s1[j][i]<='z')
				p[i] += (int)s1[j][i];
				
			}
		}
		
		for(int k=0;k<6;k++)
		{
			//cout<<p[k]<<" ";
			while(p[k]/10!=0)
			p[k] = jisuan(p[k]);
			password[k] = p[k];
			
		}
		for(int k=0;k<6;k++)
		{
			cout<<password[k];
		}
		cout<<endl;

	}
}
