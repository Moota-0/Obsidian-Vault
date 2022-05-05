- Fonction **macro** en C
```c
#define MAX(x,y) ((x)>(y)?(x):(y))
```
- Fonction ``inline`` en C++
```c++
inline int max(int x, int y)  
{  
	return x>y ? x : y;  
}
```

L’expression en C -> 
```c 
x=MAX(2,b+1);
``` 
et l’expression en C++ ->
```cpp
x=max(2,b+1);
```
sont remplacées par le compilateur par :
```c
x= ((2)>(b+1)?(2):(b+1));
```

- Variable `inline`
`inline variable`
```cpp
inline T& instance(){  
static T global;  
return global  
;}

inline T global; //>=C++17
```
