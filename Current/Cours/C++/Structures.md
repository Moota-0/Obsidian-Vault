En C++ une structure peut aussi contenir des fonctions  
(méthodes).

Exemple:
```cpp
struct Vecteur  
{  
	float x,y;  
	float longueur()  
	{  
		return (sqrt(x*x + y*y));  
	}
};
Vecteur v; // Pas besoin de mentionner struct Vecteur...
v.x=3.0; v.y=4.0;  
v.longueur();
```
