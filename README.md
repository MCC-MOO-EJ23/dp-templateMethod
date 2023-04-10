# Template Method - Caso práctico

### Intención

Define el esqueleto de un algoritmo en una operación, difiriendo algunos de los pasos a subclases. Template Method permite que las subclases redefinan ciertos pasos de un algoritmo sin cambiar la estructura del algoritmo.

### Clasificación

Patrón de Comportamiento

### Vista Estructural

![image](https://user-images.githubusercontent.com/84739791/230807009-8b6144c4-7062-4b5f-a609-b07ef887a570.png)

### Vista Dinámica

![image](https://user-images.githubusercontent.com/84739791/230807057-0b63a8a2-fda0-4629-85f4-13b827572eac.png)

### Ejemplo Real

Si alguno de nosotros ha trabajado alguna vez para empresas de venta de 
servicios, verá que es muy común que las empresas busquen establecer 
convenios con otras empresas (como podrían ser farmacias o tiendas de 
abarrotes) con el fin de que los clientes puedan pagar sus servicios a través de 
sus sucursales. Un ejemplo muy común es el pago del recibo del agua, luz 
eléctrica, gas, teléfono, internet, televisión de paga, entre otros. Todas estas 
compañías dan la opción a sus clientes de pagar estos servicios en las tiendas de 
su preferencia. 
Estos establecimientos cada día tienen que enviarnos el concentrado con todos 
los pagos que recibieron por parte de nuestros clientes, de tal manera que 
nosotros podamos aplicar estos pagos en nuestros sistemas. Estos concentrados 
por lo general son archivos planos de texto donde se concentra básicamente el
número de cliente, monto pagado, forma de pago y la fecha en que se realizó el 
pago.
Pues bien, nuestro cliente nos ha solicitado que implementemos un componente 
de software que tome estos archivos y aplique los pagos en su sistema. Hasta 
aquí todo suena bien, sin embargo, tenemos un pequeño problema, cada 
establecimiento nos entrega la información en un formato distinto.
Los requerimientos para desarrollar este componente son los siguientes:

* Los archivos pueden llegar en diferente formato por establecimiento.
* El formato cambia pero la información minina necesaria siempre viene en 
el documento.
* Los archivos no se pueden procesar más de una vez.
* El nombre del documento es validado por establecimiento y cada 
establecimiento puede tener diferente formato.
* Para aplicar el pago se debe validar que el cliente exista en nuestro 
sistema.
* Una vez procesado el documento se debe generar un archivo de log 
donde indique los pagos aplicados y los rechazados con su respectiva explicación del motivo del rechazo, además, el archivo procesado deberá 
ser movido a una carpeta de archivos procesados.
* Los pagos recibidos por los establecimientos no deberán ser mayores de 
$200.

### Solución sin el patrón Template:

![image](https://user-images.githubusercontent.com/84739791/230807487-98bd01a1-7acc-48bc-9c48-1ffab070c082.png)

### Solución con el patrón Template:

Para darle una mejor solución implementaremos el patrón de diseño Template 
Method, que nos permitirá establecer los pasos por lo que el procesamiento de 
archivos deberá pasar sin importar el establecimiento que envíe el documento.
Para lograr esto deberemos definir los pasos requeridos para poder procesar 
cualquier archivo de pagos:
1. **validateName**: Primer paso, valida el nombre del documento.
2. **validateProcess**: Segundo paso, valida que el documento no haya sido 
procesado anteriormente.
3. **processFile**: Tercer paso, procesará el documento, analizando cada 
pago (línea), aplicará el pago y localizará los errores.
4. **createLog**: Cuarto paso, generar un Log con los pagos procesados 
exitosamente y los errores encontrados.
5. **moveDocument**: Quinto paso, moverá el documento a una carpeta de 
documentos procesados.
6. **markAsProcessFile**: Sexto paso, registrará el documento como 
procesado impidiendo que un mismo archivo sea procesado más de una 
vez.

![image](https://user-images.githubusercontent.com/84739791/230807759-78699bd6-f753-46d1-84bd-606bcd0ff2d0.png)

![image](https://user-images.githubusercontent.com/84739791/230807889-e7d33049-924b-4773-aec8-f45b3c1185c1.png)

# Ejecutar Java-App 

* Cargue las Extensiones Java de VS Code correcta y completamente.
* En la clase principal de clic sobre el botón Play.

