Nouveau type (classe) pour les chaînes: ``string``
- Plus simple et plus sûr d'utilisation que ``char*``:  
	- Gestion automatique/dynamique de la taille 
	- Opérateurs utilisables simplement: ``= + += << >> []``
	- Fonctions de gestion et manipulation: ``size()``, ``capacity()``, ``find(...)``, ``erase(...)``,  ``insert(...)``, ...
- Le type est visible dans l'espace de noms standard ``std::string`` et est déclaré dans l'en-tête ``<string>``
```cpp
#include <iostream>  
#include <string>  
using namespace std;  
int main()  
{  
	string x = "toto";  
	string y = x;  
	string z = x + "_" + y;  
	cout << x << " " << y << " " << z << endl;  
	cout << "cap:" << z.capacity() << endl;  
	cout << "size:" << z.size() << endl;  
	return 0;  
}
```

```
toto toto toto_toto
cap:16
size:9
```