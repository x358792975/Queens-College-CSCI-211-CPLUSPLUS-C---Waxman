# Queens-College-CSCI-211-CPLUSPLUS-C---Waxman
Homework solutions for CSCI 211 @QC

#include <iostream>
#include <cmath>
using namespace std;

int main(){
    int b[8]={0};
    int c=0;
    int solution=0;
    
Nc: c++;
    if (c==8) goto print;
    b[c]=-1;
    
Nr: b[c]++;
    if(b[c]==8) goto backtrack;
    for(int i=0; i<c;i++) 
        if(b[i]==b[c] || c-i == abs(b[c]-b[i])) goto Nr;
    goto Nc;
backtrack: c--;
    if (c==-1) return 0;
    goto Nr;

print:	
	solution++;
        cout <<"Solution #" <<solution<<": " <<endl; 
	for (int i=0; i<8;i++) {
            cout << b[i];
        }
        cout<<endl;
   
    goto backtrack;
    return 0;
}
