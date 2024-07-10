# mergetwosortedarray
#include <iostream>
#include<vector>
using namespace std;
vector <int> merge(vector <int> v1 ,vector <int> v2)
{
    int n=v1.size();
    int m =v2.size();
    vector <int> res(n+m);
    int i=0;
    int j=0;
    int k=0;
    while(i<n && j<m)
    {
        if(v1[i]<v2[j])
        {
            res[k]=v1[i];
            i++;
        }
        else
        {
            res[k]=v2[j];
            j++;
        }
        k++;
    }
        while(j<m)
        {
            res[k]=v2[j];
            j++;
            k++;
        }

        while(i<n)
        {
            res[k]=v1[i];
            i++;
            k++;
        }
    return res;
}

int main() {
    vector <int> v1;
    v1.push_back(2);
     v1.push_back(3);
      v1.push_back(5);
       v1.push_back(9);
        v1.push_back(11);
        for(int i=0;i<v1.size();i++)
        {
            cout<<v1[i]<<" ";
        }
        cout<<endl;
     vector <int> v2;
     v2.push_back(1);
     v2.push_back(4);
      v2.push_back(6);
       v2.push_back(7);
        v2.push_back(8);
        for(int i=0;i<v2.size();i++)
        {
            cout<<v2[i]<<" ";
        }
        cout<<endl;
        vector<int> res=merge(v1,v2);
        for(int i=0;i<res.size();i++)
        {
            cout<<res[i]<<" ";
        }
        cout<<endl;

    return 0;
}
