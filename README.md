# Godot




> Creare un nodo e rinominarlo in Main 
<img width="1505" alt="Screenshot 2025-01-29 alle 15 46 57" src="https://github.com/user-attachments/assets/40cdb28f-fc67-4e38-b2d2-75c2aa985dce" />
<img width="1492" alt="Screenshot 2025-01-29 alle 15 48 22" src="https://github.com/user-attachments/assets/322fcd55-a1d8-4018-be42-f0e5259a9441" />

___________________________________


```
#main 
func _ready() -> void:
	print("hello word")
```


___________________________________



# Aggiungere un elemento al Nodo




<img width="891" alt="Screenshot 2025-01-29 alle 17 40 11" src="https://github.com/user-attachments/assets/d45a493e-1940-4167-a9b1-02f77d529f1b" />


```
func _ready() -> void:
	print("hello word")
	$Label.text = "Wooow So Awesome"
	$Label.modulate = Color.YELLOW_GREEN

```


______________________________

## Input


Progetto > Impostazione di Progetto > Mappa di Input 




<img width="1501" alt="Screenshot 2025-01-31 alle 11 24 15" src="https://github.com/user-attachments/assets/c6c1dd4c-f724-4b7a-bd3f-7f28ba0c442f" />



Premi + , e aggiungi ad esempio la barra spaziatrice.


<img width="1197" alt="Screenshot 2025-01-31 alle 11 26 03" src="https://github.com/user-attachments/assets/1a2177a6-d861-4fb1-83cb-0c3cb996e33f" />

Nella parte di Scripting :

```
func _input(event: InputEvent) -> void:
	if(event.is_action_pressed("my_action")):
		$Label.modulate = Color.RED
	if(event.is_action_released("my_action")):
		$Label.modulate = Color.YELLOW_GREEN

```

______________________________

## Variables 


```
var health = 100
```

In Godot, data types are essential for defining the kind of data that can be stored in variables, passed to functions, and returned from functions.
Godot uses a variety of built-in data types, which can be categorized into several groups:

### Basic Data Types

1. **Primitive Types:**
   - `int`: Represents integer values (e.g., `1`, `42`, `-7`).
   - `float`: Represents floating-point numbers (e.g., `3.14`, `-0.001`).
   - `String`: Represents text strings (e.g., `"Hello, World!"`).
   - `bool`: Represents boolean values (`true` or `false`).

2. **Variant Type:**
   - `Variant`: A flexible type that can hold any of the above types and more. It is used when the type of data is not known at compile time.

### Collection Types

1. **Array:**
   - A dynamic array that can hold multiple values of any type. Example: `var my_array = [1, 2, 3, "Hello"]`.

2. **Dictionary:**
   - A collection of key-value pairs, similar to a hash table or map. Example: `var my_dict = {"name": "Alice", "age": 30}`.

### Object Types

- **Node:** The base class for all scene objects in Godot. Custom scripts can extend `Node` or any of its subclasses.
- **Resource:** A base class for data resources that can be saved and reused, such as textures, sounds, and scripts.

### Custom Types

- You can define your own data types using classes. For example, you can create a custom class to represent a player or an enemy in your game.

### Type Checking

Godot provides a way to check the type of a variable using the `typeof()` function, which can be useful for debugging or ensuring that the correct types are being used in your code.

### Example Usage


```gdscript
extends Node

var my_int: int = 42
var my_float: float = 3.14
var my_string: String = "Hello, Godot!"
var my_bool: bool = true
var my_array: Array = [1, 2, 3, "four"]
var my_dict: Dictionary = {"key": "value", "number": 123}

func _ready():
    print(my_int)
    print(my_float)
    print(my_string)
    print(my_bool)
    print(my_array)
    print(my_dict)
```







