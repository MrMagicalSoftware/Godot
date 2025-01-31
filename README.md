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


__________________________________________



In Godot, le condizionali sono utilizzate per eseguire diverse azioni in base a determinate condizioni. Le strutture condizionali più comuni in GDScript sono `if`, `elif` e `else`. Ecco una panoramica di come funzionano:

### Struttura di base

1. **`if`**: Controlla se una condizione è vera e, in tal caso, esegue il blocco di codice associato.
2. **`elif`**: (abbreviazione di "else if") consente di controllare ulteriori condizioni se la condizione precedente è falsa.
3. **`else`**: Esegue un blocco di codice se tutte le condizioni precedenti sono false.

### Sintassi

Ecco la sintassi di base per le condizionali in GDScript:

```gdscript
if condition1:
    # Codice da eseguire se condition1 è vera
elif condition2:
    # Codice da eseguire se condition1 è falsa e condition2 è vera
else:
    # Codice da eseguire se tutte le condizioni precedenti sono false
```

### Esempio

Ecco un esempio pratico di utilizzo delle condizionali in GDScript:

```gdscript
extends Node

var score: int = 85

func _ready():
    if score >= 90:
        print("Ottimo lavoro! Hai ottenuto un A.")
    elif score >= 80:
        print("Buon lavoro! Hai ottenuto un B.")
    elif score >= 70:
        print("Hai passato! Hai ottenuto un C.")
    else:
        print("Non hai passato. Riprova!")
```

### Operatori di confronto

Puoi utilizzare vari operatori di confronto nelle condizioni, tra cui:

- `==`: uguale a
- `!=`: diverso da
- `<`: minore di
- `>`: maggiore di
- `<=`: minore o uguale a
- `>=`: maggiore o uguale a

### Operatori logici

Puoi anche combinare più condizioni utilizzando operatori logici:

- `and`: restituisce vero se entrambe le condizioni sono vere.
- `or`: restituisce vero se almeno una delle condizioni è vera.
- `not`: restituisce vero se la condizione è falsa.

### Esempio con operatori logici

```gdscript
var age: int = 20
var has_permission: bool = true

func _ready():
    if age >= 18 and has_permission:
        print("Puoi entrare.")
    else:
        print("Accesso negato.")
```

_______________________________________-


# Casting


In Godot, il "casting" si riferisce al processo di conversione di un valore da un tipo di dato a un altro. 
Questo è utile quando si desidera garantire che una variabile sia di un tipo specifico prima di utilizzarla in operazioni o funzioni che richiedono quel tipo. 

### Tipi di Casting in GDScript

1. **Casting tra tipi primitivi**: Puoi convertire tra tipi come `int`, `float`, e `String`.
2. **Casting di oggetti**: Puoi convertire un oggetto di una classe base in un oggetto di una classe derivata.

### Esempi di Casting

#### 1. Casting tra tipi primitivi


```gdscript
var my_float: float = 3.14
var my_int: int = int(my_float)  # Converte float in int
print(my_int)  # Output: 3

var my_string: String = "42"
var my_number: int = int(my_string)  # Converte String in int
print(my_number)  # Output: 42
```

#### 2. Casting di oggetti

Quando si lavora con oggetti, si può utilizzare il casting per convertire un oggetto di una classe base in un oggetto di una classe derivata. 
Questo è utile quando si lavora con nodi o risorse in Godot.

```gdscript
extends Node

func _ready():
    var node: Node = get_node("MyNode")
    
    # Casting di un nodo a un tipo specifico
    var my_sprite: Sprite = my_sprite as Sprite
    if my_sprite:
        my_sprite.texture = preload("res://path/to/texture.png")
    else:
        print("Il nodo non è un Sprite.")
```

### Uso di `is` e `as`

- **`is`**: Verifica se un oggetto è di un certo tipo.
- **`as`**: Esegue il casting di un oggetto a un tipo specifico e restituisce `null` se il casting non è possibile.

Ecco un esempio di utilizzo di `is` e `as`:

```gdscript
var node: Node = get_node("MyNode")

if node is Sprite:
    var my_sprite: Sprite = node as Sprite
    my_sprite.texture = preload("res://path/to/texture.png")
else:
    print("Il nodo non è un Sprite.")
```

### Considerazioni sul Casting

- Il casting è utile per garantire che il  codice funzioni correttamente con i tipi di dati previsti.
- È importante gestire i casi in cui il casting potrebbe fallire, specialmente quando si lavora con oggetti, per evitare errori di runtime.




____________

# static typing

```
var damage : int = 10 
```

**typing di inferenza**
```
var damge :=15
```
______________



# Uso di Export



In Godot, l'annotazione `@export` (precedentemente nota come `export`) è utilizzata per esporre variabili di un script all'editor di Godot. Questo consente agli sviluppatori di modificare facilmente i valori delle variabili direttamente dall'editor senza dover modificare il codice sorgente. È particolarmente utile per configurare parametri di oggetti, nodi e risorse in modo visivo.

### Utilizzi principali di `@export`

1. **Modifica dei valori nell'editor**: Le variabili contrassegnate con `@export` possono essere modificate direttamente nell'Inspector dell'editor di Godot, rendendo più semplice la personalizzazione delle proprietà degli oggetti.

2. **Tipi di dati supportati**: Puoi esportare variabili di vari tipi, inclusi `int`, `float`, `String`, `bool`, `Array`, `Dictionary`, e anche oggetti come `Node` o `Resource`.

3. **Tipizzazione**: Puoi specificare il tipo di dato della variabile esportata, il che aiuta a mantenere il codice più chiaro e a prevenire errori.

### Esempio di utilizzo

Ecco un esempio di come utilizzare `@export` in uno script GDScript:

```gdscript
extends Node

@export var speed: float = 10.0
@export var player_name: String = "Giocatore"
@export var is_active: bool = true
@export var health: int = 100

func _ready():
    print("Nome del giocatore: ", player_name)
    print("Velocità: ", speed)
```

In questo esempio:

- `speed`, `player_name`, `is_active`, e `health` sono variabili esportate.
- Puoi modificare questi valori direttamente nell'Inspector dell'editor di Godot, il che rende facile testare e configurare il comportamento del tuo gioco senza dover modificare il codice.

### Vantaggi di `@export`

- **Facilità d'uso**: Gli sviluppatori e i designer possono modificare le proprietà degli oggetti senza dover toccare il codice.
- **Flessibilità**: Consente di testare rapidamente diverse configurazioni e valori.
- **Organizzazione**: Aiuta a mantenere il codice più pulito e organizzato, separando la logica di gioco dalla configurazione.

### Considerazioni

- L'annotazione `@export` è particolarmente utile per i parametri che potrebbero dover essere regolati frequentemente durante lo sviluppo o il bilanciamento del gioco.
- È importante notare che le variabili esportate sono visibili solo nell'Inspector e non possono essere modificate durante l'esecuzione del gioco, a meno che non vengano aggiornate tramite codice.












