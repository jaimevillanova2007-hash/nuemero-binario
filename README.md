# # Función para crear la lista de 2 en 2 hasta 30
def crear_lista():
    lista = []
    
    for i in range(2, 30, 2):  # de 2 en 2 hasta 30
        lista.append(i)
    
    return lista


# Función para pedir número válido
def pedir_numero(mensaje):
    num = input(mensaje)
    while not num.isdigit():
        print("Error, ingrese solo números")
        num = input(mensaje)
    return int(num)


# Función de búsqueda binaria con while
def busqueda_binaria(lista, numero):
    izq = 0
    der = len(lista) - 1
    pasos = 0

    while izq <= der:
        pasos += 1
        cen = (izq + der) // 2

        print("\nPaso:", pasos)
        print("izq:", izq, "der:", der, "centro:", cen, "valor:", lista[cen])

        if lista[cen] == numero:
            return cen, pasos
        elif lista[cen] < numero:
            print("Buscando a la derecha...")
            izq = cen + 1
        else:
            print("Buscando a la izquierda...")
            der = cen - 1

    return -1, pasos


# Programa principal
print("=== BÚSQUEDA BINARIA ===")

arreglo = crear_lista()
print("Lista:", arreglo)

buscar = pedir_numero("Ingrese el número a buscar: ")

resultado, pasos = busqueda_binaria(arreglo, buscar)

# Resultado final
print("\n=== RESULTADO ===")
if resultado != -1:
    print("Número encontrado en la posición:", resultado)
else:
    print("Número no encontrado")

print("Total de pasos:", pasos)