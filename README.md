# Mi-aportacion
Agregare mi aportacion al proyecto final

while True:   #ayudar a hacer un bucle hasta que el usuario decida detener el bucle
  nombre_alimento = input("Ingrese el nombre del alimento (o escriba 'es todo' para finalizar): ") #tambien ayude a realizar e bucle while, una de mis compañeras le aegrego else
  if nombre_alimento.lower() == 'es todo':
    break
  else: #Esta es la parte que complemento mi compañera
      try:
          peso = float(input(f"Ingrese el peso en kg de {nombre_alimento}: "))
          alimentos.loc[len(alimentos)] = [nombre_alimento, peso]
      except ValueError:
          print("Error: Ingrese una cantidad numérica válida.")


print("\nTabla de alimentos registrados:") #esta la realizo otro de mis compañeros
print(alimentos)

try: #esta parte donde se realiza el excel fue en la que ayude
    archivo = input("Ingrese nombre del archivo: ")#esto sirve para que al finalizar se guarde la tabla en un archivo excel
    extencion_archivo = f"{archivo}.xlsx"
    alimentos.to_excel(extencion_archivo, index=False)
    print(f"\nLa tabla de alimentos ha sido guardada en el archivo '{extencion_archivo}'.") #aqui puse ya se guarda en el erchivo excel
except FileNotFoundError:
  print("Error: Archivo no encontrado.")
