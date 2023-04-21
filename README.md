# My_project
Hackathon 2.0



#### 1.Write a program to print the following pattern :
<b>
* <br>
** <br>
*** <br>
**** <br>
*** <br>
** <br>
* <br>
</b>




```python
rows = 4
for i in range(0, rows):
    for j in range(0, i + 1):
        print("*", end=' ')
    print("\r")

for i in range(rows, 0, -1):
    for j in range(0, i - 1):
        print("*", end=' ')
    print("\r")
```

    * 
    * * 
    * * * 
    * * * * 
    * * * 
    * * 
    * 
    


#### 2.Write a program to accept 5 even and 5 odd numbers from the user and display :<br>
●sum of even numbers, <br>
●product of odd numbers <br>
●absolute difference of the sum and product. <br>

Check if thefinal result (absolute difference) isa prime number or not.


```python
even_numbers = [] 
odd_numbers = [] 

#To accept 5 even and 5 odd numbers. 
for i in range(5): 
    while True: 
        num = int(input(f"Enter {i+1} even number : ")) 
        if num % 2 == 0: 
            even_numbers.append(num) 
            break 
        else: 
            print(num,"is not even number. Please enter an even number.") 

for i in range(5): 
    while True: 
        num = int(input(f"Enter {i+1} odd number 1: ")) 
        if num % 2 != 0: 
            odd_numbers.append(num) 
            break 
        else: 
            print(num,"is not odd number. Please enter an odd number.") 
                         
print("Even numbers entered:", even_numbers) 
print("Odd numbers entered:", odd_numbers) 

sum_of_even = sum(even_numbers)  
product_of_odd = 1 
for num in odd_numbers: 
    product_of_odd *= num 
     
abs_diff = abs(sum_of_even - product_of_odd) 

print(f"Sum of even numbers: {sum_of_even}") 
print(f"Product of odd numbers: {product_of_odd}") 
print(f"Absolute difference between sum and product: {abs_diff}") 
 
if abs_diff > 1: 
    for i in range (2,abs_diff): 
        if (abs_diff % i) ==0: 
            print(abs_diff,"is not prime Number.") 
            break 
        else: 
            print(abs_diff,"is prime number.")

```

    Enter 1 even number : 2
    Enter 2 even number : 4
    Enter 3 even number : 6
    Enter 4 even number : 8
    Enter 5 even number : 10
    Enter 1 odd number 1: 1
    Enter 2 odd number 1: 3
    Enter 3 odd number 1: 5
    Enter 4 odd number 1: 7
    Enter 5 odd number 1: 9
    Even numbers entered: [2, 4, 6, 8, 10]
    Odd numbers entered: [1, 3, 5, 7, 9]
    Sum of even numbers: 30
    Product of odd numbers: 945
    Absolute difference between sum and product: 915
    915 is prime number.
    915 is not prime Number.
    

#### 3.Create a class named Item that holds data about an item in a retail store. The class should have the following three properties: <br>
●name: the name property is a String object that holds the name of the item. <br>
●price: the price property is a double variable that holds the item's retail price <br>
●quantity: the quantity property is an int variable that holds the number of units currently in inventory <br>
Write four methods to retrieve the values from the three fields and their current inventory value <br>
●	getName( ) returns the item name String <br>
●	getPrice( ) returns the price of the item double <br>
●	getQuantity( ) returns the number of quantities int <br>
●	getValue( ) that returns the current inventory value (quantity * price) double <br>


```python
class Item: 
    def __init__(self, name: str, price: float, quantity: int): 
        self.name = name 
        self.price = price 
        self.quantity = quantity 
    
    def getName(self) -> str: 
        return self.name 
    
    def getPrice(self) -> float: 
        return self.price 
    
    def getQuantity(self) -> int: 
        return self.quantity 
    
    def getValue(self) -> float: 
        return self.price * self.quantity

```

#### 4.Ask the user number of rows to be generated of a series. Suppose user enters no. of rows = 5 then the series shall be :  <br>
9 <br>
99 <br>
999 <br>
9999 <br>
99999 <br>


```python
rows = int(input("Enter the Total Number of Rows  : ")) 
for i in range(1, rows + 1):
    for j in range(1, i + 1):
        print('9', end = '  ')
    print()

```

    Enter the Total Number of Rows  : 5
    9  
    9  9  
    9  9  9  
    9  9  9  9  
    9  9  9  9  9  
    

#### 5.Write a program to accept a number from the user and check whether the number entered is prime or not.


```python
num = int(input("Enter the number:"))
for i in range(2, num):
    if num % i == 0:
        print("Not a prime number")
        break
else:
    print("Prime Number")

```

    Enter the number:22
    Not a prime number
    

### Continued from Major Question 3. 
#### 6.Write a separate class called Inventory with methods 
●	generate()  -  creates three Item objects <br>
●	getDetails() -  produces a neatly formatted table of the store's inventory displaying the three items, their current inventory value, and the total inventory value for the store. <br>



```python
class Inventory:
    def __init__(self):
        self.items = []
        
    def generate(self):
        self.items.append(Item("Stapler", 2.25, 15))
        self.items.append(Item("Paper", 32.99, 255))
        self.items.append(Item("Binder", 4.75, 9))
        
    def getDetails(self):
        print("{:<20}{:<26}{:<24}{:<20}".format("Name", "Price", "Quantity", "Value"))
        print("-" * 86)
        print("-" * 86)
        total_inventory = 0
        for item in self.items:
            value = item.getValue()
            total_inventory += value
            print("{:<20}{:<25.2f}{:<23d}{:<20.2f}".format(item.getName(), item.getPrice(), item.getQuantity(), value))
        print("{:<50}{:<47}".format("Total inventory is    " + str(total_inventory), ""))

inventory = Inventory()
inventory.generate()
inventory.getDetails()

```

    Name                Price                     Quantity                Value               
    --------------------------------------------------------------------------------------
    --------------------------------------------------------------------------------------
    Stapler             2.25                     15                     33.75               
    Paper               32.99                    255                    8412.45             
    Binder              4.75                     9                      42.75               
    Total inventory is    8488.95                                                                    
    


```python

```


```python

```
