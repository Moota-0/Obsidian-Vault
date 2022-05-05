- ``nullptr`` mieux que 0 ou ``NULL``
- Terminer les fichiers source par une ligne vide.
	- Compatibilité avec anciens outils qui peuvent ignorer une ligne se terminant par EOF.
- Inférence de type avec ``auto`` et ``decltype``
	- Pour itérateur et templates
- Range-based for loop
```cpp
int values[] = {10, 20, 26};

for (const int& value : values)
{  
	cout << value << endl;  
}


// or  
for (const auto& value : values)  
{  
	cout << value << endl;  
}
```

```
10
20
26
```

