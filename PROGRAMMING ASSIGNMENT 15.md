```python
#Q1. Please write a program using generator to print the number which can be divisible by 5 and 7 between 0 and n in comma 
#    separated form while n is input by console?
#    Example:
#    If the following n is given as input to the program : 100
#    Then,the output of the program should be : 0,35,70
```


```python
class div_generator:
    def __init__(self,in_input):
        self.in_input = in_input
    def get_num(self):
        for i in range(0,self.in_input+1):
            if i%5==0 and i%7==0:
                yield i
output = div_generator(100)
for i in output.get_num():
    print(i,end=' ')
    
```

    0 35 70 


```python
#Q2. Please write a program using generator to print the even  numbers between 0 and n in comma separated froom while n is 
#    input by console?
#    Example: 
#    If the following n is given as input to the program : 10
#    Then,the output of the program should be : 0,2,4,6,8,10
```


```python
def genEvenNum(in_num):
    for i in range(in_num):
        if i % 2 == 0:
            yield i
for i in genEvenNum(10):
    print(i,end=' ')
```

    0 2 4 6 8 


```python
#Q3. The fibonacci sequence is computed based on the following formula below, please write a program using list comprehension
#    to print the Fibonacci Sequence in comma separated form with a given n input by console?
#    f(n)=0 if n=0
#    f(n)=1 if n=1
#    f(n)=f(n-1) + f(n-2) if n>1
```


```python
def genFibonaci(in_num):
    if in_num == 0:
        return 0
    elif in_num == 1:
        return 1
    else:
        return genFibonaci(in_num-1) + genFibonaci(in_num-2)
print([genFibonaci(x) for x in range(20)])
```

    [0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610, 987, 1597, 2584, 4181]
    


```python
#Q4. Assuming  that we have some email address in the "usename@copyname" format,please write program to print the user name of 
#    a given email address .Both username and copyname are composed of letters only?
#    Example: If the following email is given as input to the program: john@google.com
#    Then,the output of the program should be : john

```


```python
def getUsername():
    in_input = input("Enter the emailid in format 'username@copyname' : ")
    out_str  = in_input.split("@")
    print(out_str[0])
getUsername()
    
```

    Enter the emailid in format 'username@copyname' : sonali@google.com
    sonali
    


```python
#Q5. Define a class Shape and its subclass square. The square class has an inint function which takes a length as argument .Both
#    classes have a area function which can print the area of the shape where Shape's area is 0 by default
```


```python
class shape:
    def area(self):
        return 0
class square(shape):
    def __init__(self,length):
        self.length = length
    def area(self):
        return self.length*self.length
obj=square(100)
print(obj.area())
```

    10000
    
