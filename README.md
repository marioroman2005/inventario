#1. Programa de gestión de inventario
#Crea un programa que permita a un usuario gestionar un inventario de productos.
# El programa debe permitir:

#Agregar productos (nombre, cantidad, precio).
#Eliminar productos.
#Actualizar la cantidad de un producto.
#Mostrar el inventario completo.
#Usa un diccionario para almacenar los productos.
inventario = {}
def agregar_producto(nombre, cantidad, precio):
    inventario[nombre] = {'cantidad': cantidad, 'precio': precio}


def eliminar_producto(nombre):
    if nombre in inventario:
        del inventario[nombre]
        print(f"Producto '{nombre}' eliminado.")
    else:
        print(f"El producto '{nombre}' no existe en el inventario.")
        
        
def actualizar_cantidad_producto(nombre, cantidad):
    if nombre in inventario:
        inventario[nombre]['cantidad'] = cantidad
        print(f"Cantidad de '{nombre}' actualizada a {cantidad}.")
    else:
        print(f"El producto '{nombre}' no existe en el inventario.")
    

def mostrar_inventario():
    """Muestra todos los productos en el inventario"""
    if not inventario:
        print("El inventario está vacío.")
    else:
        print("\nInventario:")
        for nombre, datos in inventario.items():
            print(f"Producto: {nombre}, Cantidad: {datos['cantidad']}, Precio: ${datos['precio']:.2f}")
    print()

# Ejemplo de uso
agregar_producto("Manzanas", 10, 2.5)
agregar_producto("Peras", 5, 3.0)
mostrar_inventario()
actualizar_cantidad_producto("Manzanas", 20)
eliminar_producto("Peras")
mostrar_inventario()

          
