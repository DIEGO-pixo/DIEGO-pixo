import random
import time

def imprimir_pista(posicion1, posicion2):
    pista = ["-"] * 20
    pista[posicion1] = "🚗"
    pista[posicion2] = "🏎️"
    print("".join(pista))

def carrera():
    posicion1 = 0
    posicion2 = 0
    
    print("¡Comienza la carrera!")
    imprimir_pista(posicion1, posicion2)
    
    while posicion1 < 19 and posicion2 < 19:
        time.sleep(0.5)  # Pausa para hacer la carrera más visual
        
        posicion1 += random.randint(0, 2)
        posicion2 += random.randint(0, 2)
        
        posicion1 = min(posicion1, 19)
        posicion2 = min(posicion2, 19)
        
        imprimir_pista(posicion1, posicion2)
    
    if posicion1 >= 19 and posicion2 >= 19:
        print("¡Es un empate!")
    elif posicion1 >= 19:
        print("¡El coche 🚗 ha ganado!")
    else:
        print("¡El coche 🏎️ ha ganado!")

carrera()
