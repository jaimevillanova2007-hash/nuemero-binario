# funcion para pedir la opcion valuida

def perdi_nuemro (mensajes) :
    num = input("mensaje")
    while not num.isdigit():
         print("error, ingrese solo numeros")
         num = input("mensaje")
    return int(num)

# Función para crear la lista
def crear lista():
    lista = []
    n = int(input("¿Cuántos números desea ingresar? "))

    for i in range(n):
        num = int(input(f"Ingrese número {i+1}: "))
        lista.append(num)

    lista.sort()  # Ordenar la lista
    return lista


# Función de búsqueda binaria con while
def busqueda binaria(lista, numero):
    izq = 0
    der = len(lista) - 1

    while izq <= der:
        cen = (izq + der) // 2

        if lista[cen] == numero:
            return cen
        elif lista[cen] < numero:
            izq = cen + 1
        else:
            der = cen - 1

    return -1


# Programa principal
print("BÚSQUEDA BINARIA ")

arreglo = crear_lista()
print("Lista ordenada:", arreglo)

buscar = int(input("Ingrese el número a buscar: "))

resultado = busqueda_binaria(arreglo, buscar)

# Resultado
if resultado != -1:
    print("Número encontrado en la posición:", resultado)
else:
    print("Número no encontrado")# nuemero-binario
