# 📝 Apunts: Bucles i Estructures de Control en Python

## 1. Estructures de Control (`if`, `elif`, `else`)

S'utilitzen per a la presa de decisions. El programa executa un bloc de codi o un altre segons si es compleix una condició.

* `if`: S'executa si la condició és certa.
* `elif` (abreviatura de else if): Es fa servir per comprovar una segona condició si la primera ha fallat.
* `else`: S'executa si cap de les condicions anteriors és certa.

## 2. El Bucle `for` i la funció `range()`

S'utilitza quan sabem exactament quantes vegades volem repetir una acció (iteracions definides).

* `range(5)`: Genera una seqüència de 0 a 4 (5 números en total).
* `range(1, 11)`: Genera números de l'1 al 10 (el darrer número no s'inclou).

## 3. El Bucle `while`

S'utilitza quan volem repetir un bloc de codi mentre una condició sigui vertadera.

# Exemple de menú
```python
#Exemple de menú

option = 0

while option != 3:
    print("\n--- GESTIÓ DEL SISTEMA ---")
    print("1. Actualitzar")
    print("2. Reiniciar Apache")
    print("3. Sortir")

    option = int(input("Tria una opció: "))

    if option == 1:
        print(">> Executant: sudo apt-get update && upgrade...")
    elif option == 2:
        print(">> Executant: systemctl restart apache2...")
    elif option == 3:
        print(">> Tancant la sessió d'administrador. Adeu!")
    else:
        print(">> ERROR: Opció no vàlida.")
```

# Catching a Pokémon
```python
#Catching a Pokémon

attempts = 5
is_caught = False

print("A wild Mewtwo appeared!")

while attempts > 0 and not is_caught:
    print(f"\nRemaining attempts: {attempts}")
    ball_type = input("Throw ball (Masterball / Ultraball / Pokeball): ").lower()

    if ball_type == "masterball":
        print("Guaranteed catch! Mewtwo was caught!")
        is_caught = True
    elif ball_type == "ultraball":
        print("Close! But Mewtwo broke free...")
        attempts -= 1  # Equivalent a attempts = attempts - 1
    else:
        print("It's not very effective... Mewtwo didn't move.")
        attempts -= 1

if is_caught:
    print("Congratulations! You are a Pokemon Master.")
else:
    print("\nMewtwo ran away...")
```

# Training Pokemon
```python
#Training Pokemon

pokemon_name = "Charmander"

for level in range(1, 37):
    if level == 16:
        pokemon_name = "Charmeleon"
        print(f"--> What? Your Pokemon is evolving into {pokemon_name}!")
    elif level == 36:
        pokemon_name = "Charizard"
        print(f"--> Amazing! It evolved into {pokemon_name}!")
    else:
        # Imprimim el progrés cada 5 nivells per no saturar la consola
        if level % 5 == 0:
            print(f"{pokemon_name} reached level {level}...")

print(f"\nTraining finished. You now have a powerful {pokemon_name}!")
```

# Shopping in LOL
```python
#Shopping in LOL

gold = 2000
option = -1
count_boots = 0
count_sword = 0

print(f"Welcome to the shop! You have {gold} gold.")

while option != 0:
    print("\nItems available: 1. Boots (400) | 2. BF Sword (1300) | 0. Exit")
    print(f"Current inventory: Boots: {count_boots} - Swords: {count_sword}")
    option = input("What do you want to buy (Insert a number)?: ")

    if option == "1":
        if gold >= 400:
            gold -= 400
            count_boots += 1
            print(f"Purchased: Boots! Remaining gold: {gold}")
            
        else:
            print("Not enough gold for Boots.")
    elif option == "2":
        if gold >= 1300:
            gold -= 1300
            count_sword += 1
            print(f"Purchased: BF Sword! Remaining gold: {gold}")
        else:
            print("Not enough gold for BF Sword.")
    elif option == "3":
        print("Leaving the fountain. Good luck on the Rift!")
        option = 0
    else:
        print("Invalid option. The shopkeeper is confused.")

    if gold < 400:
        print("You are too poor to buy anything else. Go farm!")
```
