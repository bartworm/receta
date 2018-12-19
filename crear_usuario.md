# buscar y crear paciente
# empezando

import csv
import sys

rut = input('Ingresar rut sin guion\n')

pacientes_file = csv.reader(open('test.csv', "a"), delimiter=",")

#loop through csv list

with open('people1.csv', 'r') as csvFile:
  for row in csv_file:
      #if current rows 2nd value is equal to input, print that row
      if pacientes_file == row[0]:
          print row
          return row
      else:
        with open('test.csv', 'a') as csvFile:
        writer = csv.writer(csvFile)          #pedir datos, nombres, apellidos, fecha de nacimiento, direccion)
        nombre = input('ingresar nombre')
        apellidos = input('ingresar apellido')
        fecha_de_nacimiento = input('ingresar fecha de nacimiento dd-mm-aaaa, numeros')
        direccion = input('ingresar fecha de nacimiento dd-mm-aaaa, numeros')
        csvdata = [rut, nombres, apellidos, fecha_de_nacimiento, direccion]
        writer.writerows(csvdata)

      
          





with open('people1.csv', 'a') as csvFile:
    writer = csv.writer(csvFile)
    writer.writerow(row)

csvFile.close()
        

