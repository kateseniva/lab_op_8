#include <iostream>
#include <stdio.h>
#include <io.h>
#include <conio.h>
#include <string.h>
#include <fstream>
#include <cstdlib>
#include <sstream>


using namespace std;

fstream fo;
ofstream file;
stringstream ss;


int MAX = 255;

void open(int, ofstream &fout);
void show();

int main()
{
    char t[MAX];

    setlocale(LC_ALL, "ukr");

    ofstream fout;
    cout << "Щоб записати натиснiть 1, шоб дозаписати натиснiть 2\n";
    int choose = 0;
    cin >> choose;
    open(choose, fout);
    cout << "щоб завершити запис введiть -" << endl;
    int i = 0;
    while(strcmp(t, "-") != 0){
        cin.getline(t, MAX);

        if (strcmp(t, "-") != 0 && i != 0)
            fout << t << endl;

        i++;
    }
    fout.close();

    show();
    return 0;
}
void open(int ch, ofstream &fout){
    if(ch == 1){
        fout.open("source.txt");
    }else if (ch == 2){
        fout.open("source.txt", ios::app);
    }
}

void show(){

    int k = 1;
    char t[255];

    stringstream ss;

    ifstream fin("source.txt");
    ofstream fout("out.txt");

    while(fin.getline(t, MAX)) {
        ss << k << " " << t << " " << strlen(t) << endl;
        fout << ss.str();
        k++;
        ss.str(string());
    }
    fin.close();
    fout.close();
}
