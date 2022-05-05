- **Signature** d'une fonction:  
liste des types des paramètres effectifs d'une fonction.  
- **Surcharge** d'une fonction:  
écriture de plusieurs fonctions de **même nom**, mais de  
signature différente.
**Exemple :**
```cpp
int minimum(int a, int b)  
{  
	return a < b ? a : b;  
}  
int minimum(int a, int b, int c)  
{  
	return minimum(a, minimum(b, c));  
}
```