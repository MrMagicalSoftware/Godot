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


