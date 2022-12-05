- Use intention-revealing names. Let the object speak for itself.
```python
m = 56 # minutes of inactivity ❌
minutes_of_inactivity = 56 ✅
```
- Avoid using names that mislead the reader.
```python
names_list = set()  ❌ # list has a pre-defined meaning in python
unique_names = set() ✅ # 'unique' means that we are using a data structure containing unique values
```
- Avoid incremental names as much as possible. Entities in your program should be clearly distinguishable from each other. 
```python
def one_dimensional_convolution(line1, line2): ❌
	assert len(line1) >= len(line2)
	
	result = []
	
	for i in range(len(line1) - len(line2)):
		tmp = 0
		
		for j in range(len(line2)):
			tmp += line1[i + j] * line2[j]
			
		result.append(tmp)
```
```python
def one_dimensional_convolution(values, kernel): ✅
	assert len(values) >= len(kernel)
	
	result = []
	
	for i in range(len(values) - len(kernel)):
		tmp = 0
		
		for j in range(len(kernel)):
			tmp += values[i + j] * kernel[j]
			
		result.append(tmp)
```
- Use pronouncable names
```python
bday_dt = "10 Jan 1556" ❌
birthday_date = "10 Jan 1556" ✅
```
- Use searchable names
```python
MAX_PER_W = 4 ❌
MAX_DAY_PER_WEEK = 4 ✅
```
- Avoid meanignless prefixes
```python
m_profit = 456 ❌
max_profit = 456 ✅
```
- Use names that prevents mental map triggering (unless in the conventionally agreed context)
```python
i, j, k = 0, 4, 5 ❌ # popularly used in loop counters but this is not a loop as expected in our mental model
```
- Classe names should be noun and not verbs
```python
class Processor: ❌
	pass  
class Eat: ❌
	pass 
class Clustomer ✅:
	pass
 
class Dog: ✅
	pass 
```
- Methods should be verbs 
```python
CPU.processor() ❌
Store.cashier() ❌
Dog.bark() ✅
Customer.pay() ✅
```
- Peak one word per concept with as little overlap as possible. Don't use `footballer`, `soccer_player` in the same codebase. Another example is using  `Manager` and `Controller`  for different classes.
- Encapsulate meaning to provide context. If you have different variables in your codebase that does different thing but related to a particular **concept**. It might worthwile encapsulating them into a class or an enity that represents the **concept**.
```python
street_number, phone_number, name = 456, "+56 565 656", "John" ❌
class UserInfo: ✅
	name = "John"
	phone_number = "+56 565 656"
	street_number = 456
```
