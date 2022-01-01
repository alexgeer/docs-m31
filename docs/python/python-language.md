# Python Language

Python is a beginner-friendly language that we use in these courses at CodeWizardsHQ:

|Elementary              | Middle School                          |High School     |
|------------------------|----------------------------------------|----------------|
|Python Game Development |Introduction to Programming with Python |Intro to Python
|                        |Mastering Databases                     |APIs and Databases
|                        |Application Programming Interfaces      |Professional Web App Development
|                        |                                        |Mastering MVC Frameworks
|                        |                                        |Object Relational Mapping

In this section of our documentation, you'll find references to most of the core Python language features and built-in functions that we use in our CodeWizardsHQ courses.

You'll also find many *Further reading* sections, which pull from these excellent Python resources:

- [Python.org Documentation](https://www.python.org/doc/)
- [RealPython.com](https://realpython.com/)
- [Think Python](https://greenteapress.com/wp/think-python-2e/)

<hr>


## Comments

Programmers use comments to make notes in their source code for themselves or other programmers that will read their code later. They can also be used to "deactivate" lines of code that you don't want to run while you're working on a program.

### Single Line Comments

Single line comments begin with the `#` character. You can put them above or to the right of the line of code they reference:

```python
# Validate the user is logged in and redirect them to the appropriate page.
if is_logged_in(user):
    redirect_to_homepage()
else:
    redirect_to_login()


MIN_HEIGHT = 60  # This is measured in inches, not feet!
```

### Deactivating Code

You can deactivate sections of code with comments:

```python
if age < 18:
    # Turning this off for now
    # prompt_user()
    redirect_to_kid_zone()
else:
    login_user()

```

### Multiline Comments

You can use multiline strings if you want to make a multiline comment:

```python
"""
This calculates the hypotenuse of a right triangle when given the sides
of the right triangle. It's the Pythagorean Theorem. The ** is how you
write exponents in Python, and fractional exponents are like roots,
so 0.5 is the square root.
"""
hypotenuse = ((side_a ** 2) + (side_b ** 2)) ** 0.5
```

### Further reading

- [The Python Tutorial](https://docs.python.org/3/tutorial/introduction.html#an-informal-introduction-to-python)
- [Real Python - Writing Comments in Python](https://realpython.com/python-comments-guide/)
- [Think Python - Comments](https://greenteapress.com/thinkpython2/html/thinkpython2003.html#sec22)

<hr>







## Conditional Statements

Conditional statements allow you to run a block of code when a boolean condition is true. 

### `if`

The `if` statement is the simplest form of conditional statement. If the expression to the right of the `if` keyword is `True`, the indented code block will execute:

```python
is_hungry = True

if is_hungry:
    print("You should eat!")

```

Example Output:

```text
You should eat!
```

Usually, a conditional expression uses [comparison operators](#comparison-operators) to generate a `bool` result:

```python
age = 19

if age >= 18:
    print("You are legally an adult, congrats!")

```

Example Output:

```text
You are legally an adult, congrats!
```

### `elif`

The `elif` conditional statement is used to group *logically related* conditional statements together. The first conditional expression that evaluates to `True` will run:

```python
favorite_food = "Tacos"

if favorite_food == "Sushi":
    print("We're going out for Japanese food to night!")
elif favorite_food == "Pasta":
    print("How about we eat some Italian food tonight?")
elif favorite_food == "Tacos":
    print("Time for some Mexican food!")
elif favorite_food == "Samosa":
    print("Let's eat Indian food tonight!")
```

Example Output:

```text
Time for some Mexican food!
```

### `else`

The `else` conditional statement runs when all other conditional statements in a group are `False`. You can think of it as the *default* option:

```python
favorite_food = "Hot Dogs with Cream Cheese"

if favorite_food == "Sushi":
    print("We're going out for Japanese food to night!")
elif favorite_food == "Pasta":
    print("How about we eat some Italian food tonight?")
elif favorite_food == "Tacos":
    print("Time for some Mexican food!")
elif favorite_food == "Samosa":
    print("Let's eat Indian food tonight!")
else:
    print("I don't know what that favorite_food is!")
```

```text
I don't know what that favorite_food is!
```


### `Comparison Operators`

Here are the comparison operators that you can use in conditional expressions to generate a `bool` value:


|Operator| Description               |
|--------|---------------------------|
| `>`    | Greater-than              |
| `>=`   | Greater-than or equal-to  |
| `<`    | Less-than                 |
| `<=`   | Less-than or equal-to     |
| `==`   | Equal-to                  |
| `!=`   | Not equal-to              |


### `Complex Conditional Statements`

Complex conditional statements involve combining more than one conditional expression with [logical operators](#logical-operators):

```python
age = 15
height_in_feet = 4.6

if age >= 13 and height_in_feet > 5:
    print("You may ride the roller coaster.")
else:
    print("You may NOT ride the roller coaster.")
```

Example Output:

```text
You may NOT ride the roller coaster.
```

You can string as many logical operators together as you want to build more complex conditional statements:

```python
is_hungry = False
is_thirsty = True

food_amount = 10
drink_amount = 0

if is_hungry and food_amount > 0 or is_thirsty and drink_amount > 0:
    enter_kitchen()
else:
    play_video_games()

```

#### Formatting complex conditional statements

With a large complex conditional statement, it's often easier to read and reason about if you enclose the conditional expression in parentheses and split the statements across multiple lines:

```python
is_hungry = False
is_thirsty = True

food_amount = 10
drink_amount = 0

if (
    is_hungry  and food_amount  > 0 or 
    is_thirsty and drink_amount > 0
):
    enter_kitchen()
else:
    play_video_games()
```


### `Logical Operators`

Logical operators allow you to combine multiple conditional expressions in a single conditional statement:

|Operator| Description                                         |
|--------|-----------------------------------------------------|
| `and`  | `True` when both conditional expressions are `True` |
| `or`   | `True` when either conditional expression is `True` |
| `not`  | Reverses the value of a conditional expression      |

#### Using the `and` operator

The `and` operator evaluates to `True` when both conditional expressions are `True`:

```python
age = 15
height_in_feet = 5.2

if age >= 13 and height_in_feet > 5:
    print("You may ride the roller coaster.")
else:
    print("You may NOT ride the roller coaster.")
```

Example Output:

```text
You may ride the roller coaster.
```

#### Using the `or` operator

The `or` operator evaluates to `True` when either conditional expression is `True`:

```python
is_hungry = True
is_thirsty = False

if is_hungry or is_thirsty:
    print("You should go to the kitchen.")
else:
    print("Do whatever, you're good!")
```

Example Output:

```text
You should go to the kitchen.
```

#### Using the `not` operator

The `not` operator reverses a conditional expression:

```python
is_tired = True

if not is_tired:
    print("Let's go outside and play.")
else:
    print("Let's take a nap.")
```

Example Output:

```text
Let's take a nap.
```

### Nested Conditional Statements

Conditional statements can be nested inside other conditional statements. You just have to follow the same indentation rules for each nested conditional block:

```python
role = "admin"

if role == "admin" or role == "developer":
    print("You can see the secret stuff in this app.")
    if role == "admin":
        print("You can also see the SUPER secret stuff in this app.")
```

Example Output:

```text
You can see the secret stuff in this app.
You can also see the SUPER secret stuff in this app.
```


### Further reading

- [Real Python - Conditional Statements in Python](https://realpython.com/python-conditional-statements/)
- [Real Python - Using the `not` Boolean Operator in Python](https://realpython.com/python-not-operator/)
- [Real Python - Using the `and` Boolean Operator in Python](https://realpython.com/python-and-operator/)
- [Real Python - How to use the Python `or` Operator ](https://realpython.com/python-or-operator/)
- [The Python Library Reference - Boolean Operations](https://docs.python.org/3/library/stdtypes.html#boolean-operations-and-or-not)
- [The Python Library Reference - Boolean Values](https://docs.python.org/3/library/stdtypes.html#boolean-values)
- [The Python Library Reference - Comparisons](https://docs.python.org/3/library/stdtypes.html#comparisons)
- [The Python Library Reference - Truth Value Testing](https://docs.python.org/3/library/stdtypes.html#truth-value-testing)
- [The Python Tutorial - `if` Statements](https://docs.python.org/3/tutorial/controlflow.html#if-statements)
- [Think Python - Conditionals and Recursion](https://greenteapress.com/thinkpython2/html/thinkpython2006.html)

<hr>









## Data Types

Every value has a data type in Python. The data type determines what kinds of operations you can perform on the value. For example, you [can't perform arithmetic](#arithmetic-only-works-between-numbers) between values that aren't numeric data types.


### `bool`

The `bool` data type represents a `True` or a `False` value:

```python
is_hungry = True
is_thirsty = False
```

#### Generating `bool` in a conditional statement

You normally won't use a `bool` directly, but instead will generate a `bool` in a conditional statement:

```python
age = 19

# This generates `True`
if age >= 18:
    print("You are an adult!")


# This generates `False`
if age < 18:
    print("You are a child.")
```

#### Truthy and falsy values

Booleans are not the only values that can be True/False. Every value in Python is either *truthy* or *falsy*, which means they can be used in conditional statements without a boolean comparison operation. Empty strings and the number 0 are *falsy*, and all other strings and numbers are *truthy*.

Here's an example of a *falsy* value:

```python
username = ""

if username:
    print(f"Hello, {username}!")
else:
    print("The username is blank")
```

Example Output:

```text
The username is blank
```

Here's an example of a *truthy* value:

```python
num_bananas = 2

if num_bananas:
    print("We have bananas!")
else:
    print("We have no bananas!")
```

Example Output:

```text
We have bananas!
```



### `float`

The `float` data type represents a decimal number:

```python
total_cost = 29.99
```

### `int`

The `int` data type represents a whole number:

```python
num_tacos_eaten = 12
```

#### Converting `str` to `int`

You can use the `int()` function to convert a `str` to an `int`:

```python
age = int("13")
```

This is often combined with the `input()` function when you prompt the user for a numeric data type:

```python
age = int(input("How old are you? "))
```

### `str`

The `str` data type represents a text value:

```python
name = "Daniel"
```

#### String concatenation

If you need to combine a variable and a `str`, you can use the `+` operator. This technique is called __string concatenation__:

```python
name = "Daniel"
greeting = "Hello, " + name

print(greeting) # Hello, Daniel
```

#### String interpolation

Another way to combine a variable and a `str` is using `f-strings`. This technique is called __string interpolation__, and it is the preferred way to combine variables and `str`:

```python
name = "Daniel"
age = 35

print(f"I'm {name} and I'm {age} years old.")
```

Example Output:

```text
I'm Daniel and I'm 35 years old.
```

#### Multiline strings

Multiline strings allow you to write large blocks of text in a single `print()` statement:

```python
menu = """
    Welcome to Dan's Taco Stand!

    Tacos       $2
    Burritos    $5
    Nachos      $3

    Place your order by clicking *Order Now*
"""

print(menu)
```

Example Output:

```text

    Welcome to Dan's Taco Stand!

    Tacos       $2
    Burritos    $5
    Nachos      $3

    Place your order by clicking *Order Now*
```

##### `Removing the intial newline of a multiline string`

You can remove the initial newline from a multiline string using the `\` character:

```python
options = """\
    (1) View All Contacts (2) View Contact 
    (3) Add Contact (4) Update Contact 
    (5) Remove Contact (6) Exit
"""

print(options)
```

Example Output:

```text
    (1) View All Contacts (2) View Contact 
    (3) Add Contact (4) Update Contact 
    (5) Remove Contact (6) Exit
```

#### Raw strings

Raw strings (`str` prefaced with an `r`) tell Python to not interpret special `str` characters. You use them in CWHQ courses to print ASCII art and ensure it formats correctly. 

Generally, `r` strings will also be multiline strings, but this isn't required:

```python
mr_nibbles = r"""
        |\---/|
        | o_o |
         \_^_/
"""

print(mr_nibbles)
```

Example Output:

```text

        |\---/|
        | o_o |
         \_^_/

```

#### Getting the number of characters in a `str`

You can use the `len()` function to get the number of characters in a `str`:

```python
name = "Daniel"

len(name)  # 6
```

#### Checking if a `str` ends with a set of characters

The `str.endswith()` method lets you check if a `str` ends with a given pattern:

```python
email_addresses = ["djs@cwhq.com", "alecg@auburn.edu", "samh@bridges.com"]

for email_address in email_addresses:
    if email_address.endswith(".edu"):
        print(f"{email_address} is a school address")
    elif email_address.endswith("cwhq.com"):
        print(f"{email_address} is a CWHQ employee address")
    else:
        print(f"I don't know what {email_address} is for")
        
```

Example Output:

```text
djs@cwhq.com is a CWHQ employee address
alecg@auburn.edu is a school address
I don't know what sam@bridges.com is for
```

#### Sanitizing user input

User's do strange things, but using `str.lower()` and `str.strip()` can help your program to validate `str` data types.

`str.lower()` makes a `str` lowercase:

```python
# Imagine a user entered "Pizza" with an uppercase P
favorite_food = "Pizza"

if favorite_food.lower() == "pizza":
    print("That's my favorite food!")

```

Example Output:

```text
That's my favorite food!
```

`str.strip()` removes leading or trailing whitespace from a `str`:

```python
# Imagine a user entered " pizza" with a leading space character
favorite_food = " pizza"

if favorite_food.strip() == "pizza":
    print("That's my favorite food!")

```

Example Output:

```text
That's my favorite food!
```

You can chain these methods together to sanitize a `str` completely:

```python
# What a mess! Extra spaces before/after and odd capitalization
favorite_food = " PIzZa  "

if favorite_food.strip().lower() == "pizza":
    print("That's my favorite food!")

```

Example Output:

```text
That's my favorite food!
```


### Further reading

- [The Python Library Reference - Text Sequence Type](https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str)
- [The Python Library Reference - Numeric Types](https://docs.python.org/3/library/stdtypes.html#numeric-types-int-float-complex)
- [The Python Tutorial - Strings](https://docs.python.org/3/tutorial/introduction.html#strings)
- [Think Python - Values and Types](https://greenteapress.com/thinkpython2/html/thinkpython2002.html#sec10)
- [Think Python - Strings](https://greenteapress.com/thinkpython2/html/thinkpython2009.html)
- [Real Python - Python 3's f-Strings](https://realpython.com/python-f-strings/)
- [Real Python - Strings and Character Data in Python](https://realpython.com/python-strings/)

<hr>












## Data Structures

Data structures allow you to efficiently store and access groups of items. Think of them like different storage containers you may use around the house.


### `list`

The `list` data structure is used to store data in ordered *slots*. It is known as *mutable sequence type*, which means it can be modified after creation.

Usually, the items in a `list` are homogeneous, which means they represent a group of similar items of the same data type:

```python
names = ["alecg", "danielj", "dimas"]
menu_prices = [4.50, 5.75, 3.00]
ids = [184, 294, 832, 98, 4]
```

You can write a list on multiple lines if you want. The trailing comma is recommended but not required:

```python
foods = [
    "tacos", 
    "pizza", 
    "nachos",
    "ice cream",
    "asparagus",
]
```

#### Accessing items in a `list`

You can access individual items in a `list` using the `[]` characters and the index number of the item. The index numbers start at 0:

```python
names = ["alecg", "danielj", "dimas"]

print(names[0])  # alecg
print(names[1])  # danielj
print(names[2])  # dimas
```



#### Adding an item to a `list`

To add an item to a `list` after it has been created, you can use the `list.append()` method. The `list.append()` method adds the item to the end of the list:

```python
names = ["alecg", "danielj", "dimas"]

names.append("samh")

print(names)  # ['alecg', 'danielj', 'dimas', 'samh']
```



#### Updating an item in a `list`

To update a `list` item, replace the value at the index:

```python
names = ["alecg", "danielj", "dimas"]

names[1] = "django"

print(names)  # ['alecg', 'django', 'dimas']
```


#### Removing an item from a `list`

To remove an item from a `list`, you can use the `list.remove()` method:

```python
names = ["alecg", "danielj", "dimas"]

names.remove("alecg")

print(names)  # ['danielj', 'dimas']
```

If you want to remove an item from a `list` by its index number, use the `list.pop()` method:

```python
names = ["alecg", "danielj", "dimas"]

names.pop(0)

print(names)  # ['danielj', 'dimas']
```

#### Looping through a `list`

To loop through the items in a `list`, use a [`for`](#for) loop. Note the convention of using the plural `names` for the `list` and the singular `name` for the loop-iteration variable:

```python
names = ["alecg", "danielj", "dimas"]

print("This documentation is brought to you by:")
for name in names:
    print(name)
```

Example Output:

```text
This documentation is brought to you by:
alecg
danielj
dimas
```


#### Getting the number of items in a `list`

To get the number of items in a `list`, use the [`len()`](#len) function:

```python
names = ["alecg", "danielj", "dimas"]

num_names = len(names)

print(num_names)  # 3
```

#### Checking if an item is contained in a `list`

To check if an item is contained in a `list`, use the `in` operator:

```python
names = ["alecg", "danielj", "dimas"]

"alecg" in names  # True
"samh" in names   # False
```

The `in` operator is generally used as part of a conditional statement:

```python
names = ["alecg", "danielj", "dimas"]

if "alecg" in names:
    print("alecg is in the 'names' list")
else:
    print("alecg is NOT in the 'names' list")

if "samh" in names:
    print("samh is in the 'names' list")
else:
    print("samh is NOT in the 'names' list")
```

Example Output:

```text
alecg is in the 'names' list
samh is NOT in the 'names' list
```





#### Further reading

- [The Python Library Reference - Common Sequence Operations](https://docs.python.org/3/library/stdtypes.html#common-sequence-operations)
- [The Python Library Reference - Mutable Sequence Types](https://docs.python.org/3/library/stdtypes.html#mutable-sequence-types)
- [The Python Library Reference - `len()`](https://docs.python.org/3/library/functions.html#len)
- [The Python Tutorial - Lists](https://docs.python.org/3/tutorial/introduction.html#lists)
- [Think Python - Lists](https://greenteapress.com/thinkpython2/html/thinkpython2011.html)









### `dict`

The `dict` data structure is used to store data in key/value pairs:

```python
staff = {
    "danielj": "Curriculum Developer",
    "alecg": "Curriculum Instructor",
    "dimas": "Designer",
}
```

You can use the `dict()` function to build a `dict` as well, note that the keys are keyword arguments:

```python
staff = dict(
    danielj="Curriculum Developer",
    alecg="Curriculum Instructor",
    dimas="Designer",
)
```

#### Accessing items in a `dict`

You have to know the key to access an individual item in a `dict`:

```python
staff = {
    "danielj": "Curriculum Developer",
    "alecg": "Curriculum Instructor",
    "dimas": "Designer",
}

daniel_job = staff["danielj"]
print(f"Daniel is a {daniel_job}.")  # Daniel is a Curriculum Developer.

alec_job = staff["alecg"]
print(f"Alec is a {alec_job}.")  # Alec is a Curriculum Instructor.

dima_job = staff["dimas"]
print(f"Dima is a {dima_job}.")  # Dima is a Designer.
```

If you need to pull a value from a `dict` inside an `f-string`, you must use different quote characters for the key (if it's a `str`). 

```python
students = {
    "Vicki": "3rd grade",
    "Sam": "4th grade",
    "Tammy": "4th grade",
}

print(f"Vicki is in {students['Vicki']}") 
# Vicki is in 3rd grade

print(f"Sam is in {students['Sam']}")     
# Sam is in 4th grade

print(f"Tammy is in {students['Tammy']}") 
# Tammy is in 4th grade
```


#### Adding an item to a `dict`

You can add an item to a `dict` by providing the key/value pair (it's the same syntax as updating an item):


```python
staff = {
    "danielj": "Curriculum Developer",
    "alecg": "Curriculum Instructor",
    "dimas": "Designer",
}

staff["django"] = "Director Of Pug Snorts"

print(staff)  # {'danielj': 'Curriculum Developer', 'alecg': 'Curriculum Instructor', 'dimas': 'Designer', 'django': 'Director Of Pug Snorts'}
```


#### Updating an item in a `dict`

To update an item in a `dict`, you must know the key:

```python
staff = {
    "danielj": "Curriculum Developer",
    "alecg": "Curriculum Instructor",
    "dimas": "Designer",
}

staff["danielj"] = "Burrito Taste-Tester"

print(staff)  # {'danielj': 'Burrito Taste-Tester', 'alecg': 'Curriculum Instructor', 'dimas': 'Designer'}
```



#### Removing an item from a `dict`

To remove an item from a `dict`, use the `dict.pop()` method:

```python
staff = {
    "danielj": "Curriculum Developer",
    "alecg": "Curriculum Instructor",
    "dimas": "Designer",
}

staff.pop("danielj")

print(staff)  # {'alecg': 'Curriculum Instructor', 'dimas': 'Designer'}
```


#### Looping through a `dict`

To loop through a `dict`, you generally use the `dict.items()` method like this:

```python
staff = {
    "danielj": "Curriculum Developer",
    "alecg": "Curriculum Instructor",
    "dimas": "Designer",
}

for name, job in staff.items():
    print(f"{name} is a {job}.")

```

Example Output:

```text
danielj is a Curriculum Developer.
alecg is a Curriculum Instructor.
dimas is a Designer.
```

If you just want to loop over the keys of a `dict`, you can use a `for` loop just as you would with a `list`:

```python
staff = {
    "danielj": "Curriculum Developer",
    "alecg": "Curriculum Instructor",
    "dimas": "Designer",
}

print("CWHQ staff:")
for name in staff:
    print(name)

```

Example Output:

```text
danielj
alecg
dimas
```





#### Getting the keys from a `dict`

If you need to get all of the keys from a `dict`, use the `dict.keys()` method. Note, you'll usually want to cast the result to a `list`, which is why the `list()` function is used here:


```python
staff = {
    "danielj": "Curriculum Developer",
    "alecg": "Curriculum Instructor",
    "dimas": "Designer",
}

names = list(staff.keys())

print(f"Here are all the names in the staff dict: {names}")
```

Example Output:

```text
Here are all the names in the staff dict: ['danielj', 'alecg', 'dimas']
```

#### Getting the values from a `dict`

If you need to get all of the values from a `dict`, use the `dict.values()` method. Note, you'll usually want to cast the result to a `list`, which is why the `list()` function is used here:


```python
staff = {
    "danielj": "Curriculum Developer",
    "alecg": "Curriculum Instructor",
    "dimas": "Designer",
}

jobs = list(staff.values())

print(f"Here are all the jobs in the staff dict: {jobs}")
```

Example Output:

```text
Here are all the jobs in the staff dict: ['Curriculum Developer', 'Curriculum Instructor', 'Designer']
```

#### Getting the number of items in a `dict`

You can use the `len()` function to get the number of items in a `dict`:

```python
staff = {
    "danielj": "Curriculum Developer",
    "alecg": "Curriculum Instructor",
    "dimas": "Designer",
}

number_of_staff = len(staff)

print(f"We have {number_of_staff} people on our staff.")  # We have 3 people on our staff.
```



#### Checking if an item is contained in a `dict`

To check if an item is contained in a `dict`, use the `in` operator:

```python
students = {
    "Vicki": "3rd grade",
    "Sam": "4th grade",
    "Tammy": "4th grade",
}  

if "Vicki" in students:
    print("Vicki is a student here")

```

Example Output:

```text
Vicki is a student here
```

You can use the `not` operator before the `in` operator to test if a key is not in a `dict`:

```python
students = {
    "Vicki": "3rd grade",
    "Sam": "4th grade",
    "Tammy": "4th grade",
}  

if "Daniel" not in students:
    print("Daniel is NOT a student here")

```

Example Output:

```text
Daniel is NOT a student here
```

##### `Using dict.get() to test if an item is in a dict`

The `dict.get()` method can be used as an alternative to `in` and `not` `in`. It returns the value of the given key or the special `None` value, which is used to indicate the absence of any valid value. The `is` operator is similar to `==`, but it checks if the two values are the same exact thing in memory:

```python
students = {
    "Vicki": "3rd grade",
    "Sam": "4th grade",
    "Tammy": "4th grade",
}  

if students.get("Vicki") is not None:
    print("Vicki is a student here")


if students.get("Daniel") is None:
    print("Daniel is NOT a student here")

```

Example Output:

```text
Vicki is a student here
Daniel is NOT a student here
```


#### Further reading

- [Real Python - Dictionaries in Python](https://realpython.com/python-dicts/)
- [The Python Library Reference - Mapping Types: `dict`](https://docs.python.org/3/library/stdtypes.html#mapping-types-dict)
- [The Python Tutorial - Dictionaries](https://docs.python.org/3/tutorial/datastructures.html#dictionaries)
- [Think Python - Dictionaries](https://greenteapress.com/thinkpython2/html/thinkpython2012.html)

<hr>







## Functions

Functions allow you to group related statements together to perform a task. They help to implement the __D.R.Y.__(Don't Repeat Yourself) principle because they reduce unnecessary repetition.


### Built-in functions

Python comes with many built-in functions. We'll cover some of the most common that you'll see in CodeWizardsHQ courses below. 

##### `float()`

The `float()` function converts data to a `float`:

```python
pi = float("3.14")

print(pi)  # 3.14
type(pi)  # <class 'float'>

two = float(2)

print(two)  # 2.0
type(two)  # <class 'float'>
```

##### `input()`

The `input()` function allows you to prompt a user. The user's response is returned as a `str`, which you can store in a variable:

```python
name = input("What is your name? ")
print(f"Nice to meet you, {name}!")
```

Example Output:

```text
What is your name? Daniel
Nice to meet you, Daniel!
```

##### `int()`

The `int()` function converts data to an `int`:

```python
int_pi = int(3.14)

print(int_pi)  # 3
type(int_pi)  # <class 'int'>

meaning_of_life = int("42")

print(meaning_of_life)  # 42
type(meaning_of_life)  # <class 'int'>
```

##### `len()`

The `len()` function returns the length of a sequence such as a `list` or `str`:

```python
number_of_characters = len("How many characters are in this str?")
print(number_of_characters)  # 36

favorite_foods = ["tacos", "pizza", "nachos", "burritos"]

number_of_foods = len(favorite_foods)
print(number_of_foods)  # 4
```


##### `list()`

The `list()` function creates a list from a sequence such as the result of `dict.keys()`, `dict.values()`, or a `str`:

```python
character_list = list("Hello!")
print(character_list)  # ['H', 'e', 'l', 'l', 'o', '!']

staff = {
    "danielj": "Curriculum Developer",
    "alecg": "Curriculum Instructor",
    "dimas": "Designer",
}

names = list(staff.keys())
print(names)  # ['danielj', 'alecg', 'dimas']

jobs = list(staff.values())
print(jobs)  # ['Curriculum Developer', 'Curriculum Instructor', 'Designer']
```


##### `print()`

The `print()` function displays text on the screen:

```python
print("Hello, world!")  # Hello, world!
```

###### Using special characters with `print()`

You can use special characters such as `\n` and `\t` to format the text a bit. The `\n` adds a newline (like hitting __enter__ on your keyboard) and the `\t` adds a tab:

```python
print("Line 1\nLine 2\nLine 3\n")
print("\tThis is tabbed over\n\tThis too.")
```

Example Output:

```text
Line 1
Line 2
Line 3

        This is tabbed over
        This too.
```

###### Using the splat (`*`) operator to print a `list`

You an use the splat (`*`) operator to print the items of a `list`:

```python
names = ["alecg", "danielj", "dimas"]

print(*names)  # alecg danielj dimas
```

###### Using the `sep` parameter

The `sep` parameter of `print()` let's you specifiy a given separator to add between each item passed to `print()`. It is commonly used in combination with the splat (`*`) operator to print the items of a `list` with a given separator between each item:

```python
names = ["alecg", "danielj", "dimas"]

print(*names, sep=" -- ")  # alecg -- danielj -- dimas
```



##### `range()`

The `range()` function is mainly used for [counter-controlled repetition](#counter-controlled-repetition) with a `for` loop:

```python
for num in range(1, 4):
    print(f"{num} potato")
```

Example Output:

```text
1 potato
2 potato
3 potato
```

Note that the last number is 3 in the example above, not 4!

###### Using the `step` parameter of the `range()` function

The `range()` function takes a third argument, `step`, which allows you to generate sequences of numbers separated by a given step:

```python
for num in range(1, 11, 3):
    print(num)

```

Example Output:

```text
1
4
7
10
```



##### `sorted()`

The `sorted()` function is used to sort a `list`:

```python
names = ["danielj", "alecg", "dimas"]
sorted_names = sorted(names)

print(sorted_names)  # ['alecg', 'danielj', 'dimas']
```

You can pass keyword arguments to the `sorted()` function to customize the way the `list` is sorted.

For example, the `key` argument can be a function to run on each item of the `list` before sorting:

```python
names = ["Danielj", "alecg", "Dimas"]
sorted_names = sorted(names)

# Notice how these aren't sorted correctly? Uppercase letters are "smaller"
# than lowercase letters in the sorting algorithm that `sort()` uses!
print(sorted_names)  # ['Danielj', 'Dimas', 'alecg']

sorted_names = sorted(names, key=str.lower)

# Now, everything is sorted correctly, and the original values haven't been
# changed. `sort()` only uses the `key` function during the sorting process.
print(sorted_names)  # ['alecg', 'Danielj', 'Dimas']
```
The `reverse` keyword argument of `sort()` is used to sort from high-to-low instead of low-to-high. It expects a `bool` value:

```python
names = ["danielj", "alecg", "dimas"]
reverse_sorted_names = sorted(names, reverse=True)

print(reverse_sorted_names)  # ['dimas', 'danielj', 'alecg']
```

##### `str()`

The `str()` function turns its argument into a `str` data type. This comes in handy if you have a number but want to treat it like a `str`:

```python
meaning_of_life = 42
print("The meaning of life is " + str(meaning_of_life)) 
```

Example Output:

```text
The meaning of life is 42
```

If you use `f-strings`, you don't have to worry about converting numbers to `str` when working with `str` data:

```python
meaning_of_life = 42
print(f"The meaning of life is {meaning_of_life}")
```

Example Output:

```text
The meaning of life is 42
```


#### Further reading

- [The Python Library Reference - Built-in Functions](https://docs.python.org/3/library/functions.html)









### User-defined functions

You define a function using the `def` keyword, and function definitions go at the TOP of your file:

```python
def say_hello():
    print("Hello!")


```

#### Calling a function

Defining a function does not run the statements in the body of the function. To run a function, you *call* it like this:

```python
def say_hello():
    print("Hello!")


say_hello()  # Hello!

```

#### Adding parameters to a function

When you define a function, you can add parameters that the function caller should pass in. Parameters are like variables, but the value of the variable is set by the function caller, not the function definer:

```python
def say_hello(name):
    print(f"Hello, {name}!")

```

#### Passing arguments to a function

If a function accepts parameters, you need to pass them in when you call the function. The values you pass to the function are called the *arguments* to the function:


```python
def say_hello(name):
    print(f"Hello, {name}!")


say_hello("Daniel")  # Hello, Daniel!
```

#### Returning a value from a function

You can return a value from a function by using the `return` keyword:

```python
def add(number_1, number_2):
    total = number_1 + number_2
    return total

```

#### Capturing a function's return value

If a function returns a value, you can capture it in a varible:

```python
def add(number_1, number_2):
    total = number_1 + number_2
    return total


total = add(2, 3)
print(total)  # 5
```

You can also use the value immediately in another function, like `print()`:

```python
def add(number_1, number_2):
    total = number_1 + number_2
    return total


print(add(2, 3))  # 5
print(f"2 + 3 = {add(2, 3)}")  # 2 + 3 = 5
```


#### Indentation in functions

The base-level of indentation in a function is 4 spaces. If you have another statement inside your function that also requires indentation (like a conditional statement or loop), you need to indent the body of that statement by 4 more spaces:

```python
def say_hello(name):
    print(f"Hello, {name}!")
    if name == "Daniel":
        print("That's a cool name!")
    else:
        print("Nice to meet you!")


say_hello("Daniel")
say_hello("Alec")
```

Example Output:

```text
Hello, Daniel!
That's a cool name!

Hello, Alec!
Nice to meet you!
```


#### Using an early `return` statement to exit a function

A `return` statement can be used to exit a function. This is normally used when you want to verify (with a conditional statement) that some preconditions are valid before continuing to execute a function body:

```python
def greet_codewizard(name):
    if name not in ["danielj", "alecg", "dimas"]:
        print("I don't know you!")
        return
    
    print(f"Hello, {name}!")


greet_codewizard("danielj")  # Hello, danielj!
greet_codewizard("django")   # I don't know you!

```



#### Further reading

- [Real Python - Defining Your Own Python Function](https://realpython.com/defining-your-own-python-function/)
- [The Python Tutorial - Defining Functions](https://docs.python.org/3/tutorial/controlflow.html#defining-functions)
- [Think Python - Functions](https://greenteapress.com/thinkpython2/html/thinkpython2004.html)
- [Think Python - Fruitful Functions](https://greenteapress.com/thinkpython2/html/thinkpython2007.html)

<hr>





## Loops

If you need to repeat something in your programs, you'll need to use one of Python's looping mechanisms.


### `for`

A `for` loop is generally used to loop over a sequence, such as a `list`:


```python
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)
```

Example Output:

```text
apple
banana
cherry
```

You can also use a `for` loop to loop over the characters in a `str`:

```python
name = "Daniel"

for letter in name:
    print(letter)
```

Example Output:

```text
D
a
n
i
e
l
```

#### Counter-controlled repetition

You can combine the `range()` function and the `for` loop to create a counter-controlled loop:

```python
for num in range(1, 4):
    print(f"{num} potato")
```

Example Output:

```text
1 potato
2 potato
3 potato
```


#### Searching for a value in a `for` loop

You can use a conditional statement inside a `for` loop to search for a particular item in a `list` and then do something. Note the indentation:

```python
fruits = ["orange", "banana", "cherry", "apple"]

for fruit in fruits:
    if fruit == "orange":
        print(f"{fruit} is the best fruit")
```

Example Output:

```text
orange is the best fruit
```


#### Finding a value in a `for` loop to use after the loop finishes

You can store an item from the `for` loop for later use by creating a variable before the `for` loop with some default value.

```python
fruits = ["orange", "banana", "cherry", "apple"]

# The best_fruit will be a str, so the empty str is a good default.
best_fruit = ""

for fruit in fruits:
    if fruit == "orange":
        best_fruit = fruit


# The best fruit is orange.
print(f"The best fruit is {best_fruit}.")
```



#### Creating a new `list` in a `for` loop

Often, you'll want to loop through a `list` and build a new `list` from the contents of the original `list`. This technique is called mapping, and it's a common thing to do with `lists` and `for` loops:

```python
prices = [10, 12, 5, 8]
discounted_prices = []

for price in prices:
    discounted_price = price - (price * .10)
    discounted_prices.append(discounted_price)


# Here are your discounted prices:[9, 10.8, 4.5, 7.2]
print(f"Here are your discounted prices: {discounted_prices}")
```

#### Creating a `list` of a pre-determined size with a `for` loop

Using a `for` loop and the `range()` function, you can fill a `list` to a pre-determined size:

```python
fruits = []

for num in range(1,5):
    fruit = input(f"Enter fruit number {num}: ")
    fruits.append(fruit)

```

Example Output:

```text
Enter fruit number 1: apples
Enter fruit number 2: bananas
Enter fruit number 3: oranges
Enter fruit number 4: kiwi
```




#### Further reading

- [Real Python - Python `for` Loops](https://realpython.com/python-for-loop/)
- [The Python Tutorial - `for` Statements](https://docs.python.org/3/tutorial/controlflow.html#for-statements)
- [The Python Tutorial - The `range()` function](https://docs.python.org/3/tutorial/controlflow.html#the-range-function)
- [Think Python - Traversal with a `for` loop](https://greenteapress.com/thinkpython2/html/thinkpython2009.html#sec94)
















### `while`

A `while` loop is generally used to perform indefinite repetition (when you don't know how many times you want to loop).

For example, you can use a `while` loop to ask a user something until they answer correctly:

```python
keep_looping = True  # This variable controls whether we loop or not.

while keep_looping:
    user_guess = input("What is the meaning of life? ")
    
    if user_guess == "42":
        print("That's correct!")
        keep_looping = False  # Stops the loop.
    else:
        print("That's incorrect! Please try again.")
```

Example Output:

```text
What is the meaning of life? To make money
That's incorrect! Please try again.
What is the meaning of life? To eat tacos
That's incorrect! Please try again.
What is the meaning of life? 42
That's correct!
```

#### Using `break` to exit a loop

You can also use a `break` statement instead of using a variable to control how many times an indefinite `while` loop runs:

```python
while True:
    user_guess = input("What is the meaning of life? ")
    
    if user_guess == "42":
        print("That's correct!")
        break  # Stops the loop.
    else:
        print("That's incorrect! Please try again.")
```

Example Output:

```text
What is the meaning of life? To make money
That's incorrect! Please try again.
What is the meaning of life? To eat tacos
That's incorrect! Please try again.
What is the meaning of life? 42
That's correct!
```

#### Counter-controlled repetition

You can use a `while` loop to perform counter-controlled repetition as well, but
the `for` loop with the `range()` function is generally preferred:

```python
counter = 0

while counter < 5:
    print(counter)
    counter += 1  # If you forget this, you'll have an infinite loop!
```

Example Output:

```text
0
1
2
3
4
```







#### Further reading

- [Real Python - Python `while` Loops](https://realpython.com/python-while-loop/)
- [Think Python - The `while` statement](https://greenteapress.com/thinkpython2/html/thinkpython2008.html#sec84)


<hr>






## Math Operations

Python is used heavily in math-related fields, so there are a large suite of tools for performing mathematical operations built-in to the language.


### Arithmetic Operators

The four basic arithmetic operations (addition, subtraction, multiplication, division) are similar to how you would use them with calculator:

```python
total = 8 + 2
difference = 8 - 2
product = 8 * 2
quotient = 8 / 2

print(f"8 + 2 = {total}")       # 8 + 2 = 10
print(f"8 - 2 = {difference}")  # 8 - 2 = 6
print(f"8 * 2 = {product}")     # 8 * 2 = 16
print(f"8 / 2 = {quotient}")    # 8 / 2 = 4.0
```

Note that in the example above, division *always* produces a `float`. 

#### Arithmetic only works between numbers

Both data types *must* be numeric data types, you __cannot__ perform arithmetic between a `str` and a number.

```python
num_tacos =  2  + "1"  # no
num_tacos = "2" + "1"  # no

num_tacos = "1" *  3   # no
num_tacos = "1" * "3"  # no
```


### Other Operators

There are a few other common operators that Pythonistas use when performing math in Python. 

#### Modulo

The modulo operator (`%`) returns the remainder after division:

```python
10 % 3  # 1
```

#### Power

The power operator (`**`) multiplies a number by itself a given number of times:

```python
3 ** 2  # 9
```

#### Floor division

The floor division operator (`//`) removes any fractional portion after divison:

```python
10 // 3  # 3
```


#### Further reading

- [The Python Tutorial - Numbers](https://docs.python.org/3/tutorial/introduction.html#numbers)
- [Real Python - Numbers in Python](https://realpython.com/python-numbers/)

<hr>







## Modules

Python is often called a batteries-included language because of the plethora of built-in modules that the language contains. Modules are just Python files full of functionality that you don't have to write yourself; you merely import the things you want from a module and use them in your programs.


### Getting access to functions in modules

To get a function from a module, you import it. There are several different types of imports, which we'll briefly cover below.

#### Importing a single function

To import a single function, just write the function name (without parentheses) after the `import` keyword:

```python
from module_name import function_name
```

#### Importing multiple functions

If you need to import multiple functions from a module, separate them by commas:

```python
from module_name import some_function, some_other_function
```

#### Importing all functions

To import all items from a module (not recommended generally, but we do this in some courses like E24 and M11), use the `*` import syntax:

```python
from module_name import *
```

#### Renaming imported functions

Sometimes, its nice to rename a function you import from a module (like when the function name is really long or confusing). You can do this using the `as` keyword:

```python
from module_name import some_really_long_function_name as short_name
```

#### Further reading

- [The Python Library Reference](https://docs.python.org/3/library/index.html)
- [The Python Tutorial - Modules](https://docs.python.org/3/tutorial/modules.html)
- [Real Python - Python Modules and Packages](https://realpython.com/python-modules-packages/)











### Built-in modules

Python comes with 100s of built-in modules. We'll briefly cover a few that are used often at CWHQ in this section. See the *Further Reading* section for details on where you can browse all of Python's built-in modules.

#### random

The `random` module is used to add randomness to your programs. 

##### `Getting a random integer`

You use the `randint()` function to get a random integer between two numbers:

```python
from random import randint

# Get an integer between 1 and 10
random_integer = randint(1, 10)
print(random_integer)  # 3
```

##### `Getting a random value from a sequence`

You use the `choice()` function to get a random value from a sequence (`str`, `list`, or `tuple`):

```python
from random import choice

names = ["daniel", "alec", "dima"]
random_name = choice(names)

print(random_name)  # dima
```

#### Further reading

- [The Python Standard Library](https://docs.python.org/3/library/index.html)
- [The Python Standard Library - `random`](https://docs.python.org/3/library/random.html)

<hr>









## The `pass` statement

You use the pass statement to act as a placeholder in a conditional statement or function definition. Programmers refer to this as "stubbing-out" the code block. No logic will run in the block a `pass` statement appears in. Python needs the `pass` statement because you can't have empty function or conditional blocks.

#### Using `pass` in a function

The `pass` statement can be used in a function definition as a placeholder before you write the main logic. This ensures your program still works but gives you a convenient way to see that you still need to implement some logic:


```python
def order_pizza():
    pass

```

#### Using `pass` in a conditional statement

The `pass` statement can also be used in a conditioal statement. This comes in handy if you know that you need a conditional statement but you don't have any of the logic ready yet:


```python
action = input("What do you want to do? ")

if action == "Order Pizza":
    order_pizza()
elif action == "Order Tacos":
    pass

```









## Variables

Variables assign a name to a value. The naming convention in Python is to use *snake_case* for variable names, and *UPPER_SNAKE_CASE* for named constants.

### Creating a variable

You create a variable by assigning a name to a value using the assignment operator (`=`):

```python
my_name = "Daniel"
my_age = 35
```

### Creating a named constant

Named constants can replace *magic numbers* in your program.

For example, what does `1` and `2` represent here?

```python
if user_choice == 1:
    # Do something cool...
elif user_choice == 2:
    # Do another cool thing...

```

`1` and `2` in the example above are *magic numbers* because we would have to hunt down their meaning by reading more of the program. If we instead create a named constant for each, the meaning is clearer:

```python
ORDER_TACOS = 1
ORDER_PIZZA = 2

if user_choice == ORDER_TACOS:
    # Order tacos...
elif user_choice == ORDER_PIZZA:
    # Order pizza

```

### Updating the value of a variable

You can update the value stored in a variable like this:

```python
score = 0
score = score + 1 	# 0 + 1

print(score) 		# 1

score = score + 1 	# 1 + 1

print(score) 		# 2
```

The same works for decreasing the value of a variable:


```python
score = 3
score = score - 1 	# 3 - 1

print(score) 		# 2

score = score - 1 	# 2 - 1

print(score) 		# 1
```


There's also a shorthand notation:

```python
score = 0
score += 1 	  # 0 + 1

print(score)  # 1

score += 1 	  # 1 + 1

print(score)  # 2

score -= 1    # 2 - 1

print(score)  # 1

score -= 1    # 1 - 1

print(score)  # 0
```


### Global variables

Any variable created outside of function definition is considered a `global` variable. If you want to modify a `global` variable from *inside* a function definition, you need to use the `global` keyword:

```python
# This is a global variable
score = 0 

def update_score():
    # Must do this to modify the variable
    global score
    # Now this is OK
    score = score + 1	# 1
```



### Further reading

- [Real Python - Variables in Python](https://realpython.com/python-variables/)
- [Think Python - Variables, expressions and statements](https://greenteapress.com/thinkpython2/html/thinkpython2003.html)