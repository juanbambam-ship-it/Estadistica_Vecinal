# ==========================================================
# CENTRO ESTADÍSTICO VECINAL AVANZADO v2.0
# Proyecto STEAM - Estadística con Python
# ==========================================================

import csv
import os

# ==========================================================
# 🚀 DESAFÍO DEL PROGRAMADOR
# Biblioteca para generar gráficas
# Si no está instalada:
# pip install matplotlib
# ==========================================================

try:
    import matplotlib.pyplot as plt
    GRAFICAS = True
except:
    GRAFICAS = False

print("=" * 60)
print("        CENTRO ESTADÍSTICO VECINAL AVANZADO")
print("=" * 60)

# ==========================================================
# 🚀 DESAFÍO DEL PROGRAMADOR
# ¿Cómo deseas capturar la información?
# ==========================================================

print("\n1. Capturar respuestas manualmente")
print("2. Leer respuestas desde archivo CSV")

opcion = input("\nSelecciona una opción (1 ó 2): ")

datos_encuesta = []

# ==========================================================
# CAPTURA MANUAL
# ==========================================================

if opcion == "1":

    cantidad = int(input("\n¿Cuántos participantes responderán?: "))

    print()

    for i in range(cantidad):

        respuesta = int(input(f"Respuesta del participante {i+1} (1-10): "))

        datos_encuesta.append(respuesta)

# ==========================================================
# 🚀 DESAFÍO DEL PROGRAMADOR
# LECTURA DESDE CSV
# ==========================================================

elif opcion == "2":

    nombre_archivo = input("\nNombre del archivo CSV: ")

    if os.path.exists(nombre_archivo):

        with open(nombre_archivo, newline='', encoding="utf-8") as archivo:

            lector = csv.reader(archivo)

            next(lector)

            for fila in lector:

                try:
                    datos_encuesta.append(int(fila[0]))
                except:
                    pass

    else:

        print("\nNo se encontró el archivo.")
        exit()

else:

    print("\nOpción incorrecta.")
    exit()

# ==========================================================
# FUNCIONES ESTADÍSTICAS
# ==========================================================

total = len(datos_encuesta)
suma = sum(datos_encuesta)
promedio = suma / total
mayor = max(datos_encuesta)
menor = min(datos_encuesta)

# ==========================================================
# 🚀 DESAFÍO DEL PROGRAMADOR
# CALCULAR PORCENTAJES
# ==========================================================

conteo = {}

for dato in datos_encuesta:

    if dato in conteo:
        conteo[dato] += 1
    else:
        conteo[dato] = 1

# ==========================================================
# REPORTE
# ==========================================================

print("\n")
print("=" * 60)
print("        INFORME ESTADÍSTICO")
print("=" * 60)

print("Participantes :", total)
print("Suma          :", suma)
print("Promedio      :", round(promedio,2))
print("Valor máximo  :", mayor)
print("Valor mínimo  :", menor)

print("\nPORCENTAJES")

for valor in sorted(conteo):

    porcentaje = conteo[valor] / total * 100

    print(f"Respuesta {valor}: {conteo[valor]} personas ({porcentaje:.1f} %)")

# ==========================================================
# DIAGNÓSTICO
# ==========================================================

print("\n")
print("=" * 60)
print("DIAGNÓSTICO")
print("=" * 60)

if promedio < 4:

    print("🔴 ALERTA")
    print("La comunidad presenta problemas importantes.")
    print("Se recomienda solicitar apoyo a las autoridades.")

elif promedio < 7:

    print("🟡 NECESITA MEJORAS")
    print("Existen áreas de oportunidad para mejorar los servicios.")

else:

    print("🟢 RESULTADO FAVORABLE")
    print("La comunidad presenta buenas condiciones generales.")

# ==========================================================
# 🚀 DESAFÍO DEL PROGRAMADOR
# GUARDAR REPORTE EN TXT
# ==========================================================

with open("reporte_estadistico.txt","w",encoding="utf-8") as archivo:

    archivo.write("CENTRO ESTADÍSTICO VECINAL\n")
    archivo.write("="*45 + "\n\n")

    archivo.write(f"Participantes : {total}\n")
    archivo.write(f"Suma          : {suma}\n")
    archivo.write(f"Promedio      : {round(promedio,2)}\n")
    archivo.write(f"Máximo        : {mayor}\n")
    archivo.write(f"Mínimo        : {menor}\n\n")

    archivo.write("PORCENTAJES\n")

    for valor in sorted(conteo):

        porcentaje = conteo[valor] / total * 100

        archivo.write(
            f"Respuesta {valor}: {conteo[valor]} personas ({porcentaje:.1f} %)\n"
        )

print("\n✔ Reporte guardado como: reporte_estadistico.txt")

# ==========================================================
# 🚀 DESAFÍO DEL PROGRAMADOR
# GENERAR GRÁFICA
# ==========================================================

if GRAFICAS:

    etiquetas = []
    cantidades = []

    for valor in sorted(conteo):

        etiquetas.append(str(valor))
        cantidades.append(conteo[valor])

    plt.figure(figsize=(8,5))
    plt.bar(etiquetas, cantidades)

    plt.title("Resultados de la Encuesta")
    plt.xlabel("Calificación")
    plt.ylabel("Frecuencia")

    plt.grid(axis="y")

    plt.show()

else:

    print("\nMatplotlib no está instalado.")
    print("Instálalo con:")
    print("pip install matplotlib")

# ==========================================================
# MENSAJE FINAL
# ==========================================================

print("\n")
print("=" * 60)
print("Gracias por utilizar el")
print("CENTRO ESTADÍSTICO VECINAL")
print("=" * 60)
