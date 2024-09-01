
# Ejemplos de Uso de Ciclos Anidados en Python

Este documento proporciona ejemplos prácticos de cómo usar ciclos anidados en Python, particularmente para operar con arreglos bidimensionales y realizar otras operaciones comunes.

## 1. Recorrer una Matriz (Lista de Listas)

Este es un ejemplo básico donde se recorre una matriz de 3x3 y se imprimen todos sus elementos:

```python
matriz = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

for fila in matriz:  # Ciclo exterior que recorre cada fila
    for elemento in fila:  # Ciclo interior que recorre cada elemento de la fila
        print(elemento, end=" ")
    print()  # Salto de línea para separar las filas en la salida
```

## 2. Suma de Todos los Elementos en una Matriz

Aquí sumamos todos los elementos de una matriz utilizando ciclos anidados:

```python
matriz = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

suma_total = 0

for fila in matriz:
    for elemento in fila:
        suma_total += elemento  # Suma cada elemento a suma_total

print("La suma de todos los elementos es:", suma_total)
```

## 3. Transposición de una Matriz

La transposición de una matriz consiste en intercambiar las filas por las columnas. Este ejemplo demuestra cómo hacerlo:

```python
matriz = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

transpuesta = []

for i in range(len(matriz[0])):  # Recorre las columnas de la matriz original
    nueva_fila = []
    for j in range(len(matriz)):  # Recorre las filas de la matriz original
        nueva_fila.append(matriz[j][i])
    transpuesta.append(nueva_fila)

print("Matriz transpuesta:")
for fila in transpuesta:
    print(fila)
```

## 4. Multiplicación de Matrices

La multiplicación de dos matrices es un ejemplo típico donde se usan ciclos anidados:

```python
A = [
    [1, 2],
    [3, 4]
]

B = [
    [5, 6],
    [7, 8]
]

resultado = [
    [0, 0],
    [0, 0]
]

# Multiplicación de matrices
for i in range(len(A)):  # Recorre las filas de A
    for j in range(len(B[0])):  # Recorre las columnas de B
        for k in range(len(B)):  # Recorre las filas de B
            resultado[i][j] += A[i][k] * B[k][j]

print("Resultado de la multiplicación de matrices:")
for fila in resultado:
    print(fila)
```

## 5. Generación de una Tabla de Multiplicar

Este ejemplo genera una tabla de multiplicar del 1 al 10 utilizando ciclos anidados:

```python
for i in range(1, 11):  # Ciclo exterior para el primer factor
    for j in range(1, 11):  # Ciclo interior para el segundo factor
        print(f"{i} x {j} = {i * j}", end="	")
    print()  # Salto de línea después de cada fila
```

## 6. Impresión de un Patrón de Números

Este ciclo anidado genera un patrón numérico en forma de pirámide:

```python
n = 5

for i in range(1, n + 1):  # Ciclo exterior que controla las filas
    for j in range(1, i + 1):  # Ciclo interior que controla los elementos de cada fila
        print(j, end=" ")
    print()  # Salto de línea después de cada fila
```

**Salida:**
```
1
1 2
1 2 3
1 2 3 4
1 2 3 4 5
```

## 7. Búsqueda de un Valor en una Matriz

Si quieres buscar un valor específico en una matriz, puedes hacerlo con ciclos anidados:

```python
matriz = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

valor_a_buscar = 5
encontrado = False

for i in range(len(matriz)):
    for j in range(len(matriz[i])):
        if matriz[i][j] == valor_a_buscar:
            print(f"Valor {valor_a_buscar} encontrado en la posición ({i}, {j})")
            encontrado = True
            break
    if encontrado:
        break

if not encontrado:
    print(f"Valor {valor_a_buscar} no encontrado en la matriz.")
```


# Ejemplos de Uso de Ciclos Anidados con Diccionarios en Python

Este documento proporciona ejemplos prácticos de cómo usar ciclos anidados con diccionarios en Python, particularmente para trabajar con diccionarios anidados y realizar operaciones comunes.

## 8. Recorrer un Diccionario con Diccionarios Anidados

Este es un ejemplo básico donde se recorre un diccionario anidado y se imprimen todos sus elementos:

```python
personas = {
    "Juan": {"edad": 28, "ciudad": "Bogotá", "profesión": "Ingeniero"},
    "María": {"edad": 32, "ciudad": "Medellín", "profesión": "Doctora"},
    "Pedro": {"edad": 24, "ciudad": "Cali", "profesión": "Diseñador"}
}

for nombre, info in personas.items():
    print(f"Información de {nombre}:")
    for clave, valor in info.items():
        print(f"  {clave}: {valor}")
```

## 9. Sumar Valores en un Diccionario Anidado

Aquí sumamos los valores de un diccionario anidado para calcular el total de ventas por producto:

```python
ventas = {
    "enero": {"producto1": 100, "producto2": 200, "producto3": 150},
    "febrero": {"producto1": 120, "producto2": 240, "producto3": 130},
    "marzo": {"producto1": 130, "producto2": 210, "producto3": 170}
}

totales = {}

for mes, productos in ventas.items():
    for producto, cantidad in productos.items():
        if producto in totales:
            totales[producto] += cantidad
        else:
            totales[producto] = cantidad

print("Total de ventas por producto:")
for producto, total in totales.items():
    print(f"{producto}: {total}")
```

## 10. Buscar un Valor Específico en un Diccionario Anidado

Este ejemplo muestra cómo buscar un valor específico (por ejemplo, una ciudad) dentro de un diccionario anidado:

```python
personas = {
    "Juan": {"edad": 28, "ciudad": "Bogotá", "profesión": "Ingeniero"},
    "María": {"edad": 32, "ciudad": "Medellín", "profesión": "Doctora"},
    "Pedro": {"edad": 24, "ciudad": "Cali", "profesión": "Diseñador"}
}

ciudad_a_buscar = "Medellín"
encontrado = False

for nombre, info in personas.items():
    if info.get("ciudad") == ciudad_a_buscar:
        print(f"{nombre} vive en {ciudad_a_buscar}.")
        encontrado = True
        break

if not encontrado:
    print(f"Nadie vive en {ciudad_a_buscar}.")
```

## 11. Transformar Valores en un Diccionario Anidado

Si quieres aplicar una transformación a los valores de un diccionario anidado, como incrementar la edad de todas las personas en un año:

```python
personas = {
    "Juan": {"edad": 28, "ciudad": "Bogotá", "profesión": "Ingeniero"},
    "María": {"edad": 32, "ciudad": "Medellín", "profesión": "Doctora"},
    "Pedro": {"edad": 24, "ciudad": "Cali", "profesión": "Diseñador"}
}

for nombre, info in personas.items():
    if "edad" in info:
        info["edad"] += 1

print("Edades actualizadas:")
for nombre, info in personas.items():
    print(f"{nombre} ahora tiene {info['edad']} años.")
```

## 12. Construir un Diccionario Anidado desde Listas

Este ejemplo muestra cómo construir un diccionario anidado a partir de dos listas:

```python
nombres = ["Juan", "María", "Pedro"]
profesiones = ["Ingeniero", "Doctora", "Diseñador"]

personas = {}

for i in range(len(nombres)):
    personas[nombres[i]] = {"profesión": profesiones[i], "edad": None, "ciudad": None}

print("Diccionario construido:")
print(personas)
```

## 13. Contar la Frecuencia de Elementos en un Diccionario Anidado

Este ejemplo cuenta cuántas veces aparece cada profesión en un diccionario anidado:

```python
personas = {
    "Juan": {"edad": 28, "ciudad": "Bogotá", "profesión": "Ingeniero"},
    "María": {"edad": 32, "ciudad": "Medellín", "profesión": "Doctora"},
    "Pedro": {"edad": 24, "ciudad": "Cali", "profesión": "Diseñador"},
    "Ana": {"edad": 29, "ciudad": "Bogotá", "profesión": "Ingeniero"}
}

frecuencia_profesiones = {}

for nombre, info in personas.items():
    profesion = info["profesión"]
    if profesion in frecuencia_profesiones:
        frecuencia_profesiones[profesion] += 1
    else:
        frecuencia_profesiones[profesion] = 1

print("Frecuencia de cada profesión:")
for profesion, frecuencia in frecuencia_profesiones.items():
    print(f"{profesion}: {frecuencia}")
```


## Conclusión

Los ciclos anidados son una herramienta poderosa en Python, especialmente cuando se trata de operar sobre estructuras bidimensionales como matrices. Los ejemplos anteriores muestran cómo puedes aplicar estos conceptos a problemas comunes en la programación.
