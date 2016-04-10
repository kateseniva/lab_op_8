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

void result()
{
   if (fo) // если есть доступ к файлу,
    {
        for(int i=1; i<=(n+1); i++){
        gets(m); // инициализируем строку
        fprintf(fo, "%s\n", m);
        fprintf(file, "%d", i);
        fprintf(file, "%s\t", m);
        k=strlen(m);
        fprintf(file, "lenght: %d\n", k);

}
}
}

void open()
{
    fo = fopen("source.txt","wt");
    file = fopen("out.txt","wt");
}

void close()
{
    fclose(fo);
    fclose(file);
}

