- Use intention-revealing names. Let the variable speak for itself.
```python
m = 56 # minutes of inactivity ❌
minutes_of_inactivity = 56 ✅

```
- Avoid using variable names that mislead the reader.
```python
names_list = set()  ❌ # list has a pre-defined meaning in python
unique_names = set() ✅ # 'unique' means that we are using a data structure contain unique values

```
- Avoid incremental names as much as possible. Variables should be clearly distinguishable from each other.
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
	This is much better
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