#include <iostream>
#include <stdio.h>
#include <io.h>
#include <conio.h>
#include <string.h>

using namespace std;

char m[100];// вихідний рядок
int n, k;
FILE * fo, * file;

void result();
void open();
void close();

int main()
{
    cout << "enter n: "; cin >> n;
    open();
    result();
    close();
    return 0;
}
