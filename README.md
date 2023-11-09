# proyecto mect prom
Para el desarrollo de este código se generó por medio de chatGPt en donde se le solicito de manera clara y precisa lo siguiente 
porfavor realiza un codigo en python en donde por medio de los materiales que se tienen en stock que son 3 los cuales son un acero 1100 con limite elastico de 34 Mpa resistencia maxima de 90 Mpay una dureza brinell de 23 el segundo es un aluminio 6061 con limite elastico de 55 Mpa resistencia maxima de 124Mpa y una dureza brinell de 30 y el tercero de ellos es aluminio 7075 con limite elastico de 103 Mpa resistencia maxima de 228 Mpa y una dureza brinell de 60, para la releccion se toma en cuenta que sea el valor mas cercano por debajo de lo que se esta pidiendo en donde cumpla que los tres valores sean los mas sercanos al que se esta pidiendo al ver que no se tiene o que los rangos estan por arriba decirle al usuario que el material no se encuentra en stock, además se le tiene que pedir al usuario los valores de límite elástico, resistencia máxima, dureza brinell 
Al ejecutar este se presenta un problema, el cual se le pide directamente a chatGPT que lo corrija y genere el nuevo código como se muestra a continuación
Pregunta 2 

porfavor corrigeme el codigo anterior pues no es los valores mas cercanos a los valores que el usuario solicita sino que los 3 valores esten por encima de los que el usuario solicita
 
Al observar que el funcionamiento correcto de este mismo se le genera el proceso de ampliación del código permitiendo tener un mayor campo del mismo en donde se implementa un listado en Excel de los materiales con sus principales características.
Preguna 3

el codigo esta correcto ahora ayudame a que los valores sean tomados de un documento de excel en donde se pueden tener entre 3 a 10 materiales con distintos valores y me genere el mismo proceso variando entre los 3 a 10 materiales
 
Al ejecutar esto se nos presentó que nos daba múltiples respuestas a lo cual se necesitaba más precisión en donde se pide más precisión y se genera el ultimo código. 
Pregunta 4

por favor corregir este error del código anterior FileNotFoundError: [Errno 2] No existe tal archivo o directorio: 'materiales.xlsx'

# Cargar los datos desde un archivo Excel
df = pd.read_excel('materiales.xlsx')  # Asegúrate de que el archivo 'materiales.xlsx' contenga tus datos

# Solicitar valores al usuario
limite_elastico_deseado = float(input("Ingrese el límite elástico deseado (Mpa): "))
resistencia_maxima_deseada = float(input("Ingrese la resistencia máxima deseada (Mpa): "))
dureza_brinell_deseada = float(input("Ingrese la dureza Brinell deseada: "))

mejor_ajuste = float("inf")
material_seleccionado = None

# Iterar a través de los materiales en el archivo Excel
for index, row in df.iterrows():
    if (
        row["Límite Elástico (Mpa)"] >= limite_elastico_deseado
        and row["Resistencia Máxima (Mpa)"] >= resistencia_maxima_deseada
        and row["Dureza Brinell"] >= dureza_brinell_deseada
    ):
        diferencia_limite = row["Límite Elástico (Mpa)"] - limite_elastico_deseado
        diferencia_resistencia = row["Resistencia Máxima (Mpa)"] - resistencia_maxima_deseada
        diferencia_dureza = row["Dureza Brinell"] - dureza_brinell_deseada
        suma_diferencias = (
            diferencia_limite ** 2 + diferencia_resistencia ** 2 + diferencia_dureza ** 2
        )

        if suma_diferencias < mejor_ajuste:
            mejor_ajuste = suma_diferencias
            material_seleccionado = row["Material"]

# Comprobar si se encontró un material adecuado
if material_seleccionado:
    print(f"El material más cercano en stock que cumple con los criterios es: {material_seleccionado}")
else:
    print("Ningún material en stock cumple con los criterios especificados.")
# clasificacion de materiales 
para el codigo de la clasificación del material se genera la pregunta 
# Pregunta realizada
“por favor regalame un codigo para python en donde se implementen librerias basicas , para generar la clasificación de materiales respecto a su pero ya su volumen teniendo 9 espacion o lugares en donde se tienen los rangos de( si no están en estos rangos una zona 10 donde se colocara) primer espacio: volumen de los 8 a 5.5 metros cubiscos y un peso de 6000 kilogramos a los 4000kilogramos segundo espacion: volumen de los 5.5 a 3 metros cubiscos y un peso de 6000 kilogramos a los 4000kilogramos tercer espacio: volumen de los 3 o menos metros cubiscos y un peso de 6000 kilogramos a los 4000kilogramos cuarto espacio: volumen de los 8 a 5.5 metros cubiscos y un peso de 4000 kilogramos a los 2000kilogramos quinto espacion: volumen de los 5.5 a 3 metros cubiscos y un peso de 4000 kilogramos a los 2000kilogramos sexto espacio: volumen de los 3 o menos metros cubiscos y un peso de 4000 kilogramos a los 2000kilogramos septimo espacio: volumen de los 8 a 5.5 metros cubiscos y un peso de 2000 kilogramos a los 0kilogramos octavo espacion: volumen de los 5.5 a 3 metros cubiscos y un peso de 2000 kilogramos a los 0kilogramos noveno espacio: volumen de los 3 o menos metros cubiscos y un peso de 2000 kilogramos a los 0kilogramos” 
# Descripcion 
Donde se espesifican los rangos lo que se quiere los materiales entre otras cosas, este programa se desarrolla para ayudar a una empresa de metales a clasificar y organizar sus metales de una manera correcta y sencilla. 
Esto nos generó errores, principal mente se le pidió el a chatGPT que nos desglose el proceso de ejecución del programa para poder descargar las librerías utilizadas entre otros elementos que se usan.
Por otro lado, se le solicita la corrección de los rangos puesto que estaban invertidos y por ultimo nos entrega el código final.
