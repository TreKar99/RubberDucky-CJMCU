# Configuracion-CJMCU-BadUSB
Configuración del CJMCU como un Rubber Ducky (BadUSB).

El original: https://shop.hak5.org/products/usb-rubber-ducky-deluxe.

El dispositivo CJMCU es una alternativa al Rubber Ducky oficial de Hak5, bastante más económico.
Para usarlo como un BadUSB debemos configurarlo, tendremos que compilar en la CPU ATMELMEGA32U4 el firmware de Arduino como un Keyboard.

Usaremos el script.txt como ejemplo de payload, y en él podremos modificar las instrucciones que queremos dar.

Pasos para la configuración:

1. Instalar el software Arduino IDE.
  En Windows lo podemos instalar desde la Microsoft Store
  
  ![image](https://user-images.githubusercontent.com/101529212/175328917-07a21dac-8861-4054-b542-848f78368ace.png)
 
  Pero como método general lo instalaremos desde la página oficial: https://www.arduino.cc/en/software
  
  
2. Añadimos la libreria Arduino_keyboard_LBDL.

![image](https://user-images.githubusercontent.com/101529212/175327190-2652fbb7-8f12-4f89-b0e6-7b94a47b2096.png)

![image](https://user-images.githubusercontent.com/101529212/175327293-6487e54a-da16-4a99-a813-f5f1eb67766b.png)

3. Conectar tarjeta microSD individualmente para meter la carpeta lang y el script.txt.

  Insertamos la tarjeta en el portátil, sea con una tarjeta adaptador o con usb adaptador, y copiamos estos dos archivos.
  
  Consejo: usar una tarjeta microSD de bajo tamaño ya que por una banda no es necesario mucho espacio y mucho tamaño puede no ser compatible con el BadUSB.

4. Poner la tarjeta microSD en el CJMCU - badUSB.

5. Abrir el archivo cjmcu_badusb_es, conectar el CJMCU, y configurarlo.
  
  Importante: poner modo de Arduino -> Arduino Leonardo.
  
![image](https://user-images.githubusercontent.com/101529212/175327727-9d00b22f-e8b0-465f-a869-ed8e51dddc1e.png)

  Importante: escoger el puerto que nos salga predeterminado, en mi caso el COM3.
  
![image](https://user-images.githubusercontent.com/101529212/175327837-f990dafe-693b-445b-83f9-d6ff117d37c2.png)

6. Compilar en la placa del badUSB el firmware de configuración de placa base.

![image](https://user-images.githubusercontent.com/101529212/175327960-64f3bf8e-64f1-4392-9ad3-b194096cb903.png)

7. Configurar el payload desde la consola serial.

![image](https://user-images.githubusercontent.com/101529212/175328317-0c129ebc-1577-4bef-95b8-5dd4569893de.png)

  Introducimos las opciones siguientes para el correcto funcionamiento: 
  
    - Modo: c.
    
    - Lenguaje: es.
    
    - Payload: script.txt
    
![image](https://user-images.githubusercontent.com/101529212/175328343-aa966e8d-ed88-4b88-89c0-0c0beb450940.png)

Ejemplo de funcionamiento:

https://user-images.githubusercontent.com/101529212/175333350-de40f86b-b7b2-4198-927f-dbdcf89a4e8e.mp4




Créditos de los arreglos de la librería del firmware y librería de Arduino a: https://github.com/labuhardilladelloco/Bad-duck-esp
