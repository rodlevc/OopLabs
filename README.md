#include <iostream>
#include <string>
#include <ctime>
using namespace std;

class Array
{
int size;
int *array;
int sum=0;
public:
   Array(int size);
   Array(const Array &obj);
   ~Array();
   void Count();
};

Array::Array(const Array &obj)
{
        cout << "\n" ;
        array = new int[obj.size];
        for (int i=0;i<obj.size;i++)
        {
        array[i]=obj.array[i];
        size=obj.size;
        cout << obj.array[i] << " " << endl;
        }
}

Array::Array(int a)
{
        size = a;
        array = new int[size];
        for(int i=0; i < size; ++i)
        {
        if (i%2)
        array[i] = rand() % 5 + 7;
        else
        array[i] = rand() % 5 - 3;

        cout << array[i] << " " << endl;
        }
}

Array::~Array()
{
   delete[]array;
}

void Array::Count()
{
    for(int i=0; i<size; ++i)
    if((i+1)%3==0)
    sum+=array[i];
    cout << "\nsum: " << sum << endl;
}

int main()
{
if(true)
  {
  Array a(11);
  a.Count();
  Array b=a;
  }
}
