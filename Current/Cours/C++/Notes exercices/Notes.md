```cpp
#include <iostream>
#include <iomanip>


```

Mini série

```cpp
getline(cin, varstring);
var = (<cond>) ? iftrue : iffalse; // opérateur ternaire / ternary operator

switch(_expression_) {  
  case x:  
    _// code block_  
    break;  
  case y:  
    _// code block_  
    break;  
  default:  // code par défaut
    _// code block_

	// Skip for steps
	for (int i = 0; i < 10; i++) {
	  if (i == 4) {
	    continue;
	  }
	  cout << i << "\n";
	}
}
```

### Série 1
Exercice 1
```cpp
#include <iostream> // fonctions de base
<< (std)::boolalpha << // affichage true/false
<< (std)::noboolalpha << // annule la ligne précédente
<< (std)::(hex/dec/oct) << // hexa, décimal octal
```

```cpp
#include <iostream>
#include <iomanip>

<< (std::)setprecision(13) << // Précision significative (nombre de chiffres à afficher)
<< scientific << // affichage en notation scientifique 1.12e+03
<< defaultfloat << // affichage par défaut
```

Exercice 2

Attention aux ambiguitées des paramètres en utilisant des fonctions surchargées

```cpp
// ask for Enter confimation to end a program
cout << "Please hit ENTER to continue... ";
cin.clear();
cin.get();
```

Exercice 3

Passage de paramètres

