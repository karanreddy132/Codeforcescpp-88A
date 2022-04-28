# Codeforcescpp-88A
#include <bits/stdc++.h>

using namespace std;

string check(map<string,int> m,string X,string Y,string Z){
  int first,second;
  
  if(m[Y] > m[X])
    first = m[Y]-m[X];
  else
    first = 12-(m[X]-m[Y]);
  
  if(m[Z] > m[Y])
    second = m[Z]-m[Y];
  else
    second = 12-(m[Y]-m[Z]);
  
  if(first==4 && second==3)
    return "major";
  else if(first==3 && second==4)
    return "minor";
  else 
    return "strange";
}

int main() {
  string s[7];
	map<string,int> m;
  m["C"] = 1;
  m["C#"] = 2;
  m["D"] = 3;
  m["D#"] = 4;
  m["E"] = 5;
  m["F"] = 6;
  m["F#"] = 7;
  m["G"] = 8;
  m["G#"] = 9;
  m["A"] = 10;
  m["B"] = 11;
  m["H"] = 12;
  string X,Y,Z;
  cin >> X >> Y >> Z;
  s[0] = check(m,X,Y,Z);
  s[1] = check(m,X,Z,Y);
  s[2] = check(m,Z,Y,X);
  s[3] = check(m,Z,X,Y);
  s[4] = check(m,Y,Z,X);
  s[5] = check(m,Y,X,Z);
  for(int i=0;i<6;i++){
    if(s[i]=="minor" || s[i]=="major"){
      cout << s[i];
      return 0;
    }
  }
  cout << "strange";
	return 0;
}
