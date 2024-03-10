# Generador de Contraseñas Aleatorias en Python

import random
import string

def generar_contraseña(longitud, complejidad):
    caracteres = ""
    if "letras" in complejidad:
        caracteres += string.ascii_letters
    if "numeros" in complejidad:
        caracteres += string.digits
    if "simbolos" in complejidad:
        caracteres += string.punctuation

    contraseña = ''.join(random.choice(caracteres) for i in range(longitud))
    return contraseña

longitud = int(input("Ingrese la longitud de la contraseña: "))
print("Ingrese la complejidad deseada (separe las opciones por comas):")
print("1. Letras")
print("2. Números")
print("3. Símbolos")
complejidad = input("Opciones: ").lower().split(',')

contraseña_generada = generar_contraseña(longitud, complejidad)
print("Contraseña generada:", contraseña_generada)
