# reto 8 

## punto 1: De los retos anteriores selecione 3 funciones y escribalas en forma de lambdas
### a)
```python
#funciones tomadas del reto 4
#funcion 1
def ascii_par(str): #saber si el numero del codigo ascii de un unico caracter es par o no
    n_codigo=ord(str[0]) #indice para acceder al primer caracter de la cadena
    return n_codigo%2==0
```
```python
ascii_par = lambda str: ord(str[0]) % 2 == 0
```
### b)
```python
# funcion 2
def multiplo(x, y): #saber si elprimero es multiplo del segundo
    if y == 0:
        return False #porque no se puede dividir entre 0(bueno mas bien esta indefinido)
    return x%y == 0
```
```python
multiplo = lambda x, y: False if y == 0 else x % y == 0
```
### c)
```python
#funcion 3
def ubicacion_punto(r, c_en_x, c_en_y, punto_en_x, punto_en_y):
    formula_dist = (punto_en_x - c_en_x)**2 + (punto_en_y-c_en_y)**2 #formula de distancia entre dos puntos
    return formula_dist<= r**2
```
```python
ubicacion_punto = lambda r, c_en_x, c_en_y, punto_en_x, punto_en_y: (punto_en_x - c_en_x)**2 + (punto_en_y - c_en_y)**2 <= r**2
```

## punto 2: De los retos anteriores selecione 3 funciones y escribalas con argumentos no definidos (*args)
### a)
```python
#funcion 1
x = int(input("numero elegido: "))
if x>=2:
  s = x - 1 if x % 2 != 0 else x - 2
  for n in range(s, 1, -2):
        print(n)
#se modifico para que acepte mas argumentos
```
```python
def imprimir_numeros(*args):
    x = args[0] if args else int(input("Número elegido: "))
    if x >= 2:
        s = x - 1 if x % 2 != 0 else x - 2
        for n in range(s, 1, -2):
            print(n)
```
### b)
```python
x= int(input("ingrese numero: "))
if x>1:
 fac=1
 for i in range (1, x+1):
   fac *= i #asignacion multiplicacion
   print(f"{i}! = {fac}")
else:
  print("el numero debe ser natural")
```
```python
def factorial(*args):
    if args:
        x = args[0]  # Si se pasa un número como argumento
    else:
        x = int(input("Ingrese número: "))  # Si no, pedirlo al usuario

    if x > 1:
        fac = 1
        for i in range(1, x + 1):
            fac *= i
            print(f"{i}! = {fac}")
    else:
        print("El número debe ser natural")
```
### c)
```python
# funcion 3 (se modifico para que recibiera un argumento)
def esfera(r1):
    volume_esfera= (4/3)*math.pi*(r1**3)
    area_esfera= 4*math.pi*(r1**2)
    return volume_esfera, area_esfera
```
```python
def esfera(*args):
    if args: 
        r1 = args[0]
    else:
        r1 = float(input("Ingrese el radio de la esfera: "))  #se pide al usuario si no hay arguento
    
    volume_esfera = (4/3) * math.pi * (r1 ** 3)
    area_esfera = 4 * math.pi * (r1 ** 2)
    return volume_esfera, area_esfera
```

## punto 3: Escriba una función recursiva para calcular la operación de la potencia
```python
def potencia(base, exponente):
    if exponente == 0:
        return 1
    else:
        return base * potencia(base, exponente - 1)

resultado = potencia(2, 2)
print(resultado)
```

## punto 4:
```python
import time

def fibonacci_iterativa(n):
    a, b = 0, 1
    for _ in range(n):
        a, b = b, a + b ## cada número es la suma de los dos anteriores, El valor actual de b (el número de Fibonacci siguiente) se asigna a "a" y el nuevo valor de b se establece como la suma de a y b de la iteración anterior. Este es el siguiente número de Fibonacci.
    return a

def medir_iterativa(n):
    start_time = time.time()
    fibonacci_iterativa(n)
    end_time = time.time()
    return end_time - start_time

for n in range(150000, 400000, 1000):  # probar valores 
    tiempo_iterativa = medir_iterativa(n)
    print(f"Fibonacci({n}) - Iterativa: {tiempo_iterativa:.6f} segundos")

# al ejecutarse podemos ver que en la posicion 349000 tarda por primera vez mas de un segundo
```
![image](https://github.com/user-attachments/assets/a7db2f97-eb0c-426f-af9d-15348f9b7e66)

## punto 5:
![image](https://github.com/user-attachments/assets/9edfe939-9658-48ee-8d8d-4c57db8cce6b)

## punto 6:
![image](https://github.com/user-attachments/assets/665dcfb6-9571-4093-8784-b8b3795255e6)

