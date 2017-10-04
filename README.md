# matrix

#include <iostream>
#include <sstream>
using namespace std;
int main () {
int a[3][3],b[3][3],c[3][3];
char s;
bool failure=false;
for ( int i=0; i<3; i++) {
   for( string string; getline( cin, string ); ) {
        istringstream stream( string );
        for( int j = 0; j < 3; j++ ) {
            if( !( stream >> a[i][j] ) ) {
                failure = true;
                break;
            }
        }
        break;
      }
    }
cin>> s;
cin.ignore(1,'\n');
for ( int i=0; i<3; i++) {
   for( string string; getline( cin, string ); ) {
        istringstream stream( string );
        for( int j = 0; j < 3; ++j ) {
            if( !( stream >> b[i][j] ) ) {
                failure = true;
                break;
            }
        }
        break;
      }
    }
    if (!failure) {
if (s == '+') 
  for (int i=0; i<3; i++) {
    for (int j=0; j<3; j++){
      int k=b[i][j]+a[i][j];
      c[i][j]=k;
    }
  }
if (s == '-') 
  for (int i=0; i<3; i++) {
    for (int j=0; j<3; j++){
      int k=a[i][j]-b[i][j];
      c[i][j]=k;
    }
  }
 if (s == '*') 
  for (int i=0; i<3; i++) {
    for (int j=0; j<3; j++){
      int k=a[i][0]*b[0][j]+a[i][1]*b[1][j]+a[i][2]*b[2][j];
      c[i][j]=k;
    }
  } 
for (int i=0; i<3; i++) {
    for (int j=0; j<3; j++){
      cout << c[i][j]<<' ' ;
    }
    cout << '\n';
  }
    }
    else {
      cout << "An error has occured while reading numbers from line";
    }
    return 0;
}
