#include <iostream>
#include "console.h"
#include "grid.h"
using namespace std;

bool isSumRowsEqual(Grid<int> & Square){
    Vector<int> sum(Square.numRows());
    for(int i = 0; i < Square.numRows(); i++){
        for(int j = 0; j < Square.numCols(); j++){
            sum[i] += Square[i][j];
        }
    }
    for(int k = 1; k < Square.numRows(); k++){
        if(sum[k] != sum[k-1]) return false;
    }
    return true;
}

bool isSumColsEqual(Grid<int> & Square){
    Vector<int> sum(Square.numCols());
    for(int i = 0; i < Square.numCols(); i++){
        for(int j = 0; j < Square.numRows(); j++){
            sum[i] += Square[j][i];
        }
    }
    for(int k = 1; k < Square.numCols(); k++){
        if(sum[k] != sum[k-1]) return false;
    }
    return true;
}

bool isSumDiaEqual(Grid<int> & Square){
    int sum1 = 0;
    int sum2 = 0;
    for(int i = 0; i < Square.numRows(); i++){
        sum1 += Square[i][i];
        sum2 += Square[i][Square.numCols()-1-i];
    }
    if(sum1 == sum2) return true;
    return false;
}

bool isMagicSquare(Grid<int> & Square){
    if( Square.numRows() != Square.numCols()) return false;
    if(isSumRowsEqual(Square) && isSumColsEqual(Square) && isSumDiaEqual(Square)) return true;
    return false;
}

int main(){
    int n;
    cout << "Enter n: " << endl;
    cin >> n;
    Grid<int> Square(n, n);
    cout << "Enter a 2D arrays: ";
    for(int i = 0; i < n; i++){
        for(int j = 0; j < n; j++){
            cin >> Square[i][j];
        }
    }
    if(isMagicSquare(Square))
        cout<<"Yes"<<endl;
    else
        cout<<"No"<<endl;
    return 0;
}
