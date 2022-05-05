##### Nécessaire
-> `#include <iostream>`
ou
-> `std::<var>`

##### Entrées / Sorties avec les variables prédéfinies:
`cin` -> **source** de flux de données
	en général le clavier
`cout` -> **destination** de flux de données
	en général l'écran


##### Opérateurs
`>>` **extraction** d’un flux source
`<<` __insertion__ dans un flux destination

##### Exemple
```cpp
int n;  
cin >> n; // Lecture du flux d’entrée (clavier)  
cout << "val " << n; // Affichage à l’écran
```

---

```cpp
#include <iostream>
using namespace std;

main()
{
	cout << "val" << endl;
}
```
Ou
```cpp
#include <iostream>
main()
{
	std::cout << "val" << std::endl;
}
```

##### Manipulateurs de flux intégrés à `<iostream>`
Fin de ligne : ``endl`` 
Changement de base : ``dec, oct, hex`` 
Changement de casse : ``(no)uppercase`` 
Force l’affichage du signe + : ``(no)showpos``
Affichage booléen (persistant) : ``(no)boolalpha``

```cpp
int j = 10;
cout << hex << nouppercase << j << endl;
cout << hex << uppercase << j << endl;
cout << dec << showpos << j << endl;
```

##### Manipulateurs de flux intégrés grâce à `<iomanip>`
-> `#include <iomanip>`
`setprecision(int) ` Nombre de chiffres significatifs 
`fixed` Représentation à virgule fixe
`scientific` Représentation scientifique
`defaultfloat` Représentation par défaut
``setw(int)`` Nombre de caractères utilisés
`setfill(char)` Caractère de remplissage

##### Opérations de saisie et de contrôle de buffer
`>>` : sert à la saisie et au test
L'expression `(cin >> nombre)` est une « référence » sur le flux. Elle est nulle (=0) en cas d’échec

Exemple :
```cpp
if ( (cin >> nombre) == 0 )
	cout << "probleme de lecture";
// ou équivalent
if ( ! (cin >> nombre) )
	cout << "probleme de lecture";
```


##### Remise en état du buffer après une erreur avec la fonction `ignore()`
```cpp
istream& ignore (streamsize n=1, int delim = EOF);
```
Cette fonction vide le buffer d’entrée. L’extraction s’arrête après n
caractères ou quand le caractère `delim` est trouvé.

Exemple
```cpp
cin.ignore(numeric_limits<streamsize>::max(),'\n');
```
`numeric_limits<streamsize>::max()` -> retourne la taille maximale du buffer (`#include <limits>`)

##### Opérations de saisie et de contrôle de buffer
Méthodes qui permettent de contrôler l’état du flux d’entrée et
d’agir:
- ``cin.fail()``: Problème dans le flux d’entrée, saisie incorrecte
- ``cin.clear()``: Remet les bits de contrôle du flux à OK
- ``cin.eof()``: Fin du flux d’entrée

Exemple avec ``cin`` (flux d'entrée std)
```cpp
int N;
cout << "Entrez un chiffre entre 1 et 6 : " ;
while ( !( cin >> N ) || N < 1 || N > 6 )
{
	if ( cin.fail() )
	{
		cout << "Saisie incorrecte, recommencez : ";
		cin.clear();
		cin.ignore(256, '\n' );
	}
	else
		cout << "Le chiffre n'est pas entre 1 et 6: ";
}
```

```
Entrez un chiffre entre 1 et 6 : abcdef
Saisie incorrecte, recommencez : -3
Le chiffre n'est pas entre 1 et 6: 17
Le chiffre n'est pas entre 1 et 6: 5
```