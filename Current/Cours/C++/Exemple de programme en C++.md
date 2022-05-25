### Classe
Définition de la classe Point
`main.cpp`
```cpp
#include <iostream>
class Point 
{
	public: 
		void init(int, int);
		void translate(int, int); 
		void print() 
		{ 
		std::cout <<"("<<x<<","<<y<< ")";
		}
		int x;
		int y;
};
```
