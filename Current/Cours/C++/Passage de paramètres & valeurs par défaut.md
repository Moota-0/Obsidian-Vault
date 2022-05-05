### Par référence
- Une référence à une variable de type **T** est notée **``T&``**
- L'adresse peut être modifiée **uniquement** à sa **déclaration**
```cpp
int i;
int &r = i; // r est une référence sur i
r = j; // copie la valeur de j dans i
```
- On ne dispose pas de l’arithmétique des pointeurs!
- Alternative aux pointeurs pour manipuler des adresses
- Surtout utilisées pour les passages de paramètres

**Remarque**
La signification des opérateurs ``*`` et ``&`` dépend du contexte !

### Modes de passage de paramètres
Par **valeur**
```cpp
void fn(int par_formel){...}  
fn(par_effectif);  
```
Par **pointeur-adresse** du paramètre effectif  
```cpp
void fn(int * par_formel){...}  
fn(&par_effectif);
```
Par **référence-adresse**, mais c’est le compilateur qui gère les & et * -  
```cpp
void fn(int & par_formel){...}  
fn(par_effectif);  
```
Par **référence sur une constante**
```cpp
void fn(const int & par_formel){...}  
fn(par_effectif);
```

###### Passage de paramètres modifiables aux fonctions

**Déclaration/Définition de la fonction :**
```cpp
void swap( int & a, int & b ) // paramètres de type référence  
{  
	int t=a; a=b; b=t;  
}
```
**Appel de la fonction :**
```cpp
int x=2, y=3;
swap(x, y);
```

###### Référence sur des données constantes
Exemple :
l’argument **pasTouche** est nécessaire mais ne doit pas pouvoir
être modifié dans une fonction de calcul.
- Première méthode
``double CalculerTout(monType pasTouche){...}``
Inconvénient: création d'une copie de la valeur de l’argument
- Méthode par référence
``double CalculerTout(const monType &maRef){ ... }``

##### Opérateur & (-> adresse de `<var>` / référencement)
Donne l'**adresse** de la variable
```cpp
int &r = i; // adresse de r = i
p = &i;     // p = adresse de i
z = a&b;    // z = operation ET bit à bit entre a et b
```

##### Opérateur * (->  valeur de/pointée par adresse `<var>` / déréférencement / pointeur vers `<var>`)
Donne la **valeur** à l'adresse de la variable
ici `<var>` est une adresse

##### Fonction renvoyant une référence
```cpp
int& returnReferenceOnCount()
{
	static int count = 0;  
	return count;  
}
int main()
{  
	cout << "Count: " << returnReferenceOnCount() << endl;  
	cout << "Count: " << ++returnReferenceOnCount(); << endl;  
}
```
```
Count: 0
Count: 1
```
##### Manipulation au travers d’une fonction -sécurité
```cpp
string tabNoms[N]={ "Bob", "John"};  
int tabAges[N]={ 20, 30};
int& age(string nom){  
	for (int i=0; i<N; i++){  
		if (nom==tabNoms[i])  
			return tabAges[i];  
	}
}  
int main(){  
	age("Bob") = 50;  
	age("John")++;  
}
```

```
Bob	John
50	31
```

### Valeurs par défaut des paramètres
```cpp
void trier( void *table,            // (1)  
			int nbr,                // (2)  
			int taille = 100,       // (3)  
			bool croissant = true); // (4)
```
- Ces paramètres peuvent être omis à l’appel
```cpp
trier(tab,nb,4); // => croissant=true  
trier(tab,nb);   // => croissant=true  
                 // taille = 100
```
- Uniquement s’il est le dernier de la liste ou suivi de paramètres ayant des valeurs par défaut
- Les valeurs sont précisées à la déclaration et non à la définition
