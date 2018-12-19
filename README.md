# receta
from datetime import date
import datetime
from datetime import datetime
from fpdf import FPDF
import time

numero_de_ficha = 1
paciente = ('17402063-9', ('Bernardo', 'Javier'), ('Pinochet', 'Yañez'), '18/09/1989', 'Padre leon dehon 6271')
doctor = ('166088811-9', ('Mariano','Andres'), ('Pinochet','Yañez'), ('17/04/1988'), 'cirujano', '42154', 'mpinochet')


fecha_nacimiento = datetime.strptime(paciente[3], '%d/%m/%Y')
print (fecha_nacimiento.year)



pdf = FPDF('P', 'mm', 'A5' )
pdf.add_page()

#centro medico

pdf.set_font('Arial', '', 14)
pdf.set_xy(4, 4)
pdf.write(0, 'Clinica Messi ')
# altura fila, string escribir

pdf.set_xy(4, 80)
pdf.write(0, str(numero_de_ficha))

#fecha
pdf.set_xy(10, 40)
pdf.write(0, 'str(datem)')

#datos paciente
#Paciente

pdf.set_xy(15, 80)# x ancho y alto
pdf.write(0, paciente[1][0] + paciente[1][1] )

#rut_paciente
pdf.set_xy(30, 90)
pdf.write(0, paciente[0])

#edad_paciente
pdf.set_xy(40, 80)
pdf.write(0, '29' )

#direccion
pdf.set_xy(60, 100)
pdf.write(0, paciente[4] )

#datos doctor

#Nombre_doctor

pdf.set_xy(70, 120)
pdf.write(0, doctor[1][0] + doctor[1][1] )

#especialid_doctor

pdf.set_xy(70, 140)
pdf.write(0, doctor[4])

#rut_doctor

pdf.set_xy(70, 200)
pdf.write(0, doctor[0])

#rcm_doctor

pdf.set_xy(42, 150)
pdf.write(0, doctor[5])

#firma_doctor

pdf.set_xy(90, 80)
pdf.write(0, doctor[6])


#receta

#diagnostico
'''
pdf.set_font('Arial', 'B', 15)
pdf.write(20, 10, 'resfrio')

#medicamento

pdf.set_font('Arial', 'B', 15)
pdf.write(24, 10, 'medicamento')

#dosis
pdf.set_font('Arial', 'B', 15)
pdf.write(24, 20, 'medicamento')

#medicacion

pdf.set_font('Arial', 'B', 15)
pdf.write(24, 20, '1 comprimido al dia por 3 dias')'''

pdf.output('receta1.pdf')
