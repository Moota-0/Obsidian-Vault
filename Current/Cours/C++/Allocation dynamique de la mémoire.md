Allocation dynamique de mémoire avec les opérateurs :  
- new : est suivi d’un type et réserve de la mémoire pour ce type et renvoie un pointeur (ou une exception)
```
new type ≡ malloc (sizeof(type))
```
- delete : est suivi d’une variable contenant une adresse et il libère cette mémoire.

Exemple
```cpp
double *ptr = nullptr;  
ptr = new double; // Réservation de mémoire  
delete ptr;       // Libération de mémoire
```

Allocation dynamique de mémoire: **les tableaux**
Exemple:
```cpp
int* pTableau = nullptr;  
pTableau = new int[10];  // Alloue de la place pour 10 entiers (40 bytes)
delete []pTableau; //Ne pas oublier les [], sinon seul le premier élément du tableau est libéré => fuite mémoire
```
- En cas d'échec d'allocation de new, une exception ``std::bad_alloc`` est levée.
- L’opérateur ``new(std::nothrow)`` se contente de renvoyer un pointeur nul ``(nullptr)``, en cas d’échec.
```cpp
ptr = new (nothrow) int[1024];  
if(ptr == nullptr)...
```