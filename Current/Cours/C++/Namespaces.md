# Espaces de noms
- Dans les grands projets, le risque d’utiliser les mêmes noms pour des variables ou fonctions augmente
- On confine les noms d’un module dans un espace de noms (namespace)

##### Mots-clés et symboles associés :
```cpp
namespace XX{... }     // définit un nouvel espace de noms
namespace XX::YY{... } // imbrication (C++ 17)
using namespace XX     // ouvre l'espace de noms XX
::                     // opérateur de résolution de portée
```

##### Espaces de noms - Exemple
- **déclaration** d’espaces de noms :
```cpp
namespace language::english // Définition de l’espace « english »
{
	char *color[]={"White", "Red", "Black"};
	void colorName(int index)
	{
		cout<<"The color is" << color[index];
	}
}
namespace language::french // Définition de l’espace « french »
{
		char *color[]={"Blanc", "Rouge", "Noir"};
		void colorName(int index)
	{
		cout<<"La couleur est" << color[index];
	}
}
```
- **utilisation** d’espaces de noms :
```cpp
using namespace language::english; // -> Promotion de english au niveau global
int main()
{
	colorName(1);                  // affiche : Red
	language::french::colorName(1);// affiche : Rouge 
	// language:: -> Utilisation de l’espace « french »
	return 0;
}
```