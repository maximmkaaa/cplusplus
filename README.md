## Hello!
This is the pack of light and "useful" codes for c++

## Brainfuck interpreter
<details> 
<summary>How to use:</summary>
```c++
#include "bf.h"

bf::eval("+++++++[>+++++++<-]>."); //Will print 1
```
</details>

## Dynamic function
<details> 
<summary>How to use:</summary>
```c++
#include "func_ptr.h"

//int mul(int a, int b) { return a * b; }
auto mul = func_ptr<int(int, int)>({
	//Put your asm code here
	0x90, 0x01, 0x00, 0xE0,
	0x1E, 0xFF, 0x2F, 0xE1
});
	
int res = mul(23, 3); //Will return 69
```	
</details>

## Custom operator
<details> 
<summary>How to use:</summary>
```c++
#include "make_operator.h"

struct _in {
	template <typename T>
	inline bool operator ()(T value, std::vector<T> const& vector) const {
		return std::find(vector.begin(), vector.end(), value) != vector.end();
	}
};

auto in = make_operator(_in());

std::vector<int> v = { 10 };

bool res = 10 <in> v; //Will return true
res = 11 <in> v; //Will return false
```
</details>
