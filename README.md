#include <bits/stdc++.h>
using namespace std;
int main() 
{
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    int NN;
    cin>>NN;
    for(int iI=0;iI<NN;iI++)
    {
           int arr[257];
           for(int i=0;i<257;i++){arr[i] =0;}
           string s;cin>>s;
           for(int i=0;i<s.size();i++){arr[s[i]]++;}
        // for(int i=0;i<s.size();i++){cout<<arr[s[i]]<<endl;}
		   
           vector<int> v;
           bool res=1;
           for(int i=0;i<257;i++)
           {
               if(arr[i]){v.push_back(arr[i]);}
           }
           sort(v.begin(),v.end());
           if(v.size()>2)
           {
               if(v[2]!=v[1]+v[0]){res=0;}
           }
           if(v.size()>=4)
           {
               if((v[3]!=v[2]+v[0])&&(v[3]!=v[1]+v[2])){res=0;}
           }
           for(int i=4;i<v.size();i++)
           {
               if(v[i-2]+v[i-1]!=v[i]){res=0;break;}
           }
           if(res){cout<<"Dynamic"<<endl;}
           else{cout<<"Not"<<endl;}
           //if(iI==2){cout<<v.size();}    
    }  
	return 0;
}
