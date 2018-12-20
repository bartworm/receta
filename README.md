# receta
# empezando
from datetime import date
import datetime
from datetime import datetime
from fpdf import FPDF
import time

numero_de_ficha = 1
paciente = ('17402063-9', ('Bernardo', 'Javier'), ('Pinochet', 'Yañez'), '18/09/1989', 'Padre leon dehon 6271', 'isapre', 'Empleador', 'seguro')
doctor = ('166088811-9', ('Mariano','Andres'), ('Pinochet','Yañez'), ('17/04/1988'), 'cirujano', '42154', 'mpinochet')
clinica = ('166088811-9', 'Clinica Messi', 'direccion', 'telefono', 'ciudad')
Receta = ('resfrio', 'amoxicilina', '500mg', 'cada 8 horas', '3 dias')


pdf = FPDF('P', 'mm', 'A5' )
pdf.add_page()


#qr
pdf.set_font('Arial', '', 24)
pdf.set_xy(100, 20)
pdf.write(0, 'qr')

#centro medico
pdf.set_font('Arial', '', 24)
pdf.set_xy(10, 10)
pdf.write(0, 'logo')

pdf.set_font('Arial', '', 8)
pdf.set_xy(10, 25)
pdf.write(0, clinica[1])

pdf.set_xy(10, 30)
pdf.write(0, clinica[2])

pdf.set_xy(10, 35)
pdf.write(0, clinica[3])

pdf.set_xy(10, 40)
pdf.write(0, clinica[4])

pdf.set_font('Arial', '', 12)

pdf.set_xy(130, 10)
pdf.write(0, str(numero_de_ficha))

#fecha
pdf.set_xy(90, 60)
pdf.write(0, 'fecha' + '19-12-2018')

#datos paciente
#Paciente

pdf.set_xy(10, 50)
pdf.write(0, 'nombre ' + paciente[1][0] + ' ' + paciente[1][1] + ' ' + paciente[2][0] + ' '+ paciente[2][1] )

#rut_paciente
pdf.set_xy(10, 60)
pdf.write(0, 'rut ' + paciente[0])

#edad_paciente
pdf.set_xy(10, 70)
pdf.write(0, '29' )

#direccion
pdf.set_xy(10, 80)
pdf.write(0, paciente[4] )

#datos doctor

#Nombre_doctor

pdf.set_xy(80, 150)
pdf.write(0, doctor[1][0] +' ' + doctor[2][0] )

#especialid_doctor

pdf.set_xy(80, 155)
pdf.write(0, doctor[4])

#rut_doctor

pdf.set_xy(80, 160)
pdf.write(0, doctor[0])

#rcm_doctor

pdf.set_xy(80, 165)
pdf.write(0, doctor[5])

#firma_doctor

pdf.set_xy(110, 180)
pdf.write(0, doctor[6])


#receta

#diagnostico

receta = ('resfrio', 'amoxicilina', '500mg', 'cada 8 horas', '3 dias')
#medicamento
pdf.set_xy(10, 90)
pdf.write(0, 'Diagnostico ' + receta[0])

#dosis
pdf.set_xy(10, 100)
pdf.write(0, receta[1] + ' ' + receta[2] + ' ' + receta[3] + ' '+ receta[4])

pdf.output('receta1.pdf')

